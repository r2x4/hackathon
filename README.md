# 📊 Proyecto Hackathon – Análisis y Predicción de Churn

Este repositorio contiene el trabajo del equipo de **Data Science** realizado durante la hackathon,
enfocado en el análisis y modelado del abandono de clientes (churn).

El proyecto aborda el análisis de datos, la construcción del modelo predictivo y la documentación
técnica necesaria para su comprensión e integración.

---

## 🎯 Objetivo

Analizar el comportamiento de los clientes y construir un modelo de Machine Learning capaz de estimar
la probabilidad de abandono (churn) a partir de variables demográficas, contractuales, de servicios y de facturación.

---

## 📌 Alcance del repositorio

Este repositorio documenta exclusivamente el trabajo correspondiente al área de **Data Science**.
Incluye análisis exploratorio, modelado predictivo y diagramas de soporte utilizados durante la hackathon.

---

## 🗂️ Contenido del repositorio

### Datos
- **data.xlsx**  
  Dataset utilizado para el análisis exploratorio y el entrenamiento del modelo de churn.

### Análisis y modelo
- **hackathon.ipynb**  
  Notebook principal del proyecto que incluye:
  - Análisis exploratorio de datos (EDA)
  - Limpieza y preparación de variables
  - Entrenamiento del modelo de Machine Learning
  - Evaluación de métricas y resultados

### Modelado de datos
- **modelo_churn.mwb**  
  Modelo físico de datos diseñado en MySQL Workbench.

- **Modelado_conceptual_churn.drawio**  
  Modelo conceptual que describe las entidades principales del negocio
  (Clientes, Servicios, Contratos y Pagos) y sus relaciones.

### Flujo de predicción
- **Diagrama_Flujo_Prediccion_Churn.drawio**  
  Diagrama de flujo que representa el proceso de predicción de churn,
  desde el envío de datos del cliente hasta la respuesta con la probabilidad de abandono.

### Roadmap de análisis
- **Roadmap.png**  
  Roadmap utilizado para guiar el análisis de churn, desde el objetivo del negocio,
  el entendimiento y modelado de datos, hasta la toma de decisiones.

---

## 🛠️ Instalación y Configuración
Este proyecto fue desarrollado en **Google Colab** y requiere un entorno de Python 3.x. A continuación, se detallan las librerías necesarias para el procesamiento de datos, análisis estadístico y entrenamiento del modelo de predicción de Churn.

### Librerías Utilizadas

Para garantizar que el flujo de trabajo sea reproducible, se utilizaron las siguientes dependencias:

* **Gestión del Sistema y Utilidades:**
    * `os`: Para interactuar con el sistema operativo y gestionar rutas de archivos.
    * `math`: Para realizar operaciones matemáticas y cálculos numéricos específicos.
    * `joblib`: Utilizada para la persistencia del modelo, permitiendo guardar y cargar el modelo entrenado de forma eficiente.
* **Manipulación y Análisis de Datos:**
    * `pandas` (as `pd`): Fundamental para la carga del archivo Excel y la manipulación de DataFrames.
    * `numpy` (as `np`): Soporte para el manejo de matrices y cálculos vectorizados.
* **Visualización de Datos:**
    * `matplotlib.pyplot` (as `plt`): Para la creación de gráficos base y personalización de figuras.
    * `seaborn` (as `sns`): Para la generación de visualizaciones estadísticas avanzadas y mapas de calor.
* **Machine Learning (Scikit-Learn):**
    * **Preprocesamiento:** `SimpleImputer` para tratar valores nulos, `OneHotEncoder` para variables categóricas y `StandardScaler` para normalizar los datos.
    * **Arquitectura:** `Pipeline` y `ColumnTransformer` para automatizar y organizar el flujo de transformación de datos.
    * **Modelado y Validación:** `LogisticRegression` para la clasificación, junto con `train_test_split` y `GridSearchCV` para la partición de datos y optimización del modelo.
    * **Métricas:** `classification_report` y `confusion_matrix` para evaluar el rendimiento de la predicción.
 
### Garga y Preparación de Datos 
Para que el notebook funcione correctamente, hay que cargar la fuente de datos siguiendo los siguientes pasos:
1. **Localización del archivo:** Asegurarse de contar con el archivo `data.xlsx` adjunto en este repositorio.
2. **Carga en Colab:**
   * Abre el panel lateral izquierdo en Google Colab (icono de carpeta).
   * Arrastra el archivo `data.xlsx` directamente al área de archivos.
   * El archivo debe quedar en la ruta raíz: `/content/data.xlsx`.

#### Instrucciones en el Código
El script está configurado para leer el archivo automáticamente usando la siguiente instrucción:
```python
data = pd.read_excel("/content/data.xlsx")
```
     

---

## 🧠 Enfoque del modelo

El modelo desarrollado prioriza la identificación de clientes con mayor riesgo de abandono (churn), poniendo especial énfasis en la capacidad predictiva sobre la clase positiva y manteniendo total coherencia con el contexto del problema de negocio.

Para lograr un modelo robusto y escalable, se implementó una arquitectura basada en **Pipelines de Scikit-Learn**, la cual se divide en tres etapas clave:

### 1. Preprocesamiento Automatizado
Utilizamos un `ColumnTransformer` para tratar de forma diferenciada cada tipo de dato:
* **Variables Numéricas:** Aplicamos `SimpleImputer` para gestionar valores ausentes y `StandardScaler` para normalizar las escalas, lo que facilita la convergencia del algoritmo.
* **Variables Categóricas:** Implementamos `OneHotEncoder` para transformar atributos de texto en variables numéricas procesables por el modelo.

### 2. Algoritmo de Clasificación
Se seleccionó la **Regresión Logística** (`LogisticRegression`) como motor de predicción. Este enfoque permite no solo obtener una clasificación binaria (Churn / No Churn), sino también interpretar la probabilidad de abandono y entender el impacto de cada variable en la decisión del cliente.

### 3. Estrategia de Evaluación
El rendimiento del modelo no se mide únicamente por su precisión general (*accuracy*), sino a través de una visión integral:
* **Matriz de Confusión:** Para monitorear falsos negativos (clientes que el modelo no detectó pero que sí abandonaron).
* **Reporte de Clasificación:** Análisis detallado de *Precision*, *Recall* y *F1-Score*, asegurando que el modelo sea realmente útil para los equipos de retención de clientes.
* **Optimización:** Uso de `GridSearchCV` para encontrar los hiperparámetros óptimos que maximicen el rendimiento del clasificador.

---

## 🤝 Contexto

Este repositorio forma parte del trabajo colaborativo realizado durante la hackathon
y documenta el proceso completo de análisis y modelado de churn desde la perspectiva de Data Science.

