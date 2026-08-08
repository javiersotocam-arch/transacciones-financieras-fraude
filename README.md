# Auditoría y Análisis de Transacciones Financieras

Análisis de un dataset de **13,3 millones de transacciones financieras**, centrado en la calidad de datos, el comportamiento de gasto de los clientes y la detección de patrones de fraude.

## Contexto de negocio

Un banco necesita entender cómo gastan sus clientes y dónde se concentra el riesgo de fraude, pero antes de sacar ninguna conclusión hace falta confiar en los datos: con más de 13 millones de registros, cualquier inconsistencia sin detectar puede distorsionar los resultados y llevar a decisiones de negocio equivocadas.

## Qué hace este proyecto

- **Auditoría de calidad de datos** a gran escala: verificación de integridad referencial entre las tres tablas (usuarios, tarjetas y transacciones), detección de valores nulos y su causa raíz, y documentación explícita de los casos no calculables en vez de ocultarlos.
- **Análisis de comportamiento de gasto**: por usuario, por categoría de comercio y por segmento de ingresos.
- **Análisis por tipo de tarjeta**: comparativas y relación entre antigüedad de la cuenta y actividad.
- **Análisis temporal**: evolución mensual y estacionalidad del gasto.
- **Detección de fraude**: comparativa de transacciones fraudulentas vs. legítimas, patrones por franja horaria y por categoría de comercio.
- **Exportación de resultados**: todas las tablas resumen se consolidan en un único Excel con una hoja por análisis.

## Un hallazgo destacado

Durante la auditoría de nulos, se detectó que una parte de los valores faltantes en `merchant_state` no eran errores de captura, sino transacciones **online** (que no tienen estado físico asociado) — evitando así descartar o imputar mal esos datos. El análisis de fraude también reveló una oportunidad concreta de negocio: una estrategia de activación temprana dirigida a clientes con tarjetas recién emitidas.

## Herramientas

- **Python** (pandas, numpy) para la carga, limpieza y análisis
- **Excel** para la consolidación final de resultados

## Cómo ejecutarlo

1. Descarga el dataset original desde [Financial Transactions Dataset: Analytics](https://www.kaggle.com/datasets/computingvictor/transactions-fraud-datasets) (Kaggle).
2. Coloca los archivos `users_data.csv`, `cards_data.csv`, `transactions_data.csv`, `mcc_codes.json` y `train_fraud_labels.json` dentro de una carpeta llamada `data/`, en el mismo directorio que el notebook.
3. Abre `financialtransaction.ipynb` en Jupyter y ejecuta las celdas en orden.

## Autor

Javier Sotoca — [portfolio completo](https://sites.google.com/view/javiersotoca/home)
