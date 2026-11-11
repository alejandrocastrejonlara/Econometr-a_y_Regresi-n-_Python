

## Descripción del Proyecto
Este repositorio consolida un portafolio de análisis econométrico empírico y predictivo desarrollado en Python. A lo largo de cuatro proyectos, se aborda la progresión desde los fundamentos de la regresión lineal múltiple por Mínimos Cuadrados Ordinarios (MCO) hasta la implementación de técnicas avanzadas para solucionar problemas estructurales de datos (heterocedasticidad, autocorrelación, multicolinealidad), la modelación de sistemas complejos mediante Variables Instrumentales, y la evaluación de modelos predictivos aplicados al sector financiero e inmobiliario.

## Tecnologías y Librerías
*   **Lenguaje:** Python
*   **Análisis Econométrico:** `statsmodels` (MCO, WLS, HAC/HC0, MixedLM, VIF, Hausman), `linearmodels` (IV2SLS, IV3SLS, SUR, PanelOLS, RandomEffects)
*   **Machine Learning & Predicción:** `scikit-learn` (train_test_split, mean_squared_error)
*   **Gestión de Datos:** `pandas`, `numpy`, `scipy.stats`
*   **Visualización:** `matplotlib`, `seaborn`, `plotly`

---

## Estructura del Repositorio


### 0. Fundamentos del Aprendizaje Supervisado y Regresión Simple
**Archivo:** `Reporte_0_Regresion_Lineal_Simple.ipynb`
*   **Marco Teórico:** Introducción a la arquitectura del aprendizaje supervisado, definiendo el mapeo de variables independientes hacia variables de respuesta.
*   **Regresión Lineal Simple (RLS):** Implementación paso a paso de estimaciones de una sola variable, sirviendo como fundamento matemático y programático para los modelos múltiples y avanzados posteriores.

*   # Análisis Econométrico y Modelado de Regresión en Python

  
### 1. Regresión Lineal Múltiple y Validación Básica
**Archivo:** `Reporte_1_Regresion_Lineal_Multiple.ipynb`
*   **Estimación por MCO:** Desarrollo de un modelo de regresión lineal múltiple para explicar una variable dependiente a través de la estimación de interceptos y múltiples variables independientes.
*   **Validación de Supuestos:** Uso de la prueba de Durbin-Watson para descartar autocorrelación y el test de Jarque-Bera para evaluar la normalidad de los residuos basándose en la simetría y curtosis.
*   **Análisis de Varianza:** Cálculo manual y verificación del coeficiente de determinación ($R^2$) mediante la descomposición de la suma de cuadrados totales (SST), la suma de cuadrados de la regresión (SSR) y la suma de cuadrados del error (SSE).

### 2. Transformaciones Funcionales y Multicolinealidad
**Archivo:** `Reporte_2_Transformaciones_Dummies.ipynb`
*   **Optimización Funcional:** Contraste de modelos lineales básicos frente a transformaciones Log-Lineal y Box-Cox para corregir relaciones no lineales, empleando el Criterio de Información de Akaike (AIC) para seleccionar el ajuste más eficiente.
*   **Detección de Multicolinealidad:** Implementación del Factor de Inflación de Varianza (VIF) para identificar variables explicativas altamente colineales (ej. DPS y RE) que distorsionan la precisión del modelo.
*   **Variables Dummy e Interacciones:** Integración de variables categóricas para capturar cambios en la pendiente y el nivel base del precio por acción, determinando el modelo más eficiente mediante pruebas individuales y globales.

### 3. Detección y Corrección de Heterocedasticidad y Autocorrelación
**Archivo:** `Reporte_3_Heterocedasticidad_Autocorrelacion.ipynb`
*   **Diagnóstico de Residuos:** Detección de heterocedasticidad (varianza no constante) mediante análisis gráfico en forma de abanico y el test estadístico de Breusch-Pagan, además de la identificación de autocorrelación en series de tiempo con los tests de Durbin-Watson y Breusch-Godfrey.
*   **Corrección de Varianza transversal:** Implementación de Mínimos Cuadrados Ponderados (WLS) y errores estándar robustos de White (HC0) para asegurar la validez de los intervalos de confianza y las pruebas de hipótesis.
*   **Ajustes Temporales:** Corrección de autocorrelación iterativa mediante la transformación de Cochrane-Orcutt y la estimación de errores estándar robustos HAC (Newey-West) para compensar dependencias en los datos.

### 4. Modelo Final: Endogeneidad, Datos de Panel y Predicción Crediticia
**Archivo:** `Reporte_4_Modelo_Final_Vivienda.ipynb`
*   **Variables Instrumentales y SUR:** Corrección del sesgo por simultaneidad en decisiones financieras mediante precios de acciones como instrumentos (2SLS / 3SLS) y modelado de sistemas de ecuaciones interdependientes (SUR) considerando restricciones presupuestarias.
*   **Econometría de Panel y EIV:** Contraste empírico de Modelos de Efectos Fijos (FE) y Efectos Aleatorios (RE) mediante el test de Hausman, sumado a la simulación visual y econométrica de Errores de Medición (EIV) para estimar primas de riesgo en portafolios.
*   **Análisis Predictivo de Vivienda:** Incorporación de un dataset real de más de 76,000 registros (2015-2024) sobre créditos hipotecarios en México. Implementación de visualizaciones interactivas y preparación del entorno para predecir el comportamiento crediticio usando validación cruzada y métricas de error (MSE).

### 5. Pipeline Predictivo y EDA Interactivo de Créditos Hipotecarios
**Archivo:** `Reporte_5_Predictivo_Vivienda_v2.ipynb`
*   **Gestión de Datos:** Ingesta del dataset de créditos de vivienda asegurada, tratamiento de valores nulos y eliminación de registros duplicados garantizando una base íntegra de 76,526 observaciones.
*   **Visualización Interactiva (EDA):** Desarrollo de histogramas dinámicos con `Plotly` para analizar las distribuciones de variables clave, como los plazos de crédito en meses.
*   **Configuración del Entorno ML:** Preparación del pipeline integrando librerías de regresión y validación de `scikit-learn` junto con los estimadores estructurales de `linearmodels` (IV/Panel) para entrenamiento y prueba.
