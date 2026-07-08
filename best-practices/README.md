# Buenas prácticas móviles de Courtly

El uso cotidiano de una aplicación depende tanto de sus funcionalidades como de la
forma en que respeta las convenciones de cada plataforma. Por ese motivo, se revisaron
las aplicaciones móviles de Courtly frente a las guías oficiales de Android (Material
Design y Core App Quality) y de iOS (Human Interface Guidelines). El análisis toma como
referencia el formato del entregable **CubiPool Best Practices**, que organiza cada
práctica con un código corto, una descripción y la evidencia correspondiente.

La revisión abarca las dos aplicaciones de la organización que cuentan con interfaz
móvil. Los repositorios `backend`, `landing-page` y `mock-up` quedaron fuera del
alcance por no corresponder a interfaces de usuario móviles.

| Aplicación | Repositorio | Tecnología | Plataformas |
|-----------|-------------|-----------|-------------|
| Courtly (usuarios) | `courtly_mobile_app` | Flutter | iOS y Android |
| Courtly Coaches | `courtly_coaches_app` | Kotlin con Jetpack Compose (Material 3) | Android |

Los documentos de este análisis son los siguientes:

- [Courtly (Flutter): cumplimiento y puntos a mejorar](./courtly_mobile_app.md)
- [Courtly Coaches (Android): cumplimiento y puntos a mejorar](./courtly_coaches_app.md)
- [Cambios aplicados en el código](./cambios-aplicados.md)

## Lectura de los códigos

Cada práctica se identifica con un código corto, igual que en el entregable de
referencia. La letra inicial señala la categoría y el sufijo indica si se trata de una
fortaleza (`B` o `V`, se cumple) o de una mejora pendiente (`N`, por corregir).

| Prefijo | Categoría |
|---------|-----------|
| `UX` | Usabilidad y navegación |
| `PS` y `TH` | Presentación visual, contraste y theming |
| `SC` | Seguridad |
| `AC` y `A11Y` | Accesibilidad |
| `ER` y `ERR` | Manejo de errores y validación |
| `RS` y `RES` | Responsive y safe areas |
| `PF` y `PERF` | Rendimiento |
| `PM` y `PERM` | Permisos |
| `LC` y `L10N` | Localización |

## Resumen general

Las dos aplicaciones parten de una base sólida. Ambas manejan de forma consistente los
estados de carga, error, vacío y éxito, validan sus formularios antes de enviar datos,
traducen los errores de red a mensajes comprensibles y se comunican con el backend
sobre HTTPS.

Los puntos por mejorar también coinciden en buena medida. En las dos apps el token de
sesión se guarda sin cifrar, no existe modo oscuro, los textos están escritos
directamente en el código sin soporte de localización y quedan detalles de
accesibilidad por cubrir. En la aplicación Flutter, además, se detectó un problema que
habría roto la app en producción: el permiso de INTERNET no estaba declarado en el
manifest principal.
</content>
