# Buenas Prácticas Móviles — Courtly

Revisión de las aplicaciones móviles de Courtly frente a las buenas prácticas de
Android (Material Design / Core App Quality) y iOS (Human Interface Guidelines),
tomando como referencia el formato del entregable **CubiPool Best Practices**.

El análisis cubre las dos apps de la organización que tienen interfaz móvil:

| App | Repositorio | Stack | Plataformas |
|-----|-------------|-------|-------------|
| Courtly (usuarios) | `courtly_mobile_app` | Flutter | iOS + Android |
| Courtly Coaches | `courtly_coaches_app` | Kotlin + Jetpack Compose (Material 3) | Android |

Los repos `backend`, `landing-page` y `mock-up` quedan fuera de alcance por no ser
interfaces móviles.

Documentos:

- [Courtly (Flutter) — Cumplimiento y puntos a mejorar](./courtly_mobile_app.md)
- [Courtly Coaches (Android) — Cumplimiento y puntos a mejorar](./courtly_coaches_app.md)
- [Cambios aplicados en el código](./cambios-aplicados.md)

## Cómo leer los códigos

Cada práctica lleva un código corto, igual que en el entregable de referencia.
La letra indica la categoría y el sufijo si es fortaleza (`B`/`V`, cumple) o mejora
(`N`, por corregir).

| Prefijo | Categoría |
|---------|-----------|
| `UX` | Usabilidad y navegación |
| `PS` / `TH` | Presentación visual, contraste y theming |
| `SC` | Seguridad |
| `AC` / `A11Y` | Accesibilidad |
| `ER` / `ERR` | Manejo de errores y validación |
| `RS` / `RES` | Responsive y safe areas |
| `PF` / `PERF` | Rendimiento |
| `PM` / `PERM` | Permisos |
| `LC` / `L10N` | Localización |

## Resumen general

Ambas apps comparten una base sólida: estados de feedback completos (loading, error,
vacío, éxito), validación de formularios, manejo de errores de red traducidos a
mensajes de usuario, y backend sobre HTTPS.

Los focos de mejora también son comunes a las dos: el token de sesión se guarda sin
cifrar, no hay modo oscuro, la localización está hardcodeada y faltan detalles de
accesibilidad. En la app Flutter se detectó además un bloqueante de release: el
permiso de INTERNET no estaba en el manifest principal.
</content>
</invoke>
