# Modelo Predictivo de Demanda basado en IA - Ecuacalcios S.A.

[cite_start]Este repositorio contiene el desarrollo técnico y los modelos de Inteligencia Artificial diseñados para optimizar la gestión de inventarios y reducir el riesgo operativo en la empresa Ecuacalcios S.A.[cite: 4, 175]. [cite_start]El proyecto implementa un enfoque de **Ensamble Estacional Híbrido** utilizando el algoritmo XGBoost junto con una capa de planificación de ventas y operaciones (S&OP)[cite: 73, 76].

## 📝 Descripción del Problema y Solución

### Problema
[cite_start]Ecuacalcios S.A. enfrentaba una gestión empírica de suministros, vulnerable a sesgos subjetivos y errores humanos, lo que derivaba en sobrestock de capital inmovilizado o quiebres de stock recurrentes[cite: 74, 102, 110]. [cite_start]Factores externos como la volatilidad del precio de la urea y las precipitaciones climáticas no eran procesados matemáticamente en la planificación tradicional[cite: 104].

### Solución
[cite_start]Se desarrolló un sistema predictivo **Full Code** que estandariza los registros históricos de ventas (2018-2025) a unidades logísticas de sacos de 50 kg e integra variables exógenas determinantes[cite: 77, 89, 287]. [cite_start]El núcleo de la solución es un modelo **XGBoost** (Extreme Gradient Boosting) optimizado para penalizar desviaciones críticas en meses de alta rotación[cite: 78, 445].

## 🛠️ Requisitos Técnicos y Dependencias

[cite_start]La solución fue desarrollada íntegramente en **Python 3.12.12** y está diseñada para ejecutarse en entornos locales o en la nube (**Google Colab**)[cite: 209, 274, 275].

### Librerías Necesarias:
* [cite_start]`xgboost`: Motor principal de aprendizaje supervisado[cite: 276].
* [cite_start]`pandas` & `numpy`: Manipulación y limpieza de series de tiempo[cite: 276, 290].
* [cite_start]`scikit-learn`: Preprocesamiento, validación cruzada temporal y métricas[cite: 276].
* [cite_start]`shap`: Capa de explicabilidad (XAI) para la toma de decisiones gerenciales[cite: 297, 302].
* [cite_start]`joblib`: Serialización y persistencia de los modelos entrenados[cite: 565].
* [cite_start]`matplotlib` & `seaborn`: Visualización de resultados y análisis de sensibilidad[cite: 276].

## 🚀 Instrucciones de Ejecución Paso a Paso

1. **Preparación del Entorno:**
   * [cite_start]Clone este repositorio o abra el notebook en **Google Colab**[cite: 209, 275].
   * Asegúrese de tener instaladas las dependencias: `pip install -r requirements.txt`.

2. **Carga de Información:**
   * [cite_start]Coloque los archivos de facturación histórica y los datasets de variables exógenas (Urea y Clima) en la carpeta `/data`[cite: 301, 304].

3. **Ejecución del Pipeline:**
   * Ejecute el script principal o notebook. [cite_start]El sistema realizará automáticamente la ingesta (ETL), el entrenamiento y la generación de proyecciones[cite: 326, 327].

4. **Consumo de Resultados:**
   * [cite_start]Consulte la carpeta `/resultados` para obtener el archivo `dataset_depurado_top3.csv` y las gráficas de proyección anual para el periodo 2026[cite: 412, 552].

## ⚙️ Explicación General del Pipeline

[cite_start]El flujo de procesamiento técnico se divide en cuatro fases principales[cite: 326]:

1. [cite_start]**Fase 1: ETL e Ingesta:** Automatización de lectura de datos heterogéneos y normalización de unidades de masa a sacos de 50 kg[cite: 327, 328].
2. [cite_start]**Fase 2: Feature Engineering:** Creación de componentes de memoria temporal (Lags 1, 2, 12) y suavizado de tendencias mediante medias móviles y EWMA[cite: 385, 391, 396].
3. [cite_start]**Fase 3: Modelado y Optimización:** Entrenamiento del algoritmo XGBoost con ajuste de hiperparámetros (*fine-tuning*) y validación por partición temporal para evitar sobreajuste[cite: 270, 271, 388].
4. [cite_start]**Fase 4: Plan Maestro S&OP:** Integración de la salida algorítmica con pesos históricos y multiplicadores comerciales (*Uplifts*) para generar la proyección final de 2026[cite: 447, 450, 455].

## 📈 Resultados y Control de Versiones

* [cite_start]**Versión Actual:** V1.6 (Producción)[cite: 4].
* [cite_start]**Fecha de Última Actualización:** 29/03/2026[cite: 8].
* **Exactitud Alcanzada (Enero 2026):**
  * [cite_start]Sulfato de Calcio: 97.4%[cite: 81].
  * [cite_start]Carbonato de Calcio: 89.9%[cite: 81].
  * [cite_start]Caldolomita: 97.4%[cite: 81].

## 📂 Organización del Repositorio

* [cite_start]`/data`: Fuentes internas de ventas y variables externas (clima/economía)[cite: 301, 304].
* [cite_start]`/notebooks`: Experimentos, análisis exploratorio (EDA) y entrenamiento[cite: 302].
* [cite_start]`/src`: Código fuente para la ejecución del pipeline y funciones de ajuste S&OP[cite: 303].
* [cite_start]`/models`: Archivos binarios `.pkl` con los modelos serializados listos para uso[cite: 565].
* [cite_start]`/resultados`: Reportes gerenciales, archivos `.csv` depurados y visualizaciones SHAP[cite: 307, 412].

---
[cite_start]**Nota:** Este proyecto se basa en la metodología CRISP-DM y cumple con los estándares de calidad ISO/IEC 25010[cite: 154, 218].
