# Reporte del Modelo Final

## Resumen Ejecutivo

En esta sección se presentará un resumen de los resultados obtenidos del modelo final. Es importante incluir los resultados de las métricas de evaluación y la interpretación de los mismos.

El modelo final seleccionado es un RandomForestClassifier, el cual mostró un rendimiento superior en comparación con otros modelos evaluados. Las métricas de evaluación obtenidas fueron:

- **Accuracy:** 0.778
- **F1 Score:** 0.157
- **Precision:** 0.258
- **Recall:** 0.113

## Descripción del Problema

En esta sección se describirá el problema que se buscó resolver con el modelo final. Se debe incluir una descripción detallada del problema, el contexto en el que se desarrolla, los objetivos que se persiguen y la justificación del modelo.

El objetivo del proyecto es predecir los retrasos en los vuelos utilizando datos históricos de vuelos. La precisión del modelo es crucial para mejorar la planificación y la gestión de los vuelos, reduciendo así los costos y mejorando la satisfacción del cliente.

## Descripción del Modelo

En esta sección se describirá el modelo final que se desarrolló para resolver el problema planteado. Se debe incluir una descripción detallada del modelo, la metodología utilizada y las técnicas empleadas.

El modelo final es un RandomForestClassifier. Se seleccionó este modelo debido a su capacidad para manejar grandes conjuntos de datos y su robustez frente a la multicolinealidad de las variables.

### Extracción de Características

Se implementaron varias técnicas de selección y extracción de características, incluyendo:

- **Análisis de Componentes Principales (PCA):** Para reducir la dimensionalidad de los datos.
- **Selección de características basada en la importancia:** Utilizando el modelo RandomForest para identificar las características más relevantes.

### Código de Modelamiento

```python
import os
import pandas as pd
from sklearn.ensemble import RandomForestClassifier
from sklearn.decomposition import PCA
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score, f1_score, precision_score, recall_score

# Establecer la ruta al archivo kaggle.json
kaggle_path = os.path.join(os.getcwd(), 'scripts/data_acquisition/.kaggle')
os.environ["KAGGLE_CONFIG_DIR"] = kaggle_path

# Verificar si el archivo kaggle.json existe
if not os.path.exists(os.path.join(kaggle_path, 'kaggle.json')):
    raise FileNotFoundError("El archivo kaggle.json no se encuentra en la carpeta .kaggle.")

# Descargar y descomprimir el dataset
dataset_path = './flight_delays'
os.makedirs(dataset_path, exist_ok=True)
os.system(f"kaggle datasets download -d robikscube/flight-delay-dataset-20182022 --unzip -p {dataset_path}")

# Cargar y preprocesar los datos
data_files = [os.path.join(dataset_path, file) for file in os.listdir(dataset_path) if file.endswith('.csv')]
data = pd.concat((pd.read_csv(file) for file in data_files), ignore_index=True)

# Preprocesamiento de datos
X = data.drop(columns=['Arr_Delayed', 'FlightDate'])
y = data['Arr_Delayed']

# Dividir los datos en conjuntos de entrenamiento y prueba
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Reducir la dimensionalidad con PCA
pca = PCA(n_components=3)
X_train_pca = pca.fit_transform(X_train)
X_test_pca = pca.transform(X_test)

# Entrenar el modelo
model_rf = RandomForestClassifier(random_state=42).fit(X_train_pca, y_train)

# Evaluar el modelo
y_pred = model_rf.predict(X_test_pca)
metrics = {
    "Accuracy": accuracy_score(y_test, y_pred),
    "F1 Score": f1_score(y_test, y_pred),
    "Precision": precision_score(y_test, y_pred),
    "Recall": recall_score(y_test, y_pred)
}

print(metrics)