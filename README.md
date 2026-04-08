# Análisis de Supervivencia en el Titanic

## Objetivo

El objetivo de este proyecto es analizar los factores asociados a la supervivencia de los pasajeros del Titanic mediante Análisis Exploratorio de Datos (EDA) y la construcción de modelos predictivos.

---

## Dataset

El dataset contiene información sobre los pasajeros del Titanic, incluyendo variables demográficas, socioeconómicas y relacionadas con el viaje.

Los datos se cargan desde un repositorio público para garantizar la reproducibilidad del análisis.

---

## Análisis realizado

El proyecto se desarrolló en tres etapas principales:

### 1. Análisis Exploratorio de Datos (EDA)

* Limpieza y preparación de datos
* Análisis univariado
* Análisis bivariado respecto a la variable objetivo (`Survived`)
* Identificación de patrones y generación de hipótesis

### 2. Ingeniería de variables

Se crearon nuevas variables para capturar mejor la estructura de los datos:

```python
df["FamilySize"] = df["SibSp"] + df["Parch"] 
```

Esta variable permitió modelar la dinámica familiar de los pasajeros.

---

### 3. Modelado y evaluación

Se entrenaron modelos de clasificación utilizando diferentes combinaciones de variables, evaluando su desempeño mediante **F1-score**.

Se implementó un enfoque modular para:

* Entrenamiento del modelo
* Evaluación
* Comparación de subconjuntos de variables

Además, se analizó la importancia de variables mediante métodos basados en modelos.

---

## Principales hallazgos

* **Sexo (`Sex`)** es la variable más influyente, con mayor tasa de supervivencia en mujeres.
* **Clase (`Pclass`)** presenta una relación clara con la supervivencia, reflejando diferencias socioeconómicas.
* **Tarifa (`Fare`)** aporta información más granular que la clase, capturando variaciones dentro de cada categoría.
* **Tamaño de familia (`FamilySize`)** muestra una relación no lineal: familias pequeñas tienen mayor probabilidad de sobrevivir.
* **Edad (`Age`)** no presenta diferencias claras en el EDA, pero aporta valor en combinación con otras variables dentro del modelo.
* **Puerto de embarque (`Embarked`)** tiene una contribución marginal, pero mejora ligeramente el desempeño del modelo al combinarse con otras variables.

---

## Resultados del modelo

Se evaluaron múltiples combinaciones de variables utilizando Random Forest:

* Mejor modelo: **F1-score ≈ 0.73**
* Variables utilizadas: combinación de sex, fare y age

---

## Notas metodológicas

* El EDA se utilizó para generar hipótesis, no para eliminar variables de forma definitiva.
* La selección de variables se validó mediante desempeño del modelo.
* Se utilizó **F1-score** como métrica principal para balancear precision y recall.
* La importancia de variables se interpretó como contribución al modelo, no como causalidad.

---

## Conclusión

El modelado confirma que variables como el sexo, la tarifa y la edad son determinantes clave, mientras que otras variables aportan valor adicional en combinación, aunque no sean evidentes en el análisis exploratorio.

---

## Trabajo futuro

* Optimización de hiperparámetros
* Ajuste del threshold de decisión
* Implementación de pipelines de procesamiento
* Despliegue del modelo mediante API (ej. con FastAPI)
* Comparación con otros modelos (Logistic Regression, Gradient Boosting)

