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

Modelo Superficial (Random Forest)

Métricas simples (success_rate, loss_count, varianza, longest_loss_streak)

<img width="951" height="403" alt="image" src="https://github.com/user-attachments/assets/ed955958-432e-40ff-9b47-86e5201a36e9" />


- Accuracy (Validation): 0.500
- F1-score (macro): 0.500
- F1-score (weighted): 0.500
- Accuracy promedio CV: 0.767 ± 0.207

Métricas complejas (features derivadas o agregadas)

<img width="835" height="373" alt="image" src="https://github.com/user-attachments/assets/770e6b4c-6bda-416f-8131-06847922aed7" />


- Accuracy (Validation): 1.000
- F1-score (macro): 1.000
- F1-score (weighted): 1.000
- Accuracy promedio CV: 0.983 ± 0.033

Nota: Las métricas complejas mejoran significativamente el desempeño del modelo superficial, mostrando la importancia de una buena selección de features.

Modelo Profundo (Red Neuronal)

Métricas simples
<img width="953" height="393" alt="image" src="https://github.com/user-attachments/assets/10ae100c-c5c2-4a43-acd1-47ca519815e7" />

Clase | Precision | Recall | F1-score | Support
------|-----------|--------|----------|--------
0     | 0.50      | 0.56   | 0.53     | 9
1     | 0.50      | 0.44   | 0.47     | 9

- Accuracy (Validation): 0.50
- F1-score (macro): 0.50
- F1-score (weighted): 0.50

Métricas complejas
<img width="986" height="424" alt="image" src="https://github.com/user-attachments/assets/840ab39a-a27e-4242-ab1e-1429bd189673" />

- Accuracy (Validation): 1.00
- F1-score (macro): 1.00
- F1-score (weighted): 1.00

Nota: Al igual que en el modelo superficial, las métricas complejas aumentan drásticamente el rendimiento del modelo profundo, alcanzando predicciones perfectas en los datos de validación.

Conclusión Comparativa

- Ambos modelos dependen fuertemente de la calidad y complejidad de las features.
- Con métricas simples, el desempeño es limitado (accuracy ~0.5).
- Con métricas complejas, se alcanza accuracy perfecto (1.0).
- El modelo profundo puede escalar mejor a datasets más grandes o ruidosos, aunque ambos muestran un comportamiento similar frente a la complejida


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
