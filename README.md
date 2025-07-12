# ML_Examen1_Intento1
Análisis de Calidad de Vinos
Este proyecto realiza un análisis exploratorio de datos (EDA) y benchmarking de modelos de clasificación para predecir la calidad del vino utilizando los datasets de vino tinto y vino blanco.

Problema
El objetivo es predecir la calidad del vino (una puntuación entre 0 y 10) basándose en sus propiedades fisicoquímicas. Se exploran y comparan diferentes modelos de clasificación para determinar cuál ofrece el mejor rendimiento.

Datos
El análisis se basa en dos datasets:

winequality-red.csv: Contiene datos sobre vinos tintos.
winequality-white.csv: Contiene datos sobre vinos blancos.
Ambos datasets incluyen variables como acidez fija, acidez volátil, ácido cítrico, azúcar residual, cloruros, dióxido de azufre libre, dióxido de azufre total, densidad, pH, sulfatos y alcohol, además de la calidad del vino.

Metodología
Carga y Exploración Inicial de Datos:

Carga de los datasets de vino tinto y blanco.
Revisión de la estructura básica y tipos de datos.
Identificación y tratamiento (eliminación) de valores atípicos en el dióxido de azufre total.
Verificación de valores nulos y duplicados.
Análisis Exploratorio de Datos (EDA):

Cálculo de estadísticas descriptivas (media, desviación estándar, mínimo, máximo, moda).
Visualizaciones univariadas (histogramas y boxplots) para entender la distribución de las variables numéricas.
Visualizaciones multivariadas (mapas de calor de correlación y gráficos de dispersión) para explorar las relaciones entre variables.
Preprocesamiento de Datos:

Separación de variables predictoras (X) y variable objetivo (y - calidad).
Escalado de características numéricas usando StandardScaler.
Codificación One-Hot de características categóricas (aunque en este caso solo se agregó la columna 'type' para el análisis combinado).
División de los datos en conjuntos de entrenamiento y prueba.
Implementación y Evaluación de Modelos de Clasificación:

Implementación de Pipelines para preprocesamiento y clasificación.
Entrenamiento y evaluación de los siguientes modelos:
Regresión Logística
K-Nearest Neighbors (KNN)
Evaluación del rendimiento utilizando métricas como accuracy_score y r2_score (aunque R2 es más común para regresión, se calculó aquí).
Uso de GridSearchCV para optimizar los hiperparámetros de Regresión Logística y KNN en datasets separados de vino tinto y blanco.
Evaluación detallada de los modelos optimizados utilizando classification_report y confusion_matrix para cada tipo de vino y para el dataset combinado.
Análisis Combinado de Datos:

Combinación de los datasets de vino tinto y blanco, añadiendo una columna 'type' para diferenciar.
Aplicación del mismo proceso de preprocesamiento y entrenamiento/evaluación de modelos (Regresión Logística y KNN) al dataset combinado.
Conclusiones
Basado en los resultados del análisis:

Los datasets originales no presentaban valores nulos ni duplicados significativos (después de eliminar duplicados identificados), lo que facilitó el preprocesamiento.
El EDA proporcionó información sobre la distribución y correlaciones de las variables.
Los modelos de Regresión Logística y KNN se implementaron y evaluaron tanto en datasets separados como en el dataset combinado.
La optimización de hiperparámetros con GridSearchCV se realizó para ambos modelos en los datasets separados.
Las métricas de evaluación (Accuracy, R2, Precision, Recall, F1-score) y las matrices de confusión se utilizaron para comparar el rendimiento de los modelos.
El análisis detallado de los informes de clasificación y las matrices de confusión (mostrados en las celdas correspondientes) permiten una comparación más profunda del rendimiento de cada modelo para predecir las diferentes clases de calidad del vino.

En general, los resultados de Accuracy y R2 sugieren que los modelos tienen un rendimiento moderado para esta tarea de clasificación, lo cual es común en problemas con distribución desigual de clases como la calidad del vino. El análisis de precisión, recall y F1-score por clase en los informes de clasificación es crucial para entender el rendimiento de los modelos en la predicción de cada nivel de calidad.
