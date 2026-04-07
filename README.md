# Ev1_grupo_5
Entregables evaluacion 1 - Programacion para ciencia de datos

análisis y Retención de Clientes  - Servicio de Suscripción Digital

Descripción del Proyecto
Este proyecto aborda un problema crítico de negocio: el aumento en la tasa de cancelación de usuarios en una empresa de servicios digitales por suscripción. 

A través de un flujo de trabajo completo de Ciencia de Datos, este repositorio documenta la limpieza, transformación y análisis exploratorio de un conjunto de datos multidimensional. El objetivo es procesar variables demográficas, económicas y de comportamiento para entender los motivos de fuga, identificar perfiles de riesgo y dejar la información lista para el entrenamiento de modelos predictivos avanzados.

Hallazgos Estratégicos
Durante el análisis exploratorio, se descubrieron datos claves para el negocio:
- Foco principal de abandono: El 45% de las cancelaciones provienen de usuarios suscritos al Plan Básico.
- Identificación de Perfiles Críticos: Se detectó un "perfil paradójico" de 1.983 clientes que hacen un uso intensivo de la App, pero cuya deuda supera sus ingresos mensuales, requiriendo acción inmediata.
- Viabilidad Algorítmica: Se determinó que las correlaciones lineales individuales con el abandono son casi nulas (~0.01), lo que fundamenta la transición directa hacia algoritmos de ensamble no lineales (como Random Forest o XGBoost) para futuras predicciones.

Tecnologías Utilizadas
- Lenguaje: Python 3.0
- Análisis y Manipulación: Pandas, NumPy
-  Visualización:  Matplotlib
- Machine Learning (Preparación): Scikit-Learn
- Entorno: Jupyter Notebook / Google Colab


Cómo Ejecutar el Proyecto localmente
El cuaderno principal está diseñado para ejecutarse de manera secuencial (de arriba hacia abajo). Documenta el flujo de trabajo completo desde la ingesta de datos hasta el análisis exploratorio. 

A continuación, se detalla el paso a paso metodológico implementado en el código:

Paso 1: Configuración del Entorno y Carga Inicial
* Importación de Librerías: El script inicia cargando las dependencias fundamentales para la manipulación y visualización de datos (`pandas`, `numpy`, `matplotlib`, `seaborn` y herramientas de `scikit-learn`).
* Ingesta de Datos: Se realiza la lectura del archivo crudo `dataset_clientes.csv` importado desde github mediante un dataframe de Pandas, estableciendo la base para la auditoría inicial.

Paso 2: Auditoría y Limpieza Crítica
* Tratamiento de Identificadores: Se detectan y eliminan registros duplicados en la variable `id_cliente` para asegurar la unicidad de las observaciones.
* Gestión de Valores Nulos: Se aplica un método de imputación estratégica sobre los campos con datos faltantes (específicamente en `gasto_mensual`), utilizando medidas de tendencia central calculadas a partir de la distribución de los datos existentes para no sesgar el análisis.

Paso 3: Tratamiento de Valores Atípicos (Outliers)
* Análisis de Distribución: Se abordan las variables numéricas con el objetivo de comprender la distribución real de sus datos, identificando visual y estadísticamente la presencia de valores extremos que se escapan del comportamiento normal.
* Mitigación: Se aplica la técnica de Winsorización para limitar o "tapar" estos outliers en los extremos de la distribución. Esto permite contener la distorsión de los datos sin la necesidad de eliminar registros, evitando sesgos tanto en el análisis exploratorio como en el futuro entrenamiento algorítmico.

Paso 4: Transformación y Codificación (Feature Engineering)
* Encoding de Categóricas: Dado que los modelos predictivos requieren entradas matemáticas, se transforman las variables de texto (como `tipo_plan`, `genero`, `region`). El código aplica técnicas de codificación para vectorizar estas características sin perder su valor informativo.

Paso 5: Análisis Exploratorio de Datos (EDA)
* Cálculo de Correlaciones: La fase final del código ejecuta una matriz de correlación de Pearson sobre el dataset limpio. 
* Evaluación de Resultados: El código genera las visualizaciones que respaldan la conclusión principal del informe: la relación lineal entre las variables predictoras y la variable objetivo (`abandono`) es mínima (aprox. 0.01), validando la necesidad técnica de escalar el proyecto hacia modelos de ensamble no lineales.


Equipo de Trabajo
Diego Améstica
Agustín Cáceres
Dante Rodríguez
