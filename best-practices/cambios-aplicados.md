# Cambios aplicados en el código

Fixes aplicados a partir de la auditoría de buenas prácticas. Cada uno se commiteó
de forma atómica en su repositorio.

## Courtly (Flutter) — `courtly_mobile_app`

| Código | Cambio | Archivos |
|--------|--------|----------|
| `PM-N1` | Se declara el permiso `INTERNET` en el manifest principal (evita red rota en release) | `android/app/src/main/AndroidManifest.xml` |
| `SC-N2` | Se quitan las credenciales de prueba precargadas en el login | `sign_in_screen.dart` |
| `SC-N2` | El token de sesión pasa a `flutter_secure_storage` (Keychain / Keystore) | `local_storage_service.dart`, `pubspec.yaml` |
| `UX-N1` | Se agrega `AppBar` con botón atrás en detalle de cancha, editar perfil y pagos | `court_detail_screen.dart`, `edit_profile_screen.dart`, `payments_screen.dart` |
| `PS-V2` | El botón "Reservar esta cancha" ahora da feedback en vez de no hacer nada | `court_detail_screen.dart` |
| `AC-N1` | Etiquetas semánticas en imágenes y en el rating por estrellas | `court_search_screen.dart`, `profile_screen.dart`, `court_detail_screen.dart` |
| `PS-V1` | Se sube el contraste de labels, ítems del nav y estrellas | `profile_screen.dart`, `courtly_bottom_navigation_bar.dart`, `court_detail_screen.dart` |

## Courtly Coaches (Android) — `courtly_coaches_app`

| Código | Cambio | Archivos |
|--------|--------|----------|
| `SC-N2` | El token se cifra con `EncryptedSharedPreferences` (la dependencia ya estaba y no se usaba) | `SessionStorage.kt` |
| `SC-N3` | Nuevo `network_security_config.xml` con cleartext deshabilitado, referenciado en el manifest | `res/xml/network_security_config.xml`, `AndroidManifest.xml` |
| `L10N-V1` | `app_name` pasa a la marca "Courtly Coaches" | `res/values/strings.xml` |
| `PERF-N1` | La lista de disponibilidades se virtualiza con `LazyColumn` | `AvailabilityScreen.kt` |
| `PERF-N2` | Las dependencias del composable se memoizan con `remember` | `CoachAvailabilityScreen.kt` |
| `A11Y-V1` | `contentDescription` / `semantics` en el estado de disponibilidad y en iconos | `AvailabilityScreen.kt`, `CoachNavigation.kt` |
| `A11Y-B1` | Mínimo interactivo de 48 dp en tabs y bottom bar | `SignInScreen.kt`, `CourtlyCoachBottomBar.kt` |
| `RES-V1` | `statusBarsPadding` en el login para no dibujar bajo la barra de estado | `SignInScreen.kt` |
| `ERR-V2` | Validación de formato de fecha y hora antes de enviar disponibilidad | `AvailabilityViewModel.kt` |

## Mejoras documentadas pero no aplicadas (fases aparte)

Se dejan como recomendación por ser refactors amplios con riesgo de regresión, fuera
del margen de un fix puntual:

- **Localización completa** (`LC-N1` / `L10N-V1`): extraer todos los strings a ARB /
  `strings.xml` con soporte multi-idioma.
- **Modo oscuro** (`TH-N1` / `THEME-V1`): definir `darkTheme` / `darkColorScheme` y
  consolidar los colores hardcodeados.
- **Rediseño del bottom nav** (`UX-N2`, Flutter): mapear cada tab a su pantalla real,
  hoy varios destinos apuntan a la misma ruta.
- **Dynamic Type** (`AC-N2`, Flutter): reemplazar alturas fijas por mínimos flexibles
  para que el texto grande no se recorte.
</content>
