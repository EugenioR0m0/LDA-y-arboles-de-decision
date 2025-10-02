# LDA-y-arboles-de-decision

## Descripción
Este proyecto implementa distintas técnicas de aprendizaje supervisado para analizar un dataset previamente procesado sobre adicción al uso del teléfono. El flujo de trabajo incluyó la separación de datos, selección de variables, generación de modelos y evaluación de métricas.

## Flujo de trabajo

### 1. División de datos
- Se utilizó **StratifiedShuffleSplit** para separar los datos en entrenamiento (80%) y prueba (20%).
- Se validó que ambas clases estuvieran presentes en los subconjuntos y que se mantuviera un **balance de clases**.

### 2. Selección de variables con regresión logística
- Se ajustó un modelo de **regresión logística (GLM)** con todas las variables.
- Se identificaron las dos variables más relevantes mediante sus **p-values**:
  - `Daily_usage_hours`
  - `Time_on_social_media`

### 3. Linear Discriminant Analysis (LDA)
- Se entrenó un modelo de **LDA** con las variables seleccionadas.
- Se generó una gráfica mostrando la separación de clases.

### 4. Árbol de decisión con poda
- Se entrenó un **árbol de decisión** y se aplicó **poda por complejidad** con el valor óptimo de `ccp_alpha`.
- Se utilizó **K-Fold (k=10)** para la validación.
- Se visualizó el **árbol podado** y la **partición del espacio de variables**.

### 5. Evaluación de modelos
- Se calcularon métricas en el conjunto de prueba para **LDA** y el **árbol podado**:
  - Accuracy
  - Precision
  - Recall
  - F1-score
  - Matriz de confusión
- Ambos modelos mostraron resultados muy similares (~0.78 de accuracy).
- LDA presentó un mejor equilibrio en las métricas, mientras que el árbol destacó por su interpretabilidad.

## Conclusiones
- Se cumplió con todos los pasos solicitados: balance de clases, selección de variables, generación de modelos, optimización mediante validación cruzada y evaluación de métricas.  
- Los resultados muestran que tanto LDA como el árbol de decisión son adecuados, siendo LDA ligeramente superior en desempeño global, mientras que el árbol ofrece mayor interpretabilidad.

## Archivos
- [Notebook Jupyter (`.ipynb`)](LDA_Arboles_de_Decision.ipynb)  
- [Versión exportada a HTML](LDA_Arboles_de_Decision.html)  
- [Dataset utilizado](teen_phone_addiction_dataset.csv)  

## Requisitos
- Python 3.x
- Bibliotecas: `pandas`, `numpy`, `matplotlib`, `sklearn`, `statsmodels`

## Ejecución
1. Cargar el dataset limpio (`teen_phone_addiction_dataset.csv`).
2. Abrir y ejecutar el [notebook](proyecto.ipynb) paso a paso.
3. Revisar los resultados en el propio notebook o en la [versión HTML](proyecto.html).
