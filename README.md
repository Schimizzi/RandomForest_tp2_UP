# Predicción de Hábito de Fumar con RandomForest

Este proyecto utiliza un modelo de Machine Learning, específicamente un `RandomForestClassifier`, para predecir si una persona es fumadora o no, basándose en un conjunto de datos de salud y mediciones corporales.

El notebook (`RandomForestClassifier_tp2_v2_6.ipynb`) abarca todo el flujo de trabajo, desde el análisis exploratorio de los datos y la limpieza, hasta el entrenamiento, la optimización de hiperparámetros, el ajuste del umbral de decisión y la generación de predicciones sobre un nuevo conjunto de datos.

## 📋 Características

- **Análisis Exploratorio de Datos (EDA):** Visualizaciones para entender la distribución y correlación de las variables.
- **Preprocesamiento con `Pipeline`:** Uso de `ColumnTransformer` y `OneHotEncoder` para manejar eficientemente las variables categóricas.
- **Optimización de Modelo:** Búsqueda de los mejores hiperparámetros con `RandomizedSearchCV` para combatir el sobreajuste.
- **Análisis de Importancia de Variables:** Identificación de las características más influyentes para el modelo.
- **Ajuste del Umbral de Decisión:** Optimización del umbral de probabilidad para mejorar el **recall** de la clase "fumador".
- **Persistencia del Modelo:** El modelo final optimizado se guarda con `joblib` para su reutilización.
- **Gestión de Dependencias:** Uso de `requirements.txt` para una fácil y reproducible instalación del entorno.

## 🗂️ Estructura del Repositorio

```
.
├── datasets/
│   ├── smoking_prediction.xlsx           # Dataset para entrenamiento y prueba.
│   └── smoking_prediction_entrega.xlsx   # Nuevos datos para realizar predicciones.
│
├── modelo/
│   └── modelo_fumador_v2.6.joblib        # El modelo RandomForest entrenado y guardado.
│
├── prediction_result/
│   └── schimizzi_reporte_prediccion_fumadores.xlsx  # El archivo Excel final con las predicciones.
│
├── RandomForestClassifier_tp2_v2_6.ipynb   # Notebook principal con todo el análisis y modelado.
├── requirements.txt                        # Archivo con las dependencias del proyecto.
└── README.md                               # Este archivo.
```

## ⚙️ Requisitos y Entorno

Las dependencias de Python necesarias para este proyecto están listadas en el archivo `requirements.txt`.

Es **altamente recomendable** utilizar un entorno virtual para aislar las dependencias del proyecto y evitar conflictos con otros paquetes de tu sistema.

### ¿Cómo se creó `requirements.txt`?
Este archivo fue generado después de instalar todas las librerías necesarias dentro de un entorno virtual, usando el comando:
```bash
pip freeze > requirements.txt
```
Esto asegura que cualquier persona pueda recrear el entorno exacto en el que se desarrolló el proyecto.

## 🚀 Instalación y Uso

Sigue estos pasos para configurar y ejecutar el proyecto en tu máquina local.

1.  **Clona el repositorio:**
    ```bash
    git clone [https://github.com/Schimizzi/RandomForest_tp2_UP.git](https://github.com/Schimizzi/RandomForest_tp2_UP.git)
    cd RandomForest_tp2_UP
    ```

2.  **Crea y activa un entorno virtual (Recomendado):**
    ```bash
    # Crear el entorno
    python -m venv venv

    # Activarlo en Windows (CMD/PowerShell)
    .\venv\Scripts\activate

    # Activarlo en Mac/Linux
    source venv/bin/activate
    ```

3.  **Instala las dependencias:**
    Una vez dentro del entorno virtual activado, instala todas las librerías con un solo comando:
    ```bash
    pip install -r requirements.txt
    ```

4.  **Ejecuta el Notebook:**
    Abre y ejecuta las celdas del archivo `RandomForestClassifier_tp2_v2_6.ipynb` en un entorno como Jupyter Notebook o Google Colab para ver todo el proceso.

## 🧠 Flujo de Trabajo del Notebook

1.  **Análisis Exploratorio de Datos (EDA):** Se analizaron distribuciones y correlaciones para entender los datos y seleccionar las variables más relevantes.
2.  **Preprocesamiento y Pipeline:** Se construyó un `Pipeline` para automatizar la codificación de variables categóricas (`OneHotEncoder`) y el modelado.
3.  **Entrenamiento y Optimización:** Se utilizó `RandomizedSearchCV` para encontrar los mejores hiperparámetros y crear un modelo `RandomForest` robusto.
4.  **Ajuste del Umbral de Decisión:** Se ajustó el umbral de probabilidad a **0.45** para priorizar la correcta identificación de fumadores (mejorar `recall`).
5.  **Persistencia:** El modelo final fue guardado en `modelo/modelo_fumador_v2.6.joblib`.
6.  **Predicción:** El notebook final carga el modelo guardado, procesa un nuevo dataset y exporta las predicciones a `prediction_result/`.

## 📊 Resultados

El modelo final logra un buen balance entre la identificación de fumadores y no fumadores, con un **recall para la clase "fumador" de 0.84** en el conjunto de prueba, cumpliendo con el objetivo de priorizar la detección de esta clase.

## 👨‍💻 Autor

- **claudio** - [Schimizzi](https://github.com/Schimizzi)