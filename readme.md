# Clasificación de imágenes MRI cerebrales mediante redes neuronales convolucionales (CNN)

## 1. Descripción del proyecto

Este proyecto busca desarrollar un modelo basado en redes neuronales convolucionales (CNN) para clasificar imágenes bidimensionales de resonancia magnética (MRI) en cuatro categorías: glioma, meningioma, tumor de hipófisis (pituitary) y tejido sano (healthy).

En lugar de procesar volúmenes tridimensionales completos, se utilizan imágenes individuales extraídas de las resonancias magnéticas. Esta estrategia reduce la complejidad computacional y permite aplicar técnicas de aprendizaje profundo para identificar patrones visuales asociados a las categorías del conjunto de datos.

El proyecto comprende la preparación de las imágenes, la división de los datos en conjuntos de entrenamiento, validación y prueba, el desarrollo de una arquitectura CNN y la evaluación de su desempeño mediante métricas de clasificación.

**Nota:** este proyecto tiene fines académicos y de investigación. Sus resultados no deben utilizarse como sustituto de una evaluación o diagnóstico médico profesional.

## 2. Conjunto de datos

El conjunto de datos contiene 7.023 imágenes MRI distribuidas en cuatro clases:

- `glioma`: imágenes clasificadas como glioma.
- `healthy`: imágenes clasificadas como tejido sano.
- `meningioma`: imágenes clasificadas como meningioma.
- `pituitary`: imágenes clasificadas como tumor de hipófisis.

### Descargar los datos

El conjunto de datos está disponible en Kaggle:

[Brain Tumor MRI Scans, descargar dataset](https://www.kaggle.com/datasets/rm1000/brain-tumor-mri-scans?resource=download)

Pasos para descargarlo:

1. Ingresa al enlace de Kaggle e inicia sesión si es necesario.
2. Descarga el conjunto de datos.
3. Identifica el archivo comprimido que contiene las imágenes.
4. Coloca el archivo dentro de la carpeta `data` del proyecto y renómbralo como `data.zip`.

Verifica las condiciones de uso y distribución indicadas por el autor del conjunto de datos.

## 3. Estructura de archivos

Para ejecutar el código correctamente, conserva la siguiente estructura. La carpeta raíz puede tener cualquier nombre.

```text
nombre-del-proyecto/
├── data/
│   └── data.zip
├── notebooks/
│   └── 2026-10-22_CNN.ipynb
├── results/
└── README.md
```

Las carpetas tienen las siguientes funciones:

- **`data/`**: contiene el archivo comprimido original `data.zip`.
- **`notebooks/`**: contiene el notebook de Jupyter con el código del proyecto.
- **`results/`**: almacena los resultados generados, como reportes de clasificación.
- **`README.md`**: documenta el proyecto y explica cómo ejecutarlo.

### Extracción de las imágenes

El código busca automáticamente la carpeta raíz del proyecto. Si no existe `data/mri_images/`, crea esta carpeta y extrae allí el contenido de `data.zip`.

Después de la extracción, la estructura esperada es:

```text
data/
├── data.zip
└── mri_images/
    ├── glioma/
    ├── healthy/
    ├── meningioma/
    └── pituitary/
```

Cada carpeta debe contener las imágenes correspondientes a su clase. Los nombres deben coincidir con los definidos en la lista `CLASES` del notebook.

**Importante:** el archivo ZIP debe tener una estructura compatible con el código de extracción, de modo que las cuatro carpetas de clases queden directamente dentro de `mri_images/`. Si el ZIP incluye una carpeta adicional que contiene las cuatro clases, será necesario adaptar la extracción.

No es necesario crear manualmente `mri_images/` cuando se utiliza el bloque de configuración que realiza la extracción automática.

## 4. Requisitos y ejecución

Se necesita Python, Jupyter Notebook y las bibliotecas utilizadas por el proyecto, entre ellas:

- TensorFlow
- NumPy
- Matplotlib
- Pillow
- scikit-learn

Para ejecutar el proyecto:

1. Descarga o clona el repositorio.
2. Descarga el dataset de Kaggle y coloca el archivo como `data/data.zip`.
3. Instala las dependencias necesarias en tu entorno de Python.
4. Abre y ejecuta el notebook ubicado en `notebooks/`.
5. Verifica que se encuentren las cuatro clases y que las imágenes se carguen correctamente.
6. Ejecuta las celdas de preparación, entrenamiento y evaluación.
7. Consulta los resultados guardados en `results/`.

El código utiliza rutas relativas y una búsqueda automática de la raíz del proyecto para evitar depender de rutas absolutas específicas de cada computador. Para que funcione, conserva la estructura de carpetas descrita anteriormente.

## 5. Objetivo

Desarrollar y evaluar un modelo CNN capaz de clasificar imágenes bidimensionales de MRI en una de cuatro categorías, utilizando técnicas de aprendizaje profundo y métricas apropiadas para evaluar su desempeño.

## 6. Actividades del proyecto

1. Preparar y explorar las imágenes del conjunto de datos.
2. Construir un pipeline de carga y preprocesamiento de imágenes.
3. Dividir los datos en conjuntos de entrenamiento, validación y prueba.
4. Diseñar y entrenar una arquitectura CNN.
5. Evaluar el modelo mediante métricas como accuracy, precisión, recall y F1-score.
6. Analizar los resultados y las limitaciones del modelo.

