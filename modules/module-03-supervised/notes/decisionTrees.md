# Decision Trees — Notas Clave

## ¿Qué es un Decision Tree?
- Modelo de **clasificación** o **regresión** basado en reglas de tipo *if/else*.
- Divide los datos en ramas según condiciones en las variables de entrada.
- **Ventaja principal:** interpretabilidad (fácil de explicar a no 
técnicos).

---

## Dataset (Drug Prediction)
- 200 pacientes, variables:
  - **Age** (numérica)
  - **Sex** (M/F)
  - **BP** (LOW, NORMAL, HIGH)
  - **Cholesterol** (NORMAL, HIGH)
  - **Na_to_K** (numérica)
- Target: **Drug** (DrugA, DrugB, DrugC, DrugX, DrugY).

---

## Preprocesamiento
- Scikit-learn necesita todo en **numérico**.
- Opción rápida: `LabelEncoder`.
  - BP → HIGH=0, LOW=1, NORMAL=2
  - Cholesterol → HIGH=0, NORMAL=1
- Opción recomendada: `OneHotEncoder` → columnas con nombre (`BP_LOW`, `BP_NORMAL`, etc.) → árbol más legible.

---

## Cómo leer un árbol (scikit-learn)
- Cada nodo se imprime como: `feature <= threshold`
- **Rama izquierda** = condición True (≤).
- **Rama derecha** = condición False (>).
- Los thresholds como 0.5, 1.5 vienen de la **codificación de categorías**.

Ejemplo con BP:
- `BP <= 0.5` → BP = HIGH
- `BP > 0.5` → BP = LOW o NORMAL
- `BP <= 1.5` → BP = LOW
- `BP > 1.5` → BP = NORMAL

---

## Reglas finales del árbol (Drug Prediction)
- **Drug Y**: Na_to_K > 14.627  
- **Drug A**: Na_to_K ≤ 14.627, BP = HIGH, Age ≤ 50.5  
- **Drug B**: Na_to_K ≤ 14.627, BP = HIGH, Age > 50.5  
- **Drug C**: Na_to_K ≤ 14.627, BP = LOW, Cholesterol = HIGH  
- **Drug X**: Na_to_K ≤ 14.627, BP = NORMAL, Cholesterol = HIGH  

---

## Conceptos clave
- **No requiere normalización/estandarización** (usa splits, no distancias).
- Maneja variables categóricas y numéricas.
- Fácil de interpretar, pero puede **sobreajustar** si es muy profundo → usar `max_depth` o `min_samples_leaf`.
- Para más poder predictivo: usar **Random Forests** o **Gradient Boosting**.

---

## Tips prácticos
- Usa `feature_names` y `class_names` en `plot_tree` para entender mejor el gráfico.
- Para reglas en texto: `from sklearn.tree import export_text`.
- Si quieres máxima claridad: usa One-Hot en lugar de LabelEncoder.

---

## Frase para recordar
**Un árbol de decisión es solo un conjunto de preguntas sí/no que dividen el espacio de datos hasta llegar a una clase final.**
