# Análisis de Datos para Clasificación de Tallas

Este repositorio contiene notebooks y scripts utilizados para analizar y visualizar datos relacionados con la clasificación de tallas y su relación con características como el peso, la altura y la edad de los usuarios. El análisis incluye pruebas estadísticas y visualizaciones desarrolladas en R y Python.

## Estructura del Repositorio

- `cleaned_final_test.csv`: Conjunto de datos limpio utilizado en los análisis. Contiene las siguientes columnas:
  - `weight`: Peso del usuario (kg).
  - `age`: Edad del usuario (años).
  - `height`: Altura del usuario (cm).
  - `size`: Talla codificada como número entero.
  - `size_label`: Etiqueta de la talla (ej. `S`, `M`, `L`).

- **Notebooks**:
  - `análisis_tallas_r.ipynb`: Notebook en R para realizar un análisis ANOVA y visualización de datos relacionados con las tallas y el peso.
  - `visualización_datos_python.ipynb`: Notebook en Python que explora los datos y genera gráficos adicionales.

## Origen de los Datos
Los datos utilizados en este análisis se obtuvieron originalmente del repositorio [Clothes Price Prediction](https://www.kaggle.com/datasets/mrsimple07/clothes-price-prediction) en Kaggle. Posteriormente, se limpiaron y procesaron para ajustarse a los requerimientos del análisis.

## Métodos Implementados

### 1. Análisis Estadístico (R)
- **Prueba ANOVA**: Para determinar si existen diferencias significativas en el peso entre las distintas tallas.
- **Prueba de Tukey**: Comparación post-hoc para identificar qué pares de tallas presentan diferencias significativas en el peso promedio.
- **Visualizaciones**:
  - Gráfico de densidad para mostrar la distribución del peso en cada talla.
  - Boxplot para ilustrar las diferencias en el peso según las tallas.

### 2. Exploración y Visualización (Python)
- Limpieza de datos y mapeo de tallas a etiquetas descriptivas.
- Gráficos interactivos para explorar la relación entre peso, altura y talla.
- Análisis descriptivo de las estadísticas básicas del conjunto de datos.

Al comienzo del análisis en Python se realizó lo siguiente:
```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Cargar datos
file_path = "cleaned_final_test.csv"
df = pd.read_csv(file_path)

# Resumen inicial
print(df.info())
print(df.describe())

# Visualización inicial
sns.pairplot(df, hue="size_label")
plt.show()
```

## Requisitos

### Dependencias en R
- `ggplot2`
- `dplyr`

### Dependencias en Python
- `pandas`
- `matplotlib`
- `seaborn`
- `numpy`

### Instalación
1. Clona este repositorio:
   ```bash
   git clone https://github.com/tu_usuario/analisis-tallas.git
   cd analisis-tallas
   ```
2. Asegúrate de tener R y Python instalados en tu máquina, junto con los paquetes necesarios.
3. Ejecuta los notebooks en tu entorno local (se recomienda usar Jupyter).

## Cómo Usar este Repositorio
1. Abre los notebooks en Jupyter o RStudio.
2. Ejecuta los scripts en orden para replicar los resultados y generar visualizaciones.
3. Ajusta los parámetros o prueba con tus propios datos para adaptarlo a tus necesidades.

## Resultados Clave
- Se encontró una relación significativa entre las tallas y el peso.
- El análisis ANOVA mostró diferencias estadísticas claras entre todas las tallas.
- Las visualizaciones respaldan los hallazgos estadísticos, destacando una progresión consistente en el peso promedio de `XXS` a `XXXL`.

## Contribuciones
¡Las contribuciones son bienvenidas! Si tienes ideas para mejorar el análisis o agregar nuevas funcionalidades, siéntete libre de abrir un *pull request* o iniciar un *issue*.

## Licencia
Este proyecto está bajo la licencia MIT. Consulta el archivo `LICENSE` para más detalles.

## Autor
Creado por Ivan Cervantes.
