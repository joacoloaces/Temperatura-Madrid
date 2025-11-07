# Predicción de Temperatura Media Diaria en Madrid

**Autores:**  
- Joaquín Loaces Estrugo 
- Carmen Gallardo Martín   
- Pablo Moreno Aranda  

**Fecha:** Octubre 2025  

---

## 🧭 Descripción del Proyecto

Este proyecto forma parte de la **Práctica de Series Temporales** del Máster en Inteligencia Artificial Aplicada de la Universidad Carlos III de Madrid.  
El objetivo principal es **predecir la temperatura media semanal de la ciudad de Madrid** utilizando diferentes enfoques estadísticos y de *machine learning*, comparando su rendimiento y capacidad de generalización.

El estudio analiza la serie temporal de temperaturas junto con variables exógenas como **precipitación, velocidad del viento y presión atmosférica**, evaluando su influencia en la predicción.

---

## 🎯 Objetivos

1. Realizar un **análisis exploratorio** de la serie temporal, identificando sus componentes de tendencia, estacionalidad y ruido.  
2. Implementar y comparar modelos de la familia **Box-Jenkins (AR, ARIMA, SARIMAX)**.  
3. Desarrollar modelos de **machine learning** basados en *feature engineering* (lags, medias móviles, variables temporales).  
4. Evaluar y comparar el rendimiento mediante métricas **MAE** y **RMSE**.  
5. Analizar la **escalabilidad y eficiencia** de cada enfoque.

---

## 📊 Dataset

- **Fuente:** Datos meteorológicos históricos de Madrid (AEMET).  
- **Frecuencia original:** Diaria.  
- **Frecuencia utilizada:** Semanal (resampleo para reducir volatilidad y missing values).  
- **Variables:**  
  - `tavg`: Temperatura media  
  - `precip`: Precipitación  
  - `wspd`: Velocidad del viento  
  - `pres`: Presión atmosférica  

---

## 🧪 Modelos Implementados

### 🔹 Modelos Estadísticos
- **AR (Autoregressive)**
- **ARIMA**
- **ARIMAX**
- **SARIMAX** ← 🥇 *Mejor modelo global (MAE = 1.818, RMSE = 2.262)*

### 🔹 Modelos de Machine Learning
- Ridge, Lasso, ElasticNet  
- Decision Tree  
- Random Forest  
- Gradient Boosting  
- KNN  
- Support Vector Regressor (SVR) ← *Mejor modelo ML (MAE = 2.0074)*

---

## ⚙️ Metodología

1. **Análisis Exploratorio**  
   - Descomposición de la serie temporal.  
   - Estudio de autocorrelaciones y correlaciones de lags.  

2. **Preprocesamiento**  
   - Resampleo semanal.  
   - Eliminación de valores faltantes.  
   - Creación de *lags* y variables temporales.  

3. **Entrenamiento y Validación**  
   - División temporal:  
     - Train: 2018–2024  
     - Test: 2024–2025  
   - Backtesting con validación temporal.

4. **Evaluación**  
   - Métricas utilizadas: **MAE** y **RMSE**.  
   - Comparación entre modelos con y sin variables exógenas.

---

## 📈 Resultados Principales

| Modelo      | MAE   | RMSE  | Exógenas |
|--------------|-------|-------|-----------|
| AR           | 2.040 | 2.513 | No        |
| ARIMA        | 1.922 | 2.463 | No        |
| ARIMAX       | 1.845 | 2.281 | Sí        |
| **SARIMAX**  | **1.818** | **2.262** | ✅ Sí |
| SVR (RBF)    | 2.007 | —     | No        |

El modelo **SARIMAX** fue el único que logró mejorar su rendimiento al incorporar variables exógenas, demostrando una mayor robustez y capacidad de modelar tanto la **estacionalidad anual** como la **variabilidad a corto plazo**.

---

## 🚀 Conclusiones

- Todos los modelos capturaron correctamente la **tendencia estacional anual**.  
- **ARIMA y SVR** produjeron predicciones más suaves, ideales para representar tendencias promedio.  
- **SARIMAX** fue el único modelo capaz de reproducir el *ruido* y la variabilidad real de la serie.  
- En términos de **eficiencia y escalabilidad**, SARIMAX demostró ser más estable que los modelos de ML.  

📅 Como trabajo futuro, se propone extender las predicciones hasta el año **2030** para analizar escenarios de evolución climática.

---

## 🧰 Tecnologías Utilizadas

- Python 3.11  
- pandas, numpy  
- statsmodels  
- scikit-learn  
- skforecast  
- matplotlib, seaborn  

---

## 📚 Referencias

- AEMET (1989). *Tiempo y Clima, Nº 12*.  
- Mohammed et al. (2022). *Comparative Analysis of ARIMA, SARIMA and Prophet Model in Forecasting*.  
- Prasad et al. (2021). *Random Forest for Temperature Prediction*.  
- Liang et al. (2020). *XGBoost for Air Quality Forecasting*.  
- Torres, J. (2021). *skforecast: Time series forecasting with scikit-learn regressors*.  

---

## 📦 Estructura del Repositorio

