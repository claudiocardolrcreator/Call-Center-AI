# Operia

*Rendimiento de tu call center* (antes «CallCenter Intelligence AI»).

Aplicación web para analizar archivos Excel de call center: dashboard de KPI, ranking de operarios, análisis por equipos, comparación entre meses y revisión de la calidad de los datos.

> **Estado:** versión 1 (prototipo funcional en un solo archivo). Los datos se procesan **en el navegador** y no se envían a ningún servidor.

## Cómo usarla
1. Abre `index.html` en Chrome, Edge o Firefox (doble clic en el archivo descargado).
2. Pulsa **Importar Excel** y adjunta uno o varios archivos `.xlsx`, `.xls` o `.csv`.
3. Revisa la correspondencia de columnas y el mes; pulsa **Confirmar e importar**.
4. Consulta Dashboard, Ranking, Equipos, Comparar meses y Revisión de datos.

Para probar sin datos reales usa `ejemplos/demo_call_center_25_operarios.xlsx` (datos ficticios).

## Qué incluye
- Importación con detección automática de hojas, encabezados y columnas (sinónimos), mapeo manual, vista previa, duplicados, campos vacíos y formatos incorrectos.
- Dashboard con 10 KPI, comparación con el mes anterior y filtros (año, mes, equipo, supervisor, operario).
- Ranking por 7 criterios, top 10 / 10 que necesitan apoyo y ficha individual con comparación frente al equipo.
- Análisis por equipos y comparación entre meses (variación absoluta, % y puntos porcentuales).
- Controles cruzados entre hojas (resumen vs. detalle de ventas vs. actividad diaria) y ventas registradas vs. validadas.

## Planes
| | Gratis | Starter | Pro |
|---|---|---|---|
| Precio mensual | S/ 0 | S/ 99 | S/ 199 |
| Meses guardados | 1 | 6 | 24 |
| Operarios por mes | 30 | 100 | 1.000 |
| Ranking completo y fichas | — | ✓ | ✓ |
| Equipos y comparación de meses | — | ✓ | ✓ |
| Controles entre hojas | — | — | ✓ |

**Pagos:** pega el enlace de pago de cada plan (Mercado Pago, Culqi u otra pasarela) en la constante `PAYMENT_LINKS` de `index.html`. Mientras esté vacío, la página de pago indica que el pago en línea no está disponible. La activación del plan después de pagar todavía no es automática (requiere servidor y webhook de la pasarela); el botón "modo prueba" solo simula el plan en el navegador.

## Fórmulas principales
| KPI | Fórmula |
|---|---|
| Cumplimiento | Σ ventas ÷ Σ meta |
| Conversión | Σ ventas ÷ Σ llamadas contestadas (configurable: realizadas) |
| Tiempo promedio de atención | Promedio ponderado por llamadas contestadas |
| Calidad / Adherencia | Promedio de operarios (se muestran separadas de la productividad) |
| Variación de KPI en % | Diferencia en puntos porcentuales (pp) |

Detalle completo en [`docs/diseno-tecnico.md`](docs/diseno-tecnico.md).

## Limitaciones actuales
- Los datos y el plan se guardan solo en el navegador (localStorage); no hay cuentas ni empresas. Las restricciones por plan son de la interfaz y no son seguras hasta tener servidor.
- Exportación: botón "Copiar tabla para Excel". La descarga de Excel/PDF llegará en la versión completa.
- Usa SheetJS 0.18.5 desde CDN (versión antigua; en la versión completa se usará la actual).
- Pendiente (etapa 3): Analista IA, detección de anomalías, autenticación y gestión de empresas.

## Privacidad
No subas a este repositorio archivos con datos reales de operarios o clientes.
