# Potabilidad del Agua: Un Diagnóstico por IA

[cite_start]Este proyecto desarrolla un modelo de inteligencia artificial capaz de diagnosticar si el agua es apta para el consumo humano basándose en diversas medidas fisicoquímicas[cite: 1, 5].

## 📋 Planteamiento del Problema
[cite_start]El agua es un recurso vital cuya aptitud para el consumo debe ser medida constantemente[cite: 4]. [cite_start]El objetivo es crear un modelo predictivo que determine el estado de potabilidad a partir de indicadores estándar de calidad[cite: 5, 6].

## 📊 Descripción del Dataset
[cite_start]El conjunto de datos consta de **3,276 registros** con las siguientes características[cite: 26, 27]:
* [cite_start]**Químicas:** pH, Cloraminas, Sulfatos[cite: 28, 33, 35].
* [cite_start]**Físicas:** Dureza, Sólidos, Conductividad, Turbiedad[cite: 30, 31, 37, 44].
* [cite_start]**Orgánicas:** Carbono Orgánico, Trihalometanos[cite: 39, 43].
* [cite_start]**Target:** Potabilidad[cite: 45].

## 🛠️ Tratamiento de Datos
[cite_start]Se identificaron valores nulos (NaN) significativos en las columnas de **Sulfate (781)**, **ph (491)** y **Trihalomethanes (162)**[cite: 47, 50]. [cite_start]Para el preprocesamiento se evaluaron tres estrategias de imputación[cite: 224]:
1. [cite_start]Reemplazo por la **media**[cite: 228].
2. [cite_start]Reemplazo aleatorio basado en una **distribución normal**[cite: 229].
3. [cite_start]Reemplazo aleatorio basado en una **distribución normal segmentada por estado de potabilidad**[cite: 230].

## 📈 Análisis y Correlación
[cite_start]Se observó una **correlación cercana a cero** entre las variables, lo que incrementa la dificultad de la predicción y hace que el aprendizaje sea menos eficiente bajo condiciones estándar[cite: 51, 52].

## 🚀 Resultados de los Modelos
[cite_start]El desempeño de los clasificadores mejoró significativamente al utilizar el tercer método de imputación (segmentado por potabilidad)[cite: 383].

### Comparativa de Accuracy (Tercer Modelo)
| Clasificador | Accuracy |
| :--- | :--- |
| **Random Forest** | [cite_start]**0.795** [cite: 481] |
| **Decision Tree** | [cite_start]0.723 [cite: 480] |
| **PCA** | [cite_start]0.619 [cite: 486] |
| **SVC** | [cite_start]0.609 [cite: 484] |

## 🎥 Demostración y Detalles Técnicos
Puedes ver la presentación detallada del proyecto y la explicación del código en el siguiente video:
👉 [Ver video en YouTube](https://youtu.be/ZrBmmSQ4eZ8)

### Puntos clave del video:
* **Segmentación por Potabilidad:** Se explica por qué el tercer método de imputación (basado en una distribución normal segmentada) es el más efectivo, logrando capturar mejor la naturaleza de los datos no lineales.
* **Estabilidad del Modelo:** Mediante el uso de `n_estimators = 200`, el modelo de Random Forest logra una curva de aprendizaje más estable, reduciendo la varianza en las predicciones.
* **Validación Cruzada:** Se detalla el uso de 6 folds para garantizar que el accuracy obtenido sea consistente y no producto del azar en la partición de los datos.
* **Análisis de Características:** Explicación de cómo variables como el pH y los Sulfatos influyen en la decisión final del clasificador a pesar de su baja correlación inicial.

## 🏁 Conclusiones
* [cite_start]El modelo **Random Forest Classifier** fue el más efectivo, utilizando `n_estimators = 200` y validación cruzada con `6 folds`.
* [cite_start]La mejora en los resultados al segmentar el reemplazo de datos sugiere que la potabilidad depende de múltiples factores externos no necesariamente lineales o sistémicos[cite: 538].

---
[cite_start]**Realizado por:** Lewing Andres Mendez Oritz [cite: 2]

