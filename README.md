# Segmentación de clientes E-comerce con K-Means
## Introducción 
Este proyecto nace de la necesidad de entender el comportamiento de compra de los usuarios dentro de una plataforma de comercio electrónico a partir de un conjunto de datos masivo de 3.5 millones de eventos. En lugar de analizar las transacciones de forma aislada, este análisis consolida la actividad para perfilar a cada cliente de manera única. Con esto, el negocio puede diseñar estrategias de marketing personalizadas, optimizar la asignación de recursos y mejorar la retención de usuarios según sus hábitos reales de consumo.

## Hallazgos
Antes de aplicar modelos de inteligencia artificial, se analizaron las tendencias temporales de las compras exitosas, descubriendo dos patrones críticos para la operación: 
**Concentración Semanal (Días Pico):** Al ordenar cronológicamente las transacciones, se descubrió que los lunes (**Monday**) y martes (**Tuesday**) registran el mayor volumen de actividad del negocio. Esto sugiere que las campañas publicitarias y las notificaciones push tienen un impacto significativamente mayor si se programan al inicio de la jornada laboral, en comparación con los fines de semana. 
**Comportamiento Horario (La Ola del Consumidor):** El análisis por hora reveló que la cima absoluta de ventas ocurre a las **11:00 a.m.** Existe también un repunte nocturno secundario a las **8:00 p.m.**, lo que permite al equipo técnico y de operaciones planificar ventanas de mantenimiento fuera de estos horarios para evitar caídas en momentos de alta facturación.
## Resultados del modelo
Tras estandarizar las métricas de frecuencia y monto acumulado con `StandardScaler` para balancear el modelo, el algoritmo K-Means agrupó automáticamente a la población en 4 segmentos estratégicos:

| Cluster | Perfil Estratégico | Compras Promedio | Gasto Promedio (USD) | Total de Clientes |
| :---: | :--- | :---: | :---: | :---: |
| 0 | Clientes Ocasionales | 4.6 | \$25.26 | 19,457 |
| 1 | Compradores de Alto Valor | 44.3 | \$217.06 | 647 |
| 2 | Clientes Fieles | 16.2 | \$75.88 | 5,463 |
| 3 | Mayoristas / Cuentas Clave | 124.7 | \$676.62 | 46 |

### Conclusiones del modelado:
1. **La Mayoría Silenciosa (Cluster 0):** Representa el mayor volumen de usuarios pero con el menor ticket. Requieren estrategias de reactivación y cupones de descuento para aumentar su frecuencia.
2. **La Columna Vertebral (Cluster 2):** Un grupo sólido de más de 5,000 clientes recurrentes que sostienen el flujo constante de la tienda.
3. **Las Ballenas del Negocio (Cluster 3):** Solo 46 cuentas generan un impacto masivo en la facturación debido a su comportamiento mayorista. Requieren atención preferencial y programas de fidelización exclusivos.