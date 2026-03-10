# Challenge: Predicción de Cancelación de Clientes (Churn)

## Descripción del Proyecto
Este proyecto tiene como objetivo **analizar y predecir la cancelación de clientes (churn)** de una empresa de telecomunicaciones.  
Se emplean técnicas de **preprocesamiento de datos, modelado predictivo y análisis de variables**, con el fin de identificar los factores más relevantes que afectan la permanencia de los clientes y proponer estrategias de retención.

El proyecto incluye:
- Exploración y limpieza de datos.
- Estandarización de variables numéricas.
- Selección y comparación de modelos de machine learning.
- Evaluación del desempeño de los modelos.
- Análisis de la importancia de las variables.
- Recomendaciones basadas en los resultados obtenidos.

---

## Dataset
- Fuente: CSV público subido a GitHub.
- Contiene **7,032 registros** y **21 variables** después de eliminar columnas irrelevantes.
- Variables principales incluyen:
  - `churn`: indicador de cancelación (0 = activo, 1 = canceló).
  - `customer_tenure`: meses como cliente.
  - `account_contract_*`: tipo de contrato.
  - `account_charges_total` y `account_charges_monthly`: gastos del cliente.
  - Variables categóricas transformadas mediante **One-Hot Encoding**.

---

## Preprocesamiento
1. Eliminación de columnas irrelevantes (`customerid`).
2. Conversión de variables categóricas en **dummies**.
3. Transformación de booleanos a enteros.
4. **Estandarización** de variables numéricas para modelos sensibles a escala (`StandardScaler`).
5. División en **conjuntos de entrenamiento y prueba** (70% / 30%).

---

## Modelos Implementados
Se implementaron dos tipos de modelos para comparar su desempeño:

### 1. Regresión Logística
- Requiere **normalización de datos**.
- Permite interpretar los **coeficientes** de cada variable.
- Identifica variables que aumentan o disminuyen la probabilidad de cancelación.

### 2. Árbol de Decisión
- No requiere normalización.
- Evalúa la importancia de las variables según la **reducción de impureza** en los nodos.
- Muestra la jerarquía y combinaciones de factores que influyen en el churn.

---

## Evaluación de Modelos
Se utilizaron las siguientes métricas:

- **Exactitud (Accuracy)**  
- **Precisión (Precision)**  
- **Recall (Sensibilidad)**  
- **F1-score**  
- **Matriz de confusión**

**Análisis crítico:**
- La Regresión Logística permite interpretar la contribución de cada variable.  
- El Árbol de Decisión facilita visualizar la jerarquía de variables y sus interacciones.  
- Se identificó que `customer_tenure`, `account_contract_two_year` y `account_paymentmethod_electronic check` son variables determinantes en la cancelación.

---

## Importancia de las Variables
- **Regresión Logística:** coeficientes muestran si una variable aumenta o disminuye el churn.  
- **Árbol de Decisión:** la reducción de impureza indica la relevancia de cada variable.  
- Variables más influyentes:
  - `customer_tenure` (tiempo como cliente)  
  - `account_contract_two_year` (contratos largos)  
  - `internet_internetservice_fiber optic` (tipo de servicio)  
  - `account_paymentmethod_electronic check` (método de pago)  
  - `account_charges_total` (gasto total)

---

## Conclusiones y Estrategias
1. **Fidelización temprana:** incentivar contratos largos para clientes nuevos.  
2. **Optimización de métodos de pago:** reducir riesgos asociados a cheques electrónicos.  
3. **Segmentación del servicio de internet:** mejorar experiencia de clientes de fibra óptica.  
4. **Programas de engagement:** incentivar clientes con bajo consumo total mediante promociones o lealtad.  

El análisis combina la **interpretación de modelos lineales** con la **visualización de árboles**, proporcionando una visión completa de los factores que afectan la cancelación.

---

## Librerías Utilizadas
- `pandas`  
- `numpy`  
- `seaborn`  
- `matplotlib`  
- `scikit-learn` (`train_test_split`, `StandardScaler`, `LogisticRegression`, `DecisionTreeClassifier`, `metrics`)

---

##Autor

Neyker Ochoa

Análisis de datos, modelado predictivo y visualización.
