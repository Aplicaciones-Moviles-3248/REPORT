# Courtly (Flutter): cumplimiento y puntos a mejorar

Courtly es la aplicación de usuarios, construida en Flutter para iOS y Android sobre una
arquitectura por contextos. La revisión cubrió la configuración del proyecto, el tema,
las rutas, la capa compartida, las pantallas de cada contexto con código, los manifests
de Android y el archivo `Info.plist` de iOS.

## Cumplimiento

### Hit targets (`UX-B1` / `Hit Targets`)

Los objetos táctiles principales respetan el tamaño mínimo recomendado, es decir, 44
puntos en iOS y 48 dp en Android. El botón primario global define
`minimumSize: Size(double.infinity, 52)`, el botón central de la barra inferior mide
58 por 58 y los `IconButton` usan el valor por defecto de 48. La evidencia está en
`lib/app/theme/app_theme.dart:26` y en
`lib/shared/presentation/widgets/courtly_bottom_navigation_bar.dart:62`.

### Feedback de acciones (`PS-V1`)

La aplicación cubre de forma pareja los cuatro estados de una operación. La carga se
muestra con `CircularProgressIndicator`, el error incluye un botón para reintentar, el
estado vacío tiene su propia vista y el éxito se confirma con un `SnackBar`. Además, las
listas admiten recarga por gesto. La evidencia está en `payments_screen.dart:120,129,143`
y en `edit_profile_screen.dart:105`.

### Validación y manejo de errores (`ER-V1`)

Todos los formularios se apoyan en `Form` con validadores, y cada llamada de red está
envuelta en `try/catch`. El manejo distingue los fallos de conectividad de los errores
propios del negocio, lo que permite mostrar un mensaje adecuado en cada caso. La
evidencia está en `sign_in_screen.dart:400` y en `api_client.dart:151`.

### Tráfico HTTPS (`SC-N1`, parcial)

La URL base por defecto usa HTTPS y no hay direcciones `http://` en el código de
producción. En iOS se mantiene App Transport Security activo, ya que el `Info.plist` no
introduce excepciones. La evidencia está en `api_client.dart:15`.

### Responsive y safe areas (`RS-N1`)

El diseño usa `SafeArea` de manera sistemática y limita el ancho del contenido en
pantallas grandes con `ConstrainedBox(maxWidth: 430)`. El bottom sheet respeta el
teclado mediante `viewInsets.bottom`. La evidencia está en `sign_in_screen.dart:161` y
en `payments_screen.dart:467`.

### Rendimiento y estado (`PF-N1`)

El código aprovecha `const`, emplea listas perezosas como `GridView.builder` y libera
todos los controllers con `dispose()`. La evidencia está en
`court_search_screen.dart:287` y en `sign_in_screen.dart:146`.

## Puntos a mejorar

### Permiso de INTERNET ausente en el manifest principal (`PM-N1`, bloqueante)

El permiso `INTERNET` solo estaba declarado en los manifests de `debug` y `profile`. En
un build de release el proceso de merge no lo incluye, de modo que toda la red habría
fallado en producción. La evidencia está en `android/app/src/main/AndroidManifest.xml`.
La corrección consistió en declarar
`<uses-permission android:name="android.permission.INTERNET"/>` en el manifest
principal.

### Credenciales y token inseguros (`SC-N2`, alta prioridad)

Se identificaron dos problemas de seguridad. El primero es que el formulario de login
venía con credenciales de prueba precargadas en el código. El segundo es que el token de
sesión se guardaba en `SharedPreferences`, un almacenamiento en texto plano en Android
que tampoco usa Keychain en iOS. La evidencia está en `sign_in_screen.dart:57` y en
`local_storage_service.dart:8`. La corrección quitó la precarga y migró el token a
`flutter_secure_storage`, dejando `SharedPreferences` únicamente para datos no
sensibles.

### Sin botón atrás en las pantallas de detalle (`UX-N1`)

Las pantallas `CourtDetailScreen`, `EditProfileScreen` y `PaymentsScreen` se abren
mediante push, pero ninguna definía un `AppBar`, así que no ofrecían botón de retorno ni
título. En iOS esto deja al usuario sin una forma clara de volver. La evidencia está en
`court_detail_screen.dart:38` y en `edit_profile_screen.dart:131`. La corrección agregó
un `AppBar` con título, con lo que Material inserta el botón atrás al existir una ruta
previa.

### Barra de navegación con destinos duplicados (`UX-N2`)

Cuatro de los cinco elementos de la barra inferior apuntan a la misma ruta (`courts`), y
el cambio de pantalla usa `pushReplacementNamed`, que recrea la vista en cada toque. La
evidencia está en `courtly_bottom_navigation_bar.dart:14` y en `app_routes.dart:23`. La
recomendación es asignar cada destino a su pantalla real, o reducir la barra a los tabs
que realmente cumplen una función, y usar `IndexedStack` para conservar el estado. Este
punto queda documentado como mejora de diseño, ya que las pantallas destino todavía no
existen.

### Accesibilidad sin semántica (`AC-N1`)

La app no incluía ningún `Semantics` ni `semanticLabel`. Como consecuencia, las imágenes
de red y el rating por estrellas (`Text('★★★★★')`) resultan opacos para los lectores de
pantalla. La evidencia está en `court_detail_screen.dart:242` y en
`court_search_screen.dart:545`. La corrección añadió `semanticLabel` a las imágenes
informativas y semántica al rating.

### Texto que no escala con Dynamic Type (`AC-N2`)

Los tamaños de fuente fijos, combinados con valores de `height` menores a 1 y
contenedores de altura fija, recortan el texto cuando el usuario aumenta el tamaño de
letra del sistema. La evidencia está en `sign_in_screen.dart:207` y en
`court_detail_screen.dart:176`. La recomendación es evitar `height` menor a 1 en los
títulos grandes y reemplazar las alturas fijas por alturas mínimas flexibles.

### Contraste por debajo de WCAG AA (`PS-V1`)

Algunos textos en `white54` sobre fondo navy, las estrellas ámbar sobre tarjeta blanca y
los elementos no seleccionados de la barra inferior quedaban por debajo del ratio 4.5:1.
La evidencia está en `profile_screen.dart:270` y en `court_detail_screen.dart:245`. La
corrección subió la opacidad de los textos y oscureció el ámbar del rating.

### Localización escrita en el código (`LC-N1`)

Toda la interfaz usa textos en español incrustados en los widgets. No hay
`flutter_localizations`, `intl` ni `supportedLocales`. La evidencia está en
`courtly_app.dart:12` y en `pubspec.yaml:30`. La recomendación es incorporar
`flutter_localizations` con `intl` y extraer los textos a archivos ARB. Al tratarse de
un refactor amplio, se documenta como una fase aparte.

### Solo tema claro (`TH-N1`)

La aplicación define únicamente `lightTheme`, sin `darkTheme` ni `themeMode`, y conserva
colores escritos directamente fuera de `AppColors`. En modo oscuro del sistema la app se
ve igual que en modo claro. La evidencia está en `app_theme.dart:6` y en
`courtly_app.dart:15`. La recomendación es definir un `darkTheme`, usar
`themeMode: ThemeMode.system` y centralizar los colores en `AppColors`.

### CTA sin acción (`PS-V2`)

El botón "Reservar esta cancha" tenía `onPressed: () {}` vacío, por lo que al tocarlo no
ocurría nada y parecía una falla de la app. La evidencia está en
`court_detail_screen.dart:147`. La corrección hace que el botón dé feedback con el
mensaje "Reservas próximamente disponibles" mientras el flujo de reserva no esté listo.
</content>
