# TelecomX_parte2_Latam
# Proyecto TelecomX - Análisis de Cancelación de Clientes (Churn)

## 1. Descripción del proyecto
El objetivo de este proyecto es **analizar y predecir la cancelación de clientes** (churn) de una compañía de telecomunicaciones. Se busca identificar los factores que más influyen en la decisión de cancelar el servicio y proponer estrategias de retención basadas en modelos predictivos.

---

## 2. Preprocesamiento de datos
1. **Limpieza de datos**  
   - Eliminación de columnas irrelevantes (IDs, duplicados, datos faltantes).
   - Corrección de valores inconsistentes y estandarización de columnas numéricas y categóricas.

2. **Encoding de variables categóricas**  
   - Transformación a formato numérico mediante **One-Hot Encoding** (`get_dummies`) para compatibilidad con modelos de machine learning.

3. **Balanceo de clases**  
   - Aplicación de **SMOTE** para generar ejemplos sintéticos de la clase minoritaria y equilibrar la distribución de churn.

4. **Normalización / estandarización**  
   - Se normalizaron variables numéricas para modelos sensibles a escala (Regresión Logística, KNN).

---

## 3. Análisis exploratorio
- **Proporción de churn**: se detectó un desbalance inicial entre clientes activos y cancelados.
- **Correlación**: se visualizó la matriz de correlación para identificar relaciones entre variables numéricas y la cancelación.
- **Análisis dirigido**: se exploraron patrones de variables clave como:
  - Tiempo de contrato (`tenure`) vs cancelación.
  - Gasto total (`Charges.Monthly`) vs cancelación.

---

## 4. Modelos predictivos
Se entrenaron dos modelos con características diferentes:

### 4.1 Regresión Logística
- Modelo sensible a la escala; se aplicó normalización.
- Permite interpretar la influencia directa de cada variable en la probabilidad de churn.

### 4.2 Random Forest
- Modelo no sensible a escala.
- Capta relaciones lineales y no lineales.
- Permite identificar la importancia de cada variable para la predicción.

---

## 5. Evaluación de modelos
Se evaluó cada modelo utilizando:

- **Exactitud (Accuracy)**
- **Precisión (Precision)**
- **Recall**
- **F1-score**
- **Matriz de confusión**

**Resultados principales:**

- Random Forest mostró mayor F1-score y mejor equilibrio entre precisión y recall.
- Regresión Logística proporcionó interpretabilidad directa de las variables.
- No se detectó overfitting significativo.

---

## 6. Variables más importantes
### Regresión Logística
- `customer.tenure`: más antigüedad → menor probabilidad de churn.
- `account.Charges.Monthly`: cargos altos → mayor probabilidad de churn.

### Random Forest
- Coinciden en gran parte con Regresión Logística, pero incluyen efectos no lineales.
- Variables de uso de servicios y cargos totales destacan como determinantes.

---

## 7. Estrategias de retención
1. Ofertas personalizadas para clientes con alto gasto mensual.
2. Programas de fidelización para clientes recientes o con bajo tiempo de contrato.
3. Monitoreo de patrones de uso para identificar clientes en riesgo.
4. Combinación de modelos para predicción precisa y análisis interpretativo.

---

## 8. Conclusión ✅
El análisis permitió identificar claramente los factores que impactan en la cancelación y desarrollar modelos predictivos efectivos. La combinación de modelos interpretables (Regresión Logística) y robustos (Random Forest) proporciona una **herramienta práctica para la retención de clientes**, enfocando esfuerzos en quienes presentan mayor riesgo de churn y ajustando políticas de precios o beneficios estratégicamente.

---

## 9. Visualizaciones
- Matriz de correlación de variables numéricas.
- Boxplots y scatter plots de variables clave vs churn.
- Gráficos de importancia de variables (coeficientes y feature importance).

---

## 10. Librerías principales utilizadas
- pandas, numpy
- scikit-learn (LogisticRegression, RandomForestClassifier, StandardScaler, train_test_split, metrics)
- imblearn (SMOTE)
- seaborn, matplotlib
