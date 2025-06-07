# Segmentación de Clientes con K-Means

Este proyecto en Jupyter Notebook realiza una segmentación de clientes de una empresa de tarjetas de crédito utilizando el algoritmo de *K-Means Clustering*, con base en su comportamiento de compra en centros comerciales. El objetivo es identificar diferentes tipos de tarjetahabientes y definir estrategias de marketing personalizadas para cada grupo.

Datos tomados de [Kaggle](https://www.kaggle.com/datasets/alifarahmandfar/customer-segmentation) 

## Caso de Negocio

Una empresa desea comprender mejor a sus clientes mediante la segmentación basada en su historial de uso de tarjetas de crédito. A continuación se muestra una descripción de los atributos del conjunto de datos:

| Atributo | Descripción |
| --- | --- |
| `CUST_ID` | Identificador del tarjetahabiente |
| `BALANCE` | Promedio mensual del saldo |
| `BALANCE_FREQUENCY` | Frecuencia con la que se actualizó el saldo en los últimos 12 meses |
| `PURCHASES` | Monto total de compras en los últimos 12 meses |
| `ONEOFF_PURCHASES` | Monto total de compras puntuales |
| `INSTALLMENTS_PURCHASES` | Monto total de compras a plazos |
| `CASH_ADVANCE` | Monto total de avances de efectivo |
| `PURCHASES_FREQUENCY` | Frecuencia de compras (meses con al menos una compra) |
| `ONEOFF_PURCHASES_FREQUENCY` | Frecuencia de compras puntuales |
| `PURCHASES_INSTALLMENTS_FREQUENCY` | Frecuencia de compras a plazos |
| `CASH_ADVANCE_FREQUENCY` | Frecuencia de avances de efectivo |
| `CASH_ADVANCE_TRX` | Monto promedio por transacción de avance de efectivo |
| `PURCHASES_TRX` | Monto promedio por transacción de compra |
| `CREDIT_LIMIT` | Límite de crédito |
| `PAYMENTS` | Pagos realizados durante el periodo |
| `MINIMUM_PAYMENTS` | Pagos mínimos requeridos durante el periodo |
| `PRC_FULL_PAYMENT` | Porcentaje de meses en los que se pagó el estado de cuenta completo |
| `TENURE` | Antigüedad del cliente (en meses) |

## Flujo de Trabajo

### 1. Análisis Exploratorio de Datos (EDA)
- Se verificó la existencia de valores duplicados y datos faltantes.
- Se utilizó la clase `ProfileReport` de la librería `ydata_profiling` para generar un análisis exploratorio automatizado.

**Hallazgos clave del EDA:**

- `CUST_ID` es un identificador único y se eliminará ya que no aporta valor analítico.
- `TENURE` solo tiene 7 valores únicos (de 6 a 12 meses), lo cual puede indicar una decisión de negocio sobre el período analizado.
- Muchas variables presentan distribuciones multimodales, lo que sugiere la existencia de subgrupos.
- Existen correlaciones fuertes entre varias variables, por lo que sería recomendable aplicar una técnica de reducción de dimensionalidad.
- Los gráficos de interacción como *Balance vs Purchase* muestran patrones de agrupamiento.

### 2. Preprocesamiento y Modelado
- Se creó un pipeline con imputación de valores nulos y escalamiento de variables.
- Se aplicó el algoritmo de K-Means para segmentar a los clientes.
- Se utilizó el método del codo (*elbow method*) y el análisis de *silhouette* para determinar el número óptimo de clusters.

### 3. Análisis de Resultados
Se entrenó el modelo final y se generaron diagramas de caja (boxplots) para visualizar las diferencias entre clusters.

## Hallazgos Finales

- **Cluster 0 (3284 clientes):**  
  Clientes recientes, segundo balance más bajo y baja frecuencia de actualización. Prefieren compras puntuales (`ONEOFF_PURCHASES`) y casi no usan avances de efectivo. Tienen el porcentaje más alto de pago completo (`PRC_FULL_PAYMENT`).

- **Cluster 1 (3481 clientes):**  
  Segundo balance más alto y la frecuencia más alta de actualización. Realizan muchas compras, especialmente a plazos. Son los más activos en términos de compras y avances de efectivo.

- **Cluster 2 (1247 clientes):**  
  Tienen el balance promedio más alto, pero muy baja frecuencia de uso, bajo límite de crédito y pocas compras.

- **Cluster 3 (938 clientes):**  
  Menor balance y frecuencia de compras. Son los clientes más antiguos, con el límite de crédito más alto y alto uso de avances de efectivo. También tienen el segundo porcentaje más alto de pago completo.
