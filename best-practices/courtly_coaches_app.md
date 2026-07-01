# Courtly Coaches (Android): cumplimiento y puntos a mejorar

Courtly Coaches es la aplicación para entrenadores, desarrollada de forma nativa en
Kotlin con Jetpack Compose y Material 3. Sigue una arquitectura limpia por contextos
(iam, coaches y availabilities) con el patrón MVVM sobre `StateFlow` y `ViewModel`, y
apunta a minSdk 24 y targetSdk 36. La revisión cubrió la configuración Gradle, el
manifest, todo el código Kotlin y los recursos.

## Cumplimiento

### Feedback de acciones (`PS-V1`)

La cobertura de estados es amplia y consistente en todo el flujo. Los botones muestran
un spinner mientras trabajan, el error tiene una vista dedicada con opción de reintentar,
el estado vacío es real y el éxito se consume mediante una bandera con `LaunchedEffect`.
La evidencia está en `SignInScreen.kt:285`, `CoachProfileScreen.kt:81` y
`AvailabilityScreen.kt:201`.

### Manejo de errores y validación (`ERR-V1`)

El `SignInViewModel` traduce cada excepción de red a un mensaje comprensible, ya sea
`UnknownHostException`, `SocketTimeoutException`, `SSLHandshakeException` o un
`HttpException` según su código. La validación se ejecuta antes de la llamada en los
ViewModels. La evidencia está en `SignInViewModel.kt:272` y en `CoachViewModel.kt:217`.

### Tráfico encriptado (`SC-N1`)

La URL base usa HTTPS y el manifest no habilita `usesCleartextTraffic`. Con targetSdk 36
el tráfico en texto plano queda deshabilitado por defecto. El token se adjunta mediante
un interceptor que excluye los endpoints públicos. La evidencia está en
`RetrofitClient.kt:11` y en `AuthInterceptor.kt:15`.

### Permisos (`PERM-V1`)

El único permiso declarado es `INTERNET`, el estrictamente necesario, sin permisos
peligrosos de por medio. La evidencia está en `AndroidManifest.xml:5`.

### Navegación (`UX-N1`, parcial)

La app usa un único `NavHost` con el back-stack gestionado, una barra inferior con
`saveState`, `restoreState` y `launchSingleTop`, y botones de retorno que llaman a
`popBackStack()`. La evidencia está en `CoachNavigation.kt:129,258`.

### Hit targets (`UX-B1`, parcial)

Los botones primarios usan `.height(52.dp)` y los elementos de la barra inferior miden
64 por 62 dp. La evidencia está en `SignInScreen.kt:280` y en
`CourtlyCoachBottomBar.kt:140`.

## Puntos a mejorar

### Token en SharedPreferences sin cifrar (`SC-N2`, alta prioridad)

El token JWT y los datos de usuario se guardaban en `SharedPreferences` en texto plano,
a pesar de que la dependencia de cifrado (`androidx.security:security-crypto`) ya estaba
declarada en el proyecto sin usarse. La evidencia está en `SessionStorage.kt:8` y en
`build.gradle.kts:79`. La corrección usa `EncryptedSharedPreferences` con una `MasterKey`
AES256-GCM.

### Sin configuración explícita de seguridad de red (`SC-N3`)

No existía el archivo `res/xml/network_security_config.xml` ni el atributo
`android:networkSecurityConfig`. Aunque hoy la app funciona por el comportamiento por
defecto de targetSdk, no había una defensa explícita. La evidencia está en
`AndroidManifest.xml:7`. La corrección creó la configuración con
`cleartextTrafficPermitted="false"` y la enlazó desde el manifest.

### Textos escritos en el código (`L10N-V1`)

Casi todo el texto visible está incrustado en el código. El archivo `strings.xml` solo
contenía `app_name`, y su valor era el nombre técnico sin marca. La evidencia está en
`strings.xml:2`, `SignInScreen.kt:103` y `CourtlyCoachBottomBar.kt:85`. Como corrección
parcial, `app_name` pasó a "Courtly Coaches". La extracción completa de los textos a
`strings.xml` queda como una fase aparte por su volumen.

