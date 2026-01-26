# 📊 Data Science – Predicción de Churn (Hackathon)

Este repositorio contiene el trabajo realizado por el equipo de **Data Science** durante la hackathon, enfocado en el análisis de datos y el desarrollo de un modelo de Machine Learning para la predicción de abandono de clientes (*churn*).

---

## 🎯 Objetivo
Analizar el comportamiento de los clientes y construir un modelo predictivo capaz de estimar la probabilidad de abandono a partir de variables demográficas, contractuales, de servicios y de facturación.

---

## 📌 Alcance del repositorio
Este repositorio documenta **exclusivamente** el trabajo correspondiente al área de **Data Science**.

Incluye:
- Análisis exploratorio de datos (EDA)
- Limpieza y preparación de variables
- Feature engineering
- Entrenamiento y evaluación del modelo
- Preparación del modelo para su integración con el backend

No incluye:
- Desarrollo de APIs
- Implementación de endpoints
- Desarrollo frontend
- Lógica de negocio o visualización en producción

---

## 🧠 Enfoque del modelo
- Problema de clasificación binaria: **Churn / No Churn**
- Algoritmo: **Regresión Logística**
- Balanceo de clases mediante `class_weight='balanced'`
- Optimización enfocada en **recall de la clase positiva (abandono)**
- Arquitectura basada en **Pipelines de Scikit-Learn**
- Preprocesamiento automático de variables numéricas y categóricas

---

## 🔌 Contrato de integración con Backend
El modelo recibe un **JSON de entrada** con variables del cliente previamente definidas.

Las siguientes variables **no forman parte del contrato de entrada** y se calculan internamente:
- `num_servicios`
- `antiguedad_años`

El contrato de entrada es validado antes de ejecutar la predicción para garantizar consistencia con el modelo entrenado.

El modelo se entrega:
- Entrenado
- Serializado (`joblib`)
- Listo para ser consumido por un servicio backend del proyecto

---

## 🗂️ Contenido del repositorio

### 📁 Datos
- `data.xlsx`  
  Dataset utilizado para el análisis exploratorio y el entrenamiento del modelo.

### 📓 Análisis y modelo
- `hackathon.ipynb`  
  Notebook principal que incluye:
  - EDA
  - Limpieza de datos
  - Feature engineering
  - Entrenamiento del modelo
  - Evaluación de métricas
  - Preparación del modelo para integración

### 🧠 Modelo entrenado
- `models/churn_model_v1.joblib`  
  Modelo final serializado listo para producción.

### 📐 Modelado y diagramas
- `modelo_churn.mwb` – Modelo físico de datos (MySQL Workbench)
- `Modelado_conceptual_churn.drawio` – Modelo conceptual del negocio
- `Diagrama_Flujo_Prediccion_Churn.drawio` – Flujo del proceso de predicción
- `Roadmap.png` – Roadmap del análisis de churn

---

## 🧪 Salida del modelo (ejemplo)

```json
{
  "abandono_cliente": true,
  "probabilidad_abandono": 0.742
}
```

---

## 🤝 Contexto

Este repositorio forma parte del trabajo colaborativo realizado durante la hackathon y documenta el proceso completo de análisis y modelado del churn desde la perspectiva de Data Science, dejando el modelo preparado para su integración con el backend del proyecto.

