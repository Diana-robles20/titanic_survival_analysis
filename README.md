# Análisis de Supervivencia en el Titanic

## Objetivo

El objetivo de este proyecto es realizar un Análisis Exploratorio de Datos (EDA) sobre el dataset del Titanic para identificar los factores más relevantes asociados a la supervivencia de los pasajeros.

---

## Dataset

El dataset contiene información sobre los pasajeros del Titanic.

Los datos se cargan directamente desde un repositorio público de GitHub para garantizar la reproducibilidad del análisis.

---

## Análisis realizado

El análisis incluye:

* Limpieza y preparación de datos
* Análisis univariado
* Análisis bivariado en relación con la variable objetivo (`Survived`)
* Identificación de variables relevantes
* Ingeniería de variables
---

## Principales hallazgos

* **Sexo** es una de las variables más influyentes, con una tasa de supervivencia significativamente mayor en mujeres.
* **Clase (Pclass)** muestra una relación clara con la supervivencia, reflejando el impacto del nivel socioeconómico.
* **Tarifa (Fare)** aporta mayor detalle que la clase, ya que captura variaciones dentro de cada categoría y sugiere la existencia de subgrupos.
* **Tamaño de familia** (combinación de `SibSp` y `Parch`) presenta una relación no lineal: familias pequeñas tienen mayor probabilidad de sobrevivir, mientras que pasajeros solos o en grupos grandes tienen menor probabilidad.
* **Edad (Age)** no presenta diferencias significativas en la tasa de supervivencia entre grupos.

---

## Ingeniería de variables

Se creó una nueva variable para representar mejor la estructura familiar:

```python
df["FamilySize"] = df["SibSp"] + df["Parch"] 
```

Esta variable permite capturar patrones relacionados con el tamaño del grupo del pasajero.

---

## Notas metodológicas

* Se utilizaron proporciones y visualizaciones en lugar de correlación de Pearson para variables categóricas y relaciones no lineales.
* El objetivo del EDA es explorar los datos y generar hipótesis, no validar relaciones causales.

---

## Conclusión

La supervivencia en el Titanic estuvo influenciada por una combinación de factores sociales, económicos y estructurales. Variables como el sexo, la tarifa y la clase tienen un impacto significativo, mientras que otras aportan información complementaria o indirecta.

---

## Trabajo futuro

* Construcción de modelos predictivos (Regresión Logística, Random Forest, etc.)
* Evaluación de importancia de variables
* Mejora en la ingeniería de características

---