### Sin modo oscuro (`THEME-V1`)

El tema define únicamente `lightColorScheme`, sin `darkColorScheme`, sin `values-night/` y
sin dynamic color, y el tema XML fuerza el modo claro. La evidencia está en `Theme.kt:11`
y en `themes.xml:4`. La recomendación es añadir un `darkColorScheme` que responda a
`isSystemInDarkTheme()`.

### Lista sin virtualizar (`PERF-N1`)

Las disponibilidades se dibujaban con `forEach` dentro de un `Column` con scroll, sin
`LazyColumn` ni `key`. La evidencia está en `AvailabilityScreen.kt:146,218`. La
corrección usa `LazyColumn` con `items(..., key = { it.id })`.

### Dependencias recreadas en cada recomposición (`PERF-N2`)

La pantalla `CoachAvailabilityScreen` construía el `ApiService`, el repositorio y seis
casos de uso dentro del cuerpo del composable, por lo que se rehacían en cada
recomposición. La evidencia está en `CoachAvailabilityScreen.kt:21`. La corrección
envuelve esa construcción en `remember`.

### Estado comunicado solo por color e iconos sin descripción (`A11Y-V1`)

El componente `StatusDot` transmitía el estado únicamente mediante el color, sin
`semantics`, y varios iconos informativos tenían `contentDescription = null`. La
evidencia está en `AvailabilityScreen.kt:443` y en `CoachNavigation.kt:283`. La
corrección agregó `contentDescription` y semántica al punto de estado y a los iconos con
significado.

### Elementos clickables por debajo de 48 dp (`A11Y-B1`)

Los tabs de autenticación (`.height(44.dp)`) y algunos elementos de la barra inferior
usaban `clickable` sobre un `Box` o `Column` sin garantizar el mínimo interactivo de 48
dp. La evidencia está en `SignInScreen.kt:176` y en `CourtlyCoachBottomBar.kt:143`. La
corrección aplica `Modifier.minimumInteractiveComponentSize()`.

### Contraste y tamaños de texto en el límite (`PS-V2`)

Varios textos secundarios de 10 a 11 sp, con opacidad baja sobre fondos claros o navy,
quedaban en el borde del ratio WCAG AA. La evidencia está en `SignInScreen.kt:104` y en
`CoachProfileScreen.kt:253`. La recomendación es subir los textos a 12 sp o más y evitar
opacidades por debajo de 0.7.

### Sin TopAppBar ni manejo explícito del botón atrás (`UX-N2`)

No hay `TopAppBar` ni navegación superior. Los títulos son `Text` sueltos y falta un
`BackHandler` en los formularios con cambios sin guardar. La navegación hacia atrás
depende de los botones de retorno y del gesto del sistema. La recomendación es adoptar
`Scaffold` con `TopAppBar` y su `navigationIcon`, y agregar `BackHandler` en los
formularios.

### Insets incompletos fuera del Scaffold (`RES-V1`)

La app llama a `enableEdgeToEdge()`, pero `SignInScreen` queda fuera del `Scaffold` y
solo aplica `imePadding()`, sin `statusBarsPadding()`. Por eso el contenido superior
puede dibujarse debajo de la barra de estado. La evidencia está en `MainActivity.kt:151`
y en `SignInScreen.kt:74`. La corrección aplica `statusBarsPadding()` al contenedor raíz.

### Editor de disponibilidad sin validación de formato (`ERR-V2`)

El diálogo aceptaba la fecha y la hora como texto libre (`YYYY-MM-DD` y `HH:mm`) y no
validaba el formato antes de enviarlo al backend. La evidencia está en
`AvailabilityScreen.kt:588` y en `AvailabilityViewModel.kt:99`. La corrección valida el
formato con expresiones regulares antes de enviar y muestra el error en línea.
</content>
