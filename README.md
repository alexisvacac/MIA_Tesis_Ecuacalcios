# Ecuacalcios_Inventory_Forecasting 🚀

Este repositorio contiene el desarrollo e implementación de un modelo de **Inteligencia Artificial Pura** diseñado para optimizar la gestión de inventarios y reducir el riesgo operativo en la empresa **Ecuacalcios S.A.**. 

El proyecto transforma datos históricos y variables externas en decisiones estratégicas, permitiendo una transición de una cultura reactiva a una **gestión proactiva basada en evidencia**.

## 📌 Características Principales
* **Algoritmo Core:** Implementación de **XGBoost** (Extreme Gradient Boosting) para regresión multivariante.
* **Variables Exógenas:** Integración de niveles de precipitación (FONAG), precio internacional de la urea e indicadores de disrupción socioeconómica (paros nacionales).
* **Ingeniería de Características:** Generación de **Lags** (rezagos temporales), medias móviles y ventanas temporales para capturar la estacionalidad profunda.
* **Explicabilidad (XAI):** Uso de la Teoría de Juegos mediante valores **SHAP** para auditar cada predicción y eliminar el efecto "caja negra".
* **Inferencia Autónoma:** Generación automática del Plan Maestro de Inventarios 2026 sin intervención manual.

## 🛠️ Stack Tecnológico
* **Lenguaje:** Python 3.12
* **Entorno:** Google Colab (Infraestructura Cloud)
* **Librerías Clave:**
    * `xgboost`: Motor principal de aprendizaje supervisado.
    * `shap`: Interpretabilidad técnica del modelo.
    * `pandas` & `numpy`: Procesamiento ETL y manipulación estructural.
    * `scikit-learn`: Preprocesamiento, validación cruzada temporal y métricas.

## 📈 Resultados y Validación
El prototipo fue validado con la venta real del primer trimestre (Q1) de 2026, demostrando alta robustez en entornos de variabilidad agrícola:

* **Caldolomita:** WMAPE de **22.54%** (Precisión del 77.46%).
* **Carbonato de Calcio:** WMAPE de **39.62%**.
* **Sulfato de Calcio:** WMAPE de **40.24%**.

**Impacto Empresarial:** Se proyecta una optimización del capital de trabajo de **$37,144.19 USD anuales** para el portafolio estratégico.

## ⚙️ Metodología
El desarrollo se estructuró bajo el estándar internacional **CRISP-DM**:
1. **Comprensión del Negocio:** Análisis de sobrestock y quiebres de inventario.
2. **Preparación de Datos:** Pipeline ETL con estandarización estricta a unidades de sacos de 50kg.
3. **Modelado y Optimización:** Ajuste de hiperparámetros mediante `GridSearchCV` y validación temporal.
4. **Evaluación de Robustez:** Pruebas de estrés ante escenarios de sequía e inflación de insumos.

## 👨‍💻 Autores
**Edwin Alexis Vaca Cóndor y Lizbeth Alejandra Suárez Minchala** *Maestría en Inteligencia Artificial Aplicada - UDLA*

---
*Este proyecto cumple con las políticas de confidencialidad de Ecuacalcios S.A. y los principios éticos de anonimización de datos sensibles.*
