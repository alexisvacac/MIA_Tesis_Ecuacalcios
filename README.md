# Modelo Predictivo de Demanda basado en IA - Ecuacalcios S.A.

Este repositorio contiene el desarrollo técnico y los modelos de Inteligencia Artificial diseñados para optimizar la gestión de inventarios y reducir el riesgo operativo en la empresa Ecuacalcios S.A. El proyecto implementa un enfoque de **Ensamble Estacional Híbrido** utilizando el algoritmo XGBoost junto con una capa de planificación de ventas y operaciones (S&OP)

## 📝 Descripción del Problema y Solución

### Problema
Ecuacalcios S.A. enfrentaba una gestión empírica de suministros, vulnerable a sesgos subjetivos y errores humanos, lo que derivaba en sobrestock de capital inmovilizado o quiebres de stock recurrentes 
Factores externos como la volatilidad del precio de la urea y las precipitaciones climáticas no eran procesados matemáticamente en la planificación tradicional

### Solución
Se desarrolló un sistema predictivo **Full Code** que estandariza los registros históricos de ventas (2018-2025) a unidades logísticas de sacos de 50 kg e integra variables exógenas determinantes. El núcleo de la solución es un modelo **XGBoost** (Extreme Gradient Boosting) optimizado para penalizar desviaciones críticas en meses de alta rotación.

## 🛠️ Requisitos Técnicos y Dependencias

La solución fue desarrollada íntegramente en **Python 3.12.12** y está diseñada para ejecutarse en entornos locales o en la nube (**Google Colab**).

### Librerías Necesarias:
* `xgboost`: Motor principal de aprendizaje supervisado.
* `pandas` & `numpy`: Manipulación y limpieza de series de tiempo.
* `scikit-learn`: Preprocesamiento, validación cruzada temporal y métricas.
* `shap`: Capa de explicabilidad (XAI) para la toma de decisiones gerenciales.
* `joblib`: Serialización y persistencia de los modelos entrenados.
* `matplotlib` & `seaborn`: Visualización de resultados y análisis de sensibilidad.

## 🚀 Instrucciones de Ejecución Paso a Paso

1. **Preparación del Entorno:**
   * Clone este repositorio o abra el notebook en **Google Colab**.
   * Asegúrese de tener instaladas las dependencias: `pip install -r requirements.txt`.

2. **Carga de Información:**
   * Coloque los archivos de facturación histórica y los datasets de variables exógenas (Urea y Clima) en la carpeta `/data`.

3. **Ejecución del Pipeline:**
   * Ejecute el script principal o notebook. El sistema realizará automáticamente la ingesta (ETL), el entrenamiento y la generación de proyecciones.

4. **Consumo de Resultados:**
   * Consulte la carpeta `/resultados` para obtener el archivo `dataset_depurado_top3.csv` y las gráficas de proyección anual para el periodo 2026.

## ⚙️ Explicación General del Pipeline

El flujo de procesamiento técnico se divide en cuatro fases principales:

1. **Fase 1: ETL e Ingesta:** Automatización de lectura de datos heterogéneos y normalización de unidades de masa a sacos de 50 kg.
2. **Fase 2: Feature Engineering:** Creación de componentes de memoria temporal (Lags 1, 2, 12) y suavizado de tendencias mediante medias móviles y EWMA.
3. **Fase 3: Modelado y Optimización:** Entrenamiento del algoritmo XGBoost con ajuste de hiperparámetros (*fine-tuning*) y validación por partición temporal para evitar sobreajuste.
4. **Fase 4: Plan Maestro S&OP:** Integración de la salida algorítmica con pesos históricos y multiplicadores comerciales (*Uplifts*) para generar la proyección final de 2026.

## 📈 Resultados y Control de Versiones

* **Versión Actual:** V1.6 (Producción).
* **Fecha de Última Actualización:** 29/03/2026.
* **Exactitud Alcanzada (Enero 2026):**
  * ]Sulfato de Calcio: 97.4%.
  * Carbonato de Calcio: 89.9%.
  * Caldolomita: 97.4%.

## 📂 Organización del Repositorio

* `/data`: Fuentes internas de ventas y variables externas (clima/economía).
* `/notebooks`: Experimentos, análisis exploratorio (EDA) y entrenamiento.
* `/src`: Código fuente para la ejecución del pipeline y funciones de ajuste S&OP.
* `/models`: Archivos binarios `.pkl` con los modelos serializados listos para uso.
* `/resultados`: Reportes gerenciales, archivos `.csv` depurados y visualizaciones SHAP.

---
**Nota:** Este proyecto se basa en la metodología CRISP-DM y cumple con los estándares de calidad ISO/IEC 25010.
