# TFM-Turismo-Inteligente
Sistema de recomendación turística basado en AC + CNN + Streamlit
🧠 Sistema de Recomendación Turística Inteligente
Basado en AC + CNN + Streamlit

Autora: Alejandra Otero Leyton

🌍 Descripción General

Este proyecto integra técnicas de análisis estadístico, machine learning y visión computacional para construir un sistema de recomendación turística personalizado, desarrollado como parte del Trabajo Fin de Máster en Data Science, Big Data & Business Analytics.

La solución combina:

Análisis de Correspondencias (AC) para identificar relaciones entre actividades turísticas y variables sociodemográficas.

Red Neuronal Convolucional (CNN) entrenada con el dataset UTKFace para predecir edades a partir de imágenes faciales.

Un sistema de recomendación basado en la edad estimada.

Una aplicación web interactiva construida en Streamlit.

🧩 Arquitectura del Proyecto

flowchart TD
   
    A[Base SITUR Valle] --> B[Procesamiento y limpieza de datos]
    B --> C[Análisis de Correspondencias]
    C --> D[Asignación de actividades por edad]
    
    E[UTKFace Dataset] --> F[Entrenamiento CNN]
    
    D --> G[Sistema de recomendación]
    F --> G
    
    G --> H[App Streamlit]

📊 Componentes del Proyecto
1️⃣ Procesamiento de Datos

Limpieza e integración de 46.000+ registros de turismo receptivo.

Selección de variables relevantes:

Género

Procedencia

Rango de edad

Actividades turísticas (31 categorías)

2️⃣ Análisis de Correspondencias

Ejecutado con FactoMineR (R)

Identifica que el rango de edad es la variable más informativa.

Agrupa actividades según cercanía euclidiana entre categorías.

Asignación final por grupos etarios:

| Rango de Edad | Actividades                                                   |
| ------------- | ------------------------------------------------------------- |
| 15–26         | y6, y8, y10, y13, y14, y22, y24, y27, y29                     |
| 27–38         | y7, y9, y15, y16, y17, y18, y19, y20, y21, y23, y25, y26, y30 |
| 39–50         | y1, y2, y3, y12, y28                                          |
| 51–62 y 63+   | y4, y5, y11, y31                                              |

3️⃣ Red Neuronal Convolucional (CNN)

Dataset: UTKFace (23.7K imágenes)

Arquitectura:

Conv2D (64 filtros)

Conv2D (128 filtros)

Dense 256 → Dense 128

Dropout(0.5)

Métrica final:
MAE: 7.84 años

4️⃣ Sistema de Recomendación

Combina:

Edad estimada por la CNN

Actividades asignadas por AC

Reglas de recomendación coordinadas entre ambos modelos

5️⃣ Aplicación Web (Streamlit)

Funcionalidades:

Subir o capturar foto

Predicción de edad en tiempo real

Recomendaciones automáticas

Conexiones a fuentes externas de información turística

⚠️ Sobre el Modelo .h5

El modelo entrenado (age_prediction_model.h5) no se incluye debido a restricciones de tamaño de GitHub (límite de 100 MB).

Para reproducirlo:

Ejecutar el notebook Tesis_Master.ipynb

El entrenamiento generará nuevamente el archivo .h5

🛠️ Tecnologías Utilizadas

Python (Pandas, NumPy, TensorFlow, OpenCV)

R (FactoMineR, ggplot2)

Streamlit

Ngrok

Kaggle API

Google Colab


    
