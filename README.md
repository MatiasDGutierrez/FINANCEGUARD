# 🏦 FinanceGuard - Sistema de Predicción de Churn Bancario

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Advanced-green)
![Data Science](https://img.shields.io/badge/Data%20Science-Analysis-orange)

## 📋 Descripción del Proyecto

**FinanceGuard** es un proyecto integral de Machine Learning diseñado para predecir y reducir el churn (abandono de clientes) en una entidad bancaria. El proyecto combina técnicas supervisadas y no supervisadas para proporcionar una solución completa que va desde la predicción individual hasta la segmentación estratégica de clientes.

### 🎯 Objetivo Principal

Identificar clientes en riesgo de abandono y proporcionar estrategias de retención personalizadas basadas en segmentación de comportamiento, con el fin de maximizar la rentabilidad del banco mediante la reducción de la pérdida de valor del cliente (LTV).

## 📊 Estructura del Proyecto

```
ProyectoM4_MatiasGutierrez/
├── Notebooks/
│   ├── 1_EDA_RegresionLogistica.ipynb      # Análisis Exploratorio y Baseline
│   ├── 2_GradientBoosting_Optimizacion.ipynb  # Modelos Avanzados y Optimización
│   ├── 3_AprendisajeNoSupervisado.ipynb    # Clustering y Segmentación
│   ├── 4_Extra_Credit.ipynb                # Integración y Optimización de Negocio
│   ├── Churn_Modelling.csv                 # Dataset Original
│   ├── Churn_Modelling_Clusters.csv        # Dataset con Clusters
│   ├── mejor_modelo_churn.pkl              # Modelo Final Guardado
│   ├── scaler_churn.pkl                    # Scaler Guardado
│   └── catboost_info/                      # Información de entrenamiento CatBoost
├── Documentacion/
│   └── Reporte_Modelos.pdf                 # Documentación técnica detallada
└── README.md                               # Este archivo
```

## 🔬 Componentes del Proyecto

### 1. Análisis Exploratorio de Datos (EDA) y Regresión Logística
**Archivo:** `1_EDA_RegresionLogistica.ipynb`

- **Análisis demográfico:** Estudio de variables como edad, género y geografía
- **Análisis financiero:** Evaluación de balance, número de productos, puntuación crediticia
- **Matriz de correlaciones:** Identificación de relaciones entre variables
- **Modelo baseline:** Regresión Logística como punto de referencia
- **Métricas iniciales:** Accuracy: 80.8%, AUC: 0.7748

**Hallazgos clave:**
- Tasa de churn global: 20.4%
- Clientes alemanes tienen mayor tasa de abandono
- Edad y actividad del cliente son predictores fuertes
- Clientes con balances extremos (muy altos o muy bajos) muestran mayor churn

### 2. Gradient Boosting y Optimización de Hiperparámetros
**Archivo:** `2_GradientBoosting_Optimizacion.ipynb`

- **Modelos implementados:**
  - Random Forest (Baseline)
  - XGBoost con Grid Search
  - XGBoost con Optuna (Optimización Bayesiana)
  - LightGBM
  - CatBoost
  - Stacking Ensemble

- **Optimización:**
  - Grid Search para búsqueda exhaustiva
  - Optuna para optimización bayesiana eficiente
  - Validación cruzada estratificada

- **Mejoras logradas:**
  - AUC mejorado de 0.7748 a 0.8686
  - Precision mejorada significativamente
  - Mejor captura de clientes en riesgo

### 3. Aprendizaje No Supervisado y Segmentación
**Archivo:** `3_AprendisajeNoSupervisado.ipynb`

- **Reducción de dimensionalidad:**
  - PCA (Principal Component Analysis)
  - t-SNE para visualización no lineal

- **Algoritmos de clustering:**
  - K-Means con método del codo y silueta
  - DBSCAN para detección de anomalías

- **Segmentación estratégica:**
  - 4 clusters identificados con perfiles distintos
  - Motor de estrategia con recomendaciones personalizadas
  - Detección de outliers (0.40% de la base)

**Perfiles de clusters identificados:**
- **Cluster 0:** Riesgo alto (32.4% churn) - Clientes sensibles al precio
- **Cluster 1:** Riesgo moderado (16.4% churn) - Comportamiento estable
- **Cluster 2:** Riesgo moderado (16.7% churn) - Comportamiento estable
- **Cluster 3:** Riesgo moderado (15.9% churn) - Clientes leales

### 4. Integración Analítica y Optimización de Negocio
**Archivo:** `4_Extra_Credit.ipynb`

- **Comparativa de modelos:**
  - Baseline vs Modelo Final Ensamble
  - Ganancia de 9.87% en AUC

- **Integración con clusters:**
  - Validación de predicciones por segmento
  - Consistencia del modelo en cada cluster

- **Optimización de threshold:**
  - Análisis de costos de negocio
  - Costo Falso Negativo: $500 (pérdida LTV)
  - Costo Falso Positivo: $50 (costo campaña)
  - Threshold óptimo: 0.29 (vs 0.50 estándar)
  - Reducción de pérdida total en 22%

## 🛠️ Stack Tecnológico

### Bibliotecas Principales
- **pandas, numpy:** Manipulación de datos
- **matplotlib, seaborn:** Visualizaciones
- **scikit-learn:** Preprocesamiento y métricas
- **xgboost:** Gradient Boosting optimizado
- **lightgbm:** Gradient Boosting eficiente
- **catboost:** Gradient Boosting con manejo automático de categóricas
- **optuna:** Optimización de hiperparámetros

### Algoritmos Implementados
- Regresión Logística
- Random Forest
- XGBoost
- LightGBM
- CatBoost
- Stacking Ensemble
- K-Means
- DBSCAN
- PCA
- t-SNE

## 📈 Resultados Principales

### Métricas del Modelo Final
- **Accuracy:** 87.1%
- **Precision:** 81.4%
- **Recall:** 47.4%
- **F1-Score:** 59.9%
- **ROC-AUC:** 0.8686

### Impacto de Negocio
- **Mejora en detección:** 15% más de clientes en riesgo identificados
- **Eficiencia financiera:** 22% de mejora en rentabilidad neta
- **Threshold optimizado:** 0.29 (vs 0.50 estándar)
- **Ahorro estimado:** Reducción significativa de pérdida de LTV

## 🚀 Cómo Usar el Proyecto

### Instalación de Dependencias

**Opción 1: Usar requirements.txt (Recomendado)**
```bash
pip install -r requirements.txt
```

**Opción 2: Instalar manualmente**
```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost lightgbm catboost optuna joblib nbconvert==6.5.0 nbformat==5.4.0
```

### Ejecutar los Notebooks

1. **Análisis Exploratorio:**
```bash
jupyter notebook Notebooks/1_EDA_RegresionLogistica.ipynb
```

2. **Modelos Avanzados:**
```bash
jupyter notebook Notebooks/2_GradientBoosting_Optimizacion.ipynb
```

3. **Segmentación:**
```bash
jupyter notebook Notebooks/3_AprendisajeNoSupervisado.ipynb
```

4. **Integración Final:**
```bash
jupyter notebook Notebooks/4_Extra_Credit.ipynb
```

### Usar el Modelo Entrenado

```python
import joblib
import pandas as pd

# Cargar modelo y scaler
model = joblib.load('Notebooks/mejor_modelo_churn.pkl')
scaler = joblib.load('Notebooks/scaler_churn.pkl')

# Preprocesar datos (siguiendo el mismo proceso que en los notebooks)
# ... (ver código en notebooks para detalles)

# Predecir
probabilidad_churn = model.predict_proba(X_scaled)[:, 1]
```

## 📊 Dataset

**Fuente:** Churn_Modelling.csv
- **Muestras:** 10,000 clientes
- **Variables:** 14 características
- **Target:** Exited (0 = No Churn, 1 = Churn)
- **Desbalance:** 79.6% No Churn, 20.4% Churn

**Variables principales:**
- CreditScore: Puntuación crediticia
- Geography: País (France, Germany, Spain)
- Gender: Género
- Age: Edad
- Tenure: Antigüedad en el banco
- Balance: Saldo de cuenta
- NumOfProducts: Número de productos bancarios
- HasCrCard: Tiene tarjeta de crédito
- IsActiveMember: Es miembro activo
- EstimatedSalary: Salario estimado

## 🎓 Conclusiones y Recomendaciones

### Insights Estratégicos
1. **Geografía importa:** Alemania concentra la mayor tasa de churn
2. **Edad como factor:** Clientes mayores (45-60 años) tienen mayor riesgo
3. **Actividad crítica:** Clientes inactivos tienen 3.5x más probabilidad de churn
4. **Segmentación efectiva:** Los clusters permiten estrategias personalizadas

### Recomendaciones de Negocio
- **Cluster 0 (Alto Riesgo):** Contacto telefónico prioritario, descuentos agresivos
- **Clusters 1-3 (Riesgo Moderado):** Email marketing, cross-selling suave
- **Outliers:** Monitoreo especial y análisis individualizado
- **Threshold optimizado:** Usar 0.29 en lugar de 0.50 para maximizar rentabilidad

## 👤 Autor

**Matias Damian Gutierrez**
- Rol: Científico de Datos Junior
- Proyecto: M4 - Machine Learning Avanzado
- Fecha: 2025

## 📄 Licencia

Este proyecto es parte de un portfolio académico y está disponible para fines educativos.

## 🔗 Enlaces

- **GitHub Repository:** https://github.com/MatiasDGutierrez/FINANCEGUARD.git
- **Documentación detallada:** Ver `Documentacion/Reporte_Modelos.pdf`

---

**Nota:** Este proyecto demuestra la aplicación completa de técnicas de Machine Learning en un contexto de negocio real, desde el análisis exploratorio hasta la implementación de modelos optimizados y la generación de valor estratégico.
