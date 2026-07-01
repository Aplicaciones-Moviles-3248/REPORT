# Cambios aplicados en el código

A partir de la auditoría de buenas prácticas se aplicaron los cambios que se describen a
continuación. Cada uno se registró en su repositorio como un commit independiente, de
modo que el historial mantiene una relación clara entre el hallazgo y su corrección.

## Courtly (Flutter): `courtly_mobile_app`

| Código | Cambio | Archivos |
|--------|--------|----------|
| `PM-N1` | Se declara el permiso `INTERNET` en el manifest principal, con lo que se evita que la red falle en release | `android/app/src/main/AndroidManifest.xml` |
| `SC-N2` | Se retiran las credenciales de prueba precargadas en el login | `sign_in_screen.dart` |
| `SC-N2` | El token de sesión pasa a `flutter_secure_storage`, apoyado en Keychain y Keystore | `local_storage_service.dart`, `pubspec.yaml` |
| `UX-N1` | Se agrega un `AppBar` con botón atrás en las pantallas de detalle de cancha, edición de perfil y pagos | `court_detail_screen.dart`, `edit_profile_screen.dart`, `payments_screen.dart` |
| `PS-V2` | El botón "Reservar esta cancha" ahora da feedback en lugar de no responder | `court_detail_screen.dart` |
| `AC-N1` | Se añaden etiquetas semánticas a las imágenes y al rating por estrellas | `court_search_screen.dart`, `profile_screen.dart`, `court_detail_screen.dart` |
| `PS-V1` | Se mejora el contraste de los textos, los elementos de la barra inferior y las estrellas | `profile_screen.dart`, `courtly_bottom_navigation_bar.dart`, `court_detail_screen.dart` |

## Courtly Coaches (Android): `courtly_coaches_app`

| Código | Cambio | Archivos |
|--------|--------|----------|
| `SC-N2` | El token se cifra con `EncryptedSharedPreferences`, usando la dependencia que ya estaba declarada | `SessionStorage.kt` |
| `SC-N3` | Se crea `network_security_config.xml` con el tráfico en texto plano deshabilitado y se enlaza desde el manifest | `res/xml/network_security_config.xml`, `AndroidManifest.xml` |
| `L10N-V1` | `app_name` pasa a la marca "Courtly Coaches" | `res/values/strings.xml` |
| `PERF-N1` | La lista de disponibilidades se virtualiza con `LazyColumn` | `AvailabilityScreen.kt` |
| `PERF-N2` | Las dependencias del composable se memorizan con `remember` | `CoachAvailabilityScreen.kt` |
| `A11Y-V1` | Se añade `contentDescription` y semántica al estado de disponibilidad y a los iconos | `AvailabilityScreen.kt`, `CoachNavigation.kt` |
| `A11Y-B1` | Se garantiza el mínimo interactivo de 48 dp en los tabs y en la barra inferior | `SignInScreen.kt`, `CourtlyCoachBottomBar.kt` |
| `RES-V1` | Se aplica `statusBarsPadding` en el login para no dibujar debajo de la barra de estado | `SignInScreen.kt` |
| `ERR-V2` | Se valida el formato de la fecha y la hora antes de enviar la disponibilidad | `AvailabilityViewModel.kt` |

## Mejoras documentadas y no aplicadas

Los siguientes puntos se dejan como recomendación porque implican refactors amplios, con
riesgo de introducir regresiones, que exceden el margen de una corrección puntual.

- Localización completa (`LC-N1` y `L10N-V1`): extraer todos los textos a archivos ARB o
  a `strings.xml` con soporte de varios idiomas.
- Modo oscuro (`TH-N1` y `THEME-V1`): definir el tema oscuro y centralizar los colores
  que hoy están escritos directamente en el código.
- Rediseño de la barra de navegación (`UX-N2`, en la app Flutter): asignar cada tab a su
  pantalla real, ya que varios destinos apuntan hoy a la misma ruta.
- Soporte de Dynamic Type (`AC-N2`, en la app Flutter): reemplazar las alturas fijas por
  mínimos flexibles para que el texto grande no se recorte.
</content>
