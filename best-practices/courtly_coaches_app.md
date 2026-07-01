# Courtly Coaches (Android) — Cumplimiento y puntos a mejorar

App de coaches, nativa en Kotlin con Jetpack Compose y Material 3. Arquitectura
limpia por contextos (iam, coaches, availabilities) con MVVM (`StateFlow` +
`ViewModel`). minSdk 24, targetSdk 36. Se revisó `build.gradle.kts`, el manifest,
todo el código Kotlin y los recursos.

## Cumplimiento

### Feedback de acciones — `PS-V1`
Cobertura de estados muy completa: spinner dentro de los botones, estado de error con
reintento, estado vacío real y éxito consumido vía flag con `LaunchedEffect`.
Evidencia: `SignInScreen.kt:285`, `CoachProfileScreen.kt:81`, `AvailabilityScreen.kt:201`.

### Manejo de errores y validación — `ERR-V1`
`SignInViewModel` traduce cada excepción de red (`UnknownHostException`,
`SocketTimeoutException`, `SSLHandshakeException`, `HttpException` por código) a un
mensaje de usuario. Validación previa a la llamada en los ViewModels.
Evidencia: `SignInViewModel.kt:272`, `CoachViewModel.kt:217`.

### Tráfico encriptado — `SC-N1`
Base URL HTTPS, sin `usesCleartextTraffic="true"`, y con `targetSdk 36` el cleartext
está deshabilitado por defecto. El token se adjunta por interceptor con exclusión de
endpoints públicos.
Evidencia: `RetrofitClient.kt:11`, `AuthInterceptor.kt:15`.

### Permisos — `PERM-V1`
El único permiso declarado es `INTERNET`, el estrictamente necesario, sin permisos
peligrosos.
Evidencia: `AndroidManifest.xml:5`.

### Navegación — `UX-N1` (parcial)
`NavHost` único con back-stack manejado, bottom bar con `saveState` / `restoreState` /
`launchSingleTop`, y botones de volver con `popBackStack()`.
Evidencia: `CoachNavigation.kt:129,258`.

### Hit targets — `UX-B1` (parcial)
Botones primarios con `.height(52.dp)` e ítems de bottom bar de 64x62 dp.
Evidencia: `SignInScreen.kt:280`, `CourtlyCoachBottomBar.kt:140`.

## Puntos a mejorar

### Token en SharedPreferences sin cifrar — `SC-N2` (alta prioridad)
El token JWT y los datos de usuario se guardan en `SharedPreferences` en texto plano,
pese a que la dependencia de cifrado (`androidx.security:security-crypto`) ya estaba
declarada en el proyecto sin usarse.
Evidencia: `SessionStorage.kt:8`, `build.gradle.kts:79`.
Corrección: usar `EncryptedSharedPreferences` con `MasterKey` AES256-GCM.

### Sin network security config explícito — `SC-N3`
No existía `res/xml/network_security_config.xml` ni `android:networkSecurityConfig`.
Hoy funciona por el default de targetSdk, pero no hay defensa en profundidad.
Evidencia: `AndroidManifest.xml:7`.
Corrección: crear el config con `cleartextTrafficPermitted="false"` y referenciarlo
en el manifest.

### Strings hardcodeados — `L10N-V1`
Casi todo el texto visible está en código; `strings.xml` solo tiene `app_name`, y su
valor era el nombre técnico sin marca.
Evidencia: `strings.xml:2`, `SignInScreen.kt:103`, `CourtlyCoachBottomBar.kt:85`.
Corrección aplicada parcial: `app_name` pasa a "Courtly Coaches". La extracción total
a `strings.xml` queda como fase aparte por su volumen.

### Sin modo oscuro — `THEME-V1`
Solo se define `lightColorScheme`; no hay `darkColorScheme`, `values-night/` ni
dynamic color, y el theme XML fuerza `Light`.
Evidencia: `Theme.kt:11`, `themes.xml:4`.
Recomendación: agregar `darkColorScheme` según `isSystemInDarkTheme()`.

### Lista sin virtualizar — `PERF-N1`
Las disponibilidades se renderizan con `forEach` dentro de un `Column` scrollable, sin
`LazyColumn` ni `key`.
Evidencia: `AvailabilityScreen.kt:146,218`.
Corrección: usar `LazyColumn { items(..., key = { it.id }) }`.

### Dependencias recreadas por recomposición — `PERF-N2`
`CoachAvailabilityScreen` construye el `ApiService`, el repositorio y seis use-cases en
el cuerpo del composable, rehaciéndolos en cada recomposición.
Evidencia: `CoachAvailabilityScreen.kt:21`.
Corrección: envolver la construcción en `remember { }`.

### Accesibilidad: estado por color y iconos sin descripción — `A11Y-V1`
El `StatusDot` comunica el estado solo por color, sin `semantics`, y varios iconos
informativos tienen `contentDescription = null`.
Evidencia: `AvailabilityScreen.kt:443`, `CoachNavigation.kt:283`.
Corrección: agregar `contentDescription` / `semantics` al punto de estado y a los
iconos con significado.

### Targets clickables por debajo de 48 dp — `A11Y-B1`
Los tabs de auth (`.height(44.dp)`) y algunos ítems del bottom bar usan `clickable`
sobre `Box`/`Column` sin garantizar el mínimo interactivo de 48 dp.
Evidencia: `SignInScreen.kt:176`, `CourtlyCoachBottomBar.kt:143`.
Corrección: aplicar `Modifier.minimumInteractiveComponentSize()` o subir la altura.

### Contraste y tamaños de texto al límite — `PS-V2`
Textos secundarios de 10 a 11 sp con opacidad baja sobre fondos claros o navy quedan
en el borde de WCAG AA.
Evidencia: `SignInScreen.kt:104`, `CoachProfileScreen.kt:253`.
Corrección: subir labels a 12 sp o más y evitar opacidades menores a 0.7 para texto.

### Sin TopAppBar ni back handling explícito — `UX-N2`
No hay `TopAppBar` / up-navigation; los títulos son `Text` sueltos y no hay
`BackHandler` en formularios con cambios sin guardar.
Evidencia: navegación por botones "Volver" y back del sistema.
Recomendación: `Scaffold` + `TopAppBar` con `navigationIcon` y `BackHandler` en
formularios.

### Insets incompletos fuera del Scaffold — `RES-V1`
Se llama `enableEdgeToEdge()` pero `SignInScreen` está fuera del `Scaffold` y solo
aplica `imePadding()`, sin `statusBarsPadding()`, por lo que el contenido superior
puede dibujarse bajo la barra de estado.
Evidencia: `MainActivity.kt:151`, `SignInScreen.kt:74`.
Corrección: aplicar `Modifier.statusBarsPadding()` al contenedor raíz.

### Editor de disponibilidad sin validación de formato — `ERR-V2`
El diálogo acepta fecha y hora como texto libre (`YYYY-MM-DD`, `HH:mm`) y no valida
formato antes de enviar al backend.
Evidencia: `AvailabilityScreen.kt:588`, `AvailabilityViewModel.kt:99`.
Corrección: validar formato con regex antes de enviar, mostrando error inline.
</content>
