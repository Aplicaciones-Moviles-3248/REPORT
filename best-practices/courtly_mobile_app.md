# Courtly (Flutter) — Cumplimiento y puntos a mejorar

App de usuarios, construida en Flutter para iOS y Android. Arquitectura por
contextos (DDD). Se revisó `pubspec.yaml`, el tema, las rutas, la capa compartida,
todas las pantallas de los contextos con código, los manifests de Android y el
`Info.plist` de iOS.

## Cumplimiento

### Hit targets — `UX-B1` / `Hit Targets`
Los objetos táctiles principales cumplen el mínimo (44 pt en iOS, 48 dp en Android).
El botón primario global usa `minimumSize: Size(double.infinity, 52)`, el botón
central del bottom nav mide 58x58 y los `IconButton` usan el default de 48.
Evidencia: `lib/app/theme/app_theme.dart:26`, `lib/shared/presentation/widgets/courtly_bottom_navigation_bar.dart:62`.

### Feedback de acciones — `PS-V1`
Cobertura consistente de los cuatro estados: loading con `CircularProgressIndicator`,
error con botón de reintento, estado vacío dedicado y confirmación de éxito por
`SnackBar`. Además hay pull to refresh.
Evidencia: `payments_screen.dart:120,129,143`, `edit_profile_screen.dart:105`.

### Validación y manejo de errores — `ER-V1`
Todos los formularios usan `Form` con validators y todas las llamadas de red están
envueltas en `try/catch`, diferenciando fallos de conectividad de errores de negocio.
Evidencia: `sign_in_screen.dart:400`, `api_client.dart:151`.

### Tráfico HTTPS — `SC-N1` (parcial)
La base URL por defecto es HTTPS y no hay URLs `http://` en código productivo. iOS
mantiene App Transport Security por defecto (no hay excepciones en `Info.plist`).
Evidencia: `api_client.dart:15`.

### Responsive y safe areas — `RS-N1`
Uso sistemático de `SafeArea` y `ConstrainedBox(maxWidth: 430)` para acotar el ancho
en pantallas grandes; el bottom sheet respeta el teclado con `viewInsets.bottom`.
Evidencia: `sign_in_screen.dart:161`, `payments_screen.dart:467`.

### Rendimiento y estado — `PF-N1`
Uso extensivo de `const`, listas perezosas (`GridView.builder`) y `dispose()` de
todos los controllers.
Evidencia: `court_search_screen.dart:287`, `sign_in_screen.dart:146`.

## Puntos a mejorar

### Permiso INTERNET ausente en el manifest principal — `PM-N1` (bloqueante)
El permiso `INTERNET` solo estaba declarado en los manifests de `debug` y `profile`.
En un build **release** el merge no lo incluye y toda la red falla en producción.
Evidencia: `android/app/src/main/AndroidManifest.xml`.
Corrección: declarar `<uses-permission android:name="android.permission.INTERNET"/>`
en el manifest principal.

### Credenciales y token inseguros — `SC-N2` (alta prioridad)
Dos problemas: (a) el formulario de login venía con credenciales de prueba
precargadas en código; (b) el token de sesión se persistía en `SharedPreferences`,
que es texto plano en Android y no usa Keychain en iOS.
Evidencia: `sign_in_screen.dart:57`, `local_storage_service.dart:8`.
Corrección: quitar la precarga y migrar el token a `flutter_secure_storage`
(Keychain / Keystore), dejando `SharedPreferences` solo para datos no sensibles.

### Sin botón atrás en pantallas de detalle — `UX-N1`
`CourtDetailScreen`, `EditProfileScreen` y `PaymentsScreen` se abren con push pero
ningún `Scaffold` definía `AppBar`, así que no había botón de retorno ni título. En
iOS eso deja al usuario sin affordance de vuelta.
Evidencia: `court_detail_screen.dart:38`, `edit_profile_screen.dart:131`.
Corrección: agregar `AppBar` con título; Material inyecta el botón atrás al haber
ruta previa.

### Bottom nav con destinos duplicados — `UX-N2`
Cuatro de los cinco ítems del bottom nav llevan a la misma ruta (`courts`), y se usa
`pushReplacementNamed`, que recrea la pantalla en cada toque.
Evidencia: `courtly_bottom_navigation_bar.dart:14`, `app_routes.dart:23`.
Recomendación: mapear cada destino a su pantalla real (o reducir el nav a los tabs
funcionales) y usar `IndexedStack` para preservar estado. Queda documentado como
mejora de diseño porque las pantallas destino todavía no existen.

### Accesibilidad sin semántica — `AC-N1`
No había ningún `Semantics` ni `semanticLabel`. Las imágenes de red y el rating por
estrellas (`Text('★★★★★')`) son opacos para lectores de pantalla.
Evidencia: `court_detail_screen.dart:242`, `court_search_screen.dart:545`.
Corrección: agregar `semanticLabel` a las imágenes informativas y semántica al rating.

### Texto que no escala con Dynamic Type — `AC-N2`
Tamaños de fuente fijos con `height` menor a 1 y contenedores de altura fija provocan
recorte cuando el usuario sube el tamaño de texto del sistema.
Evidencia: `sign_in_screen.dart:207`, `court_detail_screen.dart:176`.
Recomendación: evitar `height < 1` en títulos grandes y usar altura mínima flexible
en lugar de fija.

### Contraste por debajo de WCAG AA — `PS-V1`
Textos en `white54` sobre navy, estrellas ámbar sobre tarjeta blanca e ítems no
seleccionados del bottom nav en `white54` quedan por debajo de 4.5:1.
Evidencia: `profile_screen.dart:270`, `court_detail_screen.dart:245`.
Corrección: subir la opacidad de los labels y usar un ámbar más oscuro para el rating.

### Localización hardcodeada — `LC-N1`
Toda la UI usa strings en español embebidos. No hay `flutter_localizations`, `intl`
ni `supportedLocales`.
Evidencia: `courtly_app.dart:12`, `pubspec.yaml:30`.
Recomendación: incorporar `flutter_localizations` + `intl`, extraer strings a ARB.
Refactor grande, se documenta como fase aparte.

### Solo tema claro — `TH-N1`
La app solo define `lightTheme`; no hay `darkTheme` ni `themeMode`, y hay colores
hardcodeados fuera de `AppColors`. En modo oscuro del sistema se ve igual.
Evidencia: `app_theme.dart:6`, `courtly_app.dart:15`.
Recomendación: definir `darkTheme` y `themeMode: ThemeMode.system`, consolidando los
literales de color en `AppColors`.

### CTA sin acción — `PS-V2`
El botón "Reservar esta cancha" tenía `onPressed: () {}` vacío: al tocarlo no pasaba
nada, aparentando un fallo.
Evidencia: `court_detail_screen.dart:147`.
Corrección: dar feedback ("Próximamente") mientras el flujo de reserva no esté listo.
</content>
