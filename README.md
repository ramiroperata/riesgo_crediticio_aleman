# Análisis de riesgo crediticio

Este proyecto utiliza un conjunto de datos sobre riesgo crediticio de Alemania para realizar un análisis exploratorio de datos (EDA), preprocesamiento, entrenamiento de modelos predictivos y evaluación de resultados. El objetivo principal es clasificar a los clientes en categorías de "Buen" o "Mal" riesgo crediticio basándose en características demográficas y financieras.

## Introducción

El riesgo crediticio es una de las principales preocupaciones para las instituciones financieras. Este proyecto aborda el problema utilizando técnicas de ciencia de datos para identificar patrones que permitan predecir la probabilidad de que un cliente incumpla con sus obligaciones de crédito.

---

## Análisis Exploratorio de Datos (EDA)

En el EDA se realizaron las siguientes tareas principales:

1. **Distribución de Variables:**
   - Se analizaron las distribuciones de variables continuas como la duración del crédito y el monto solicitado.
   - Variables categóricas como el propósito del crédito, género, y cuentas de ahorro se exploraron mediante gráficos de barras y tablas de frecuencia.

2. **Relaciones entre Variables:**
   - Se analizaron las correlaciones entre variables numéricas.
   - Se observaron diferencias significativas en características como "Monto del crédito" y "Duración" según la clasificación de riesgo.

3. **Hallazgos Clave:**
   - Clientes con mayores montos de crédito tienden a tener un mayor riesgo.
   - Las cuentas de ahorro y corrientes son fuertes indicadores del riesgo crediticio.
   - Algunos propósitos del crédito, como "negocios", están asociados con un menor riesgo relativo.

---

## Preprocesamiento

El conjunto de datos fue preprocesado siguiendo estas etapas:
1. Imputación de valores faltantes en las cuentas de ahorro y corriente.
2. Codificación de variables categóricas utilizando técnicas como `LabelEncoder` y `get_dummies`.
4. División del conjunto de datos en entrenamiento y prueba (80%-20%) con estratificación para preservar la proporción de clases.

---

## Modelos Entrenados

El modelo principal utilizado fue un **Random Forest Classifier**, seleccionado por su capacidad para manejar datos no lineales y su robustez frente a los outliers cuando se regula correctamente. 

### Optimización del Modelo
- Se realizaron ajustes en hiperparámetros como `max_depth`, `min_samples_split` y `n_estimators` para encontrar el balance óptimo entre bias y varianza.

### Métricas de Evaluación
- **Matriz de Confusión:** Para analizar la proporción de verdaderos positivos, falsos positivos, etc.
- **Reporte de Clasificación:** Precisión, recall y F1-score para ambas clases.
- **Curvas de Pérdida:** Visualización de la pérdida en función de la profundidad máxima de los árboles para prevenir sobreajuste.

---

## Resultados y Conclusiones

1. **Resultados del Modelo:**
   - Precisión en el conjunto de prueba: 78%.
   - Recall para la clase "Buen riesgo": 85%, indicando una buena capacidad para identificar clientes de bajo riesgo.
   - Recall para la clase "Mal riesgo": 70%, lo que sugiere margen de mejora en la detección de clientes de alto riesgo.

2. **Hallazgos Importantes:**
   - Las características más importantes para la predicción fueron:
     - Monto del crédito solicitado.
     - Duración del crédito.
     - Cuentas de ahorro y corriente.
   - Limitar la profundidad máxima del bosque aleatorio a 10 árboles redujo significativamente el sobreajuste sin comprometer demasiado el desempeño en el conjunto de prueba.

3. **Conclusiones:**
   - El modelo proporciona una herramienta útil para priorizar clientes en función de su riesgo crediticio.
   - Hay oportunidad de mejorar el rendimiento del modelo mediante la ingeniería de características o el uso de técnicas avanzadas como XGBoost o LightGBM.

---

## Este proyecto sigue en proceso, por lo que se agradece el feedback y recomendaciones

---

## Cómo Ejecutarlo

1. Clona este repositorio:
   ```bash
   git clone https://github.com/ramiroperata/riesgo_crediticio_aleman.git
   cd riesgo_crediticio_aleman

2. Ejecuta el notebook
