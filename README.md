# TP2 - Minería de Datos  
## Modelos de regresión y clasificación

Este repositorio contiene el desarrollo del **Trabajo Práctico N°2** de la materia **Minería de Datos**.  
El objetivo del trabajo fue aplicar modelos supervisados sobre dos problemas diferentes: uno de regresión, orientado a estimar la variable `Profit`, y otro de clasificación, orientado a predecir la variable `Droga`.

## Integrantes
- Lara Onyskiw
- Sebastián Muñoz

## Contenido del trabajo

El trabajo se divide en dos partes principales.

### Parte A - Regresión

Se trabajó con el dataset `1000_Companies.csv`, correspondiente a información financiera de empresas.

A lo largo del notebook se desarrollan las siguientes etapas:

- **Limpieza y preprocesamiento de datos**
  - revisión de tipos de datos
  - detección de valores faltantes
  - revisión y eliminación de duplicados
  - análisis de outliers
  - codificación de variables categóricas
  - estandarización de variables numéricas
  - particiones 80/20 y 70/30

- **Análisis exploratorio**
  - distribución de variables numéricas
  - análisis de valores extremos
  - relación entre variables predictoras y `Profit`
  - matriz de correlación
  - análisis de `Profit` según `State`

- **Modelo de regresión**
  - árbol de decisión para regresión
  - comparación de hiperparámetros
  - evaluación con MAE, MSE y RMSE
  - visualización del árbol final

### Parte B - Clasificación

Se trabajó con el dataset `drugType.csv`, correspondiente a información de pacientes y tipos de droga indicados.

A lo largo del notebook se desarrollan las siguientes etapas:

- **Limpieza y preprocesamiento de datos**
  - revisión de tipos de datos
  - detección de valores faltantes
  - revisión de duplicados
  - análisis de distribución de clases
  - codificación de variables categóricas
  - estandarización de variables numéricas
  - particiones 80/20 y 70/30 con estratificación

- **Análisis exploratorio**
  - distribución de la variable objetivo `Droga`
  - análisis de variables numéricas
  - análisis de variables categóricas
  - cruces entre variables predictoras y `Droga`

- **Modelos de clasificación**
  - árbol de decisión
  - post-poda con `ccp_alpha`
  - Bayes Ingenuo
  - k vecinos más cercanos
  - comparación final de modelos

## Datasets

Se utilizaron los siguientes archivos:

- `1000_Companies.csv` → dataset utilizado para el problema de regresión.
- `drugType.csv` → dataset utilizado para el problema de clasificación.

Las variables principales del dataset de empresas fueron:

- `RyD_Spend`
- `Administration`
- `MarketingSpend`
- `State`
- `Profit`

La variable objetivo de esta parte fue:

- `Profit`

Las variables principales del dataset de drogas fueron:

- `Edad`
- `Sexo`
- `BP`
- `Colesterol`
- `Na_a_K`
- `Droga`

La variable objetivo de esta parte fue:

- `Droga`

## Estructura del repositorio

- `Regresion-Munoz-Onyskiw.ipynb` → notebook correspondiente a la Parte A.
- `Clasificacion-Muñoz-Onyskiw.ipynb` → notebook correspondiente a la Parte B.
- `1000_Companies.csv` → dataset de empresas.
- `drugType.csv` → dataset de drogas.
- `README.md` → descripción general del proyecto.
- `requirements.txt` → librerías necesarias para ejecutar los notebooks.

## Herramientas utilizadas

El trabajo fue realizado en Python, principalmente con:

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `graphviz`

## Requerimientos

Para instalar las librerías principales de Python, ejecutar:

```bash
pip install -r requirements.txt
```

El archivo requirements.txt contiene:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- graphviz

## Instalación de Graphviz

Para visualizar los árboles de decisión con export_graphviz y Source, no alcanza únicamente con instalar la librería de Python graphviz. También es necesario instalar Graphviz como programa del sistema.

Opción con pip

Instalar primero la librería de Python:

```bash
pip install graphviz
```

Luego instalar Graphviz en Windows:

```bash
winget install Graphviz.Graphviz
```

Después de la instalación, cerrar y volver a abrir Visual Studio Code o reiniciar el kernel del notebook.

Opción con Conda

Si se trabaja con Anaconda, se puede instalar con:
```bash
conda install -c conda-forge graphviz python-graphviz
```

Verificación de instalación

Para comprobar que Graphviz quedó correctamente instalado, ejecutar en la terminal:

```bash
dot -V
```

Si el comando devuelve la versión de Graphviz, la instalación fue exitosa.

En caso de que Python no encuentre el ejecutable, puede agregarse la ruta manualmente dentro del notebook:

```bash
import os

os.environ["PATH"] += os.pathsep + r"C:\Program Files\Graphviz\bin"
```

## Cómo ejecutar los notebooks
1. Clonar este repositorio o descargar los archivos.
2. Instalar los requerimientos indicados en requirements.txt.
3. Instalar Graphviz como programa del sistema si se desean visualizar los árboles de decisión.
4. Abrir los notebooks en Jupyter Notebook, JupyterLab o Visual Studio Code.
5. Ejecutar las celdas en orden.


## Resultados generales
De manera resumida, el trabajo permitió observar que:

- en el problema de regresión, RyD_Spend fue la variable con mayor peso para estimar Profit;
- el árbol de decisión de regresión logró buenos resultados luego de ajustar sus hiperparámetros;
- en el problema de clasificación, Na_a_K, BP y Colesterol mostraron una relación clara con el tipo de droga;
- el árbol de decisión fue el modelo de clasificación con mejor desempeño e interpretabilidad;
- Naive Bayes y k-NN obtuvieron resultados aceptables, aunque con más errores que el árbol de decisión;
- la poda permitió simplificar el árbol, pero en este caso redujo el desempeño del modelo final.


## Observaciones
Este repositorio tiene fines académicos y corresponde a una entrega universitaria.
Las decisiones metodológicas y las conclusiones fueron desarrolladas en función de la consigna de la materia y de los contenidos vistos en clase.


Materia: Minería de Datos
Año: 2026