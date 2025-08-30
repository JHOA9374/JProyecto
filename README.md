# 📡 Predicción de Distancia de Transmisión en Motes: Comparativa entre Modelos Superficiales y Profundos

## 📖 Descripción

Este proyecto implementa modelos de **Machine Learning supervisado** para predecir la **distancia de transmisión** de motes (nodos sensores inalámbricos), utilizando métricas de rendimiento como tasa de éxito, número de pérdidas, varianza y racha más larga de pérdidas consecutivas. Se comparan dos enfoques:

1. **Modelo superficial**: Random Forest Classifier.
2. **Modelo profundo**: Red neuronal utilizando TensorFlow/Keras.

El objetivo es evaluar cuál modelo se adapta mejor a los datos de métricas de transmisión y estimar la distancia con mayor precisión y robustez.

## 📊 Dataset

El dataset contiene las siguientes características:

- `success_rate`: Proporción de paquetes recibidos exitosamente.
- `loss_count`: Número de paquetes perdidos.
- `varianza`: Desviación estándar de las métricas de transmisión.
- `longest_loss_streak`: Racha más larga de pérdidas consecutivas.
- `distancia`: Distancia de transmisión (en metros), variable objetivo.

## ⚙️ Metodología

1. **Preprocesamiento de datos**: Selección de características relevantes y preparación del conjunto de datos.
2. **División de datos**: Separación en conjuntos de entrenamiento (60%), prueba (20%) y validación (20%).
3. **Entrenamiento de modelos**:
   - *Modelo superficial*: Random Forest con optimización de hiperparámetros usando GridSearchCV.
   - *Modelo profundo*: Red neuronal con capas densas, activación ReLU y optimización con Adam.
4. **Evaluación**:
   - Métricas: Accuracy, F1-score (macro y weighted).
   - Matriz de confusión.
   - Curvas de aprendizaje y pérdidas.

## 📈 Resultados



## 🛠️ Tecnologías utilizadas

- Python 3.x
- scikit-learn
- TensorFlow / Keras
- pandas
- numpy
- matplotlib
- seaborn

## 🚀 Instalación

Clonar el repositorio e instalar las dependencias:

```bash
git clone https://github.com/JHOA9374/JProyecto.git
cd JProyecto
pip install -r requirements.txt
