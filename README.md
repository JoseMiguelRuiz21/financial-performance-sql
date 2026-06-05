# 📊 Análisis de Desempeño Financiero y Calidad de Datos con SQL

Este proyecto realiza una consolidación de datos y un análisis financiero profundo utilizando **SQL avanzado** sobre un conjunto de datos globales de ventas, catálogos de productos, territorios y presupuestos de marketing. 

El objetivo principal es responder a la dirección financiera cuántos ingresos se generan por país y qué tan rentable es cada mercado cuando se consideran los gastos de campañas publicitarias.

---

## 🛠️ Estructura del Análisis Estadístico y ETL

El desarrollo del proyecto se dividió en tres etapas críticas mediante consultas relacionales:

1. **Limpieza e Integración:** Conexión de tablas de ventas, productos y territorios mediante operaciones `JOIN`. Se implementó el control de valores nulos con `COALESCE` para asegurar la precisión en las columnas calculadas de `ingreso_total` y `costo_total`.
2. **Cálculo de KPIs de Negocio:** Agrupación y ordenamiento de datos por mercado para obtener métricas financieras clave:
   * **Beneficio Bruto:** Ganancia real tras cubrir costos directos.
   * **Margen %:** Eficiencia de las ventas directas.
   * **ROI %:** Retorno neto sobre la inversión en marketing personalizado.
3. **Auditoría de Calidad de Datos (QA):** Implementación de pruebas de integridad para detectar nulos en llaves primarias (`numero_pedido`, `clave_producto`) y registros inválidos (cantidades o precios menores o iguales a cero).

---

## 📈 Resumen Ejecutivo e Insights Financieros

A partir de la consulta final consolidada, se extrajeron las siguientes conclusiones estratégicas para la toma de decisiones:

| País | Ingresos | Costos | Costo Campañas | Beneficio Bruto | Margen % | ROI % |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| United States | $3,353,939.92 | $1,899,471.33 | $1,920,000.00 | $1,454,468.60 | 43.37% | **75.75%** |
| Australia | $2,532,003.49 | $1,474,958.18 | $2,150,400.00 | $1,057,045.31 | 41.75% | **49.16%** |
| United Kingdom | $1,189,636.78 | $681,508.55 | $2,304,000.00 | $508,128.24 | 42.71% | **22.05%** |
| Germany | $1,071,460.42 | $611,295.36 | $2,265,600.00 | $460,165.06 | 42.95% | **20.31%** |
| France | $924,316.93 | $527,797.14 | $2,208,000.00 | $396,519.79 | 42.90% | **17.96%** |
| Canada | $710,205.18 | $392,325.91 | $1,824,000.00 | $317,879.27 | 44.76% | **17.43%** |

### 🔍 Hallazgos Clave:
* **Eficiencia en United States:** Es el mercado más sólido. No solo genera el mayor volumen de ingresos, sino que registra un ROI sobresaliente del **75.75%**, lo que demuestra una respuesta sumamente eficiente del consumidor a las campañas locales.
* **Desgaste Publicitario en Australia:** Aunque retiene un excelente margen operativo en ventas directas (41.75%), el costo de sus campañas de marketing es sumamente agresivo en comparación con su beneficio, reduciendo su rentabilidad neta a un ROI del **49.16%**.
* **Micro-Mercados Estables:** Países como Canada muestran el margen de ventas más alto del catálogo (44.76%), sugiriendo que, aunque el mercado es pequeño en volumen, la estructura de costos directos es sumamente saludable.

### 💡 Recomendaciones de Negocio:
1. **Redistribución de Presupuesto:** Incrementar la inversión publicitaria en United States para capitalizar su alto retorno financiero, maximizando el flujo de caja global.
2. **Optimización en Australia y Europa:** Evaluar la efectividad y los canales de las campañas de marketing en Australia y United Kingdom para reducir el gasto publicitario excesivo sin comprometer el volumen de ventas actual.

---

## 🛠️ Tecnologías Utilizadas
* **SQL (PostgreSQL / MySQL nativo)**
* **Funciones de Agregación e Integridad:** `SUM`, `COUNT`, `COALESCE`, `CASE WHEN`
* **Operaciones Relacionales:** `LEFT JOIN`, `INNER JOIN`, `GROUP BY`, `ORDER BY`
