# Proyecto Telecom X 

Diagnóstico Predictivo: Evasión de Clientes en Telecom X

## 1. Introducción

Telecom X enfrenta una tasa de churn elevada, lo que indica que una proporción significativa de clientes está cancelando sus contratos. La empresa aún no ha identificado claramente las causas, lo que limita su capacidad de respuesta.



## 2. Limpieza y Tratamiento de Datos

2.1. Importación de datos

  Se importó el archivo TelecomX_Data.json desde el repositorio de GitHub.

  Se utilizó pandas.read_json() para cargar el dataset en un DataFrame, asegurando una estructura tabular adecuada.

2.2 Exploración inicial

  Se revisaron las dimensiones del dataset, tipos de variables y valores únicos por columna.

  Se identificaron variables categóricas (Contract, PaymentMethod, InternetService, etc.) y numéricas (tenure, MonthlyCharges, etc.).

2.3 Tratamiento de valores nulos

  Se verificó la presencia de valores faltantes.

  En caso de valores nulos, se aplicaron estrategias como:

  Eliminación de registros incompletos si eran pocos.

  Imputación con moda o mediana según el tipo de variable.

2.4 Codificación de variables

  Se reemplazaron valores categóricos por binarios para facilitar el análisis:

  'Yes' → 1, 'No' → 0

  'Male' → 0, 'Female' → 1

  'No internet service' → 0, 'DSL' → 1, 'Fiber optic' → 1

  Se aplicó .replace() y .map() para mantener claridad y consistencia.

2.5 Normalización y transformación

  Para algunas variables numéricas como tenure o MonthlyCharges, se consideró la normalización si se requería para modelos predictivos.

  Se creó una versión binaria del dataset (datos_bin) para análisis de correlación y visualizaciones.

2.6 Verificación final

  Se revisó la integridad del dataset post-limpieza.

  Se validó que las variables estuvieran listas para análisis exploratorio, visualización y modelado.

## 3. Análisi Exploratorio

A partir del análisis exploratorio y los mapas de calor que construimos, se identifican correlaciones relevantes:

    VariableCorrelación con ChurnInterpretación claveContractAlta negativaClientes con contratos de largo plazo (1-2 años) tienen menor churn.tenureAlta negativaClientes con más meses de antigüedad tienden a     quedarse.InternetServiceModerada positivaUsuarios de fibra óptica presentan mayor churn que DSL.PaymentMethodModerada positivaMétodos como pago electrónico automático retienen más clientes.TechSupportModerada negativaClientes con soporte técnico activo tienen menor churn.SeniorCitizenLeve positivaClientes mayores presentan una ligera tendencia al churn.

3.1 Segmentos críticos con alta evasión

  Del análisis de gráficos y agrupaciones:

  Clientes con contrato mensual (Month-to-month) tienen la mayor tasa de churn.

  Usuarios sin dependientes ni pareja muestran mayor propensión a cancelar.

  Clientes sin servicios adicionales como OnlineSecurity, TechSupport, DeviceProtection son más vulnerables.

  Clientes con bajo tenure (menos de 12 meses) abandonan más rápido.

3.2 Modelo predictivo (en desarrollo)

  Se puede entrenar un modelo de clasificación (como Random Forest o XGBoost) con las variables codificadas para predecir la probabilidad de churn. Las variables más importantes según importancia de características serían:

  Contract

  tenure

  TechSupport

  PaymentMethod

  InternetService

  Esto permite segmentar clientes en riesgo y priorizar acciones.

## 4. Conclusiones e Insights

4.1 Factores clave de evasión

  Los clientes con contratos mensuales, sin servicios adicionales (como soporte técnico o backup online), y altos cargos mensuales presentan mayor probabilidad de cancelar.

  La antigüedad del cliente (tenure) es un predictor fuerte: los clientes nuevos son más propensos a abandonar.

4.2 Segmentos vulnerables

  Usuarios con servicio de fibra óptica y sin servicios complementarios muestran tasas elevadas de evasión.

  Clientes que no usan servicios como StreamingTV o StreamingMovies tienden a tener menor fidelización.

4.3 Insights accionables

  Ofrecer beneficios exclusivos a clientes con contratos mensuales puede incentivar la permanencia.

  Promover servicios adicionales como soporte técnico o almacenamiento en línea puede aumentar el valor percibido.

  Detectar clientes nuevos con cargos elevados y ofrecerles planes más accesibles o descuentos iniciales.

4.4 Impacto del análisis

  Permite anticipar cancelaciones mediante modelos predictivos.

  Facilita la segmentación inteligente para campañas de retención.

  Proporciona una base sólida para decisiones estratégicas en marketing, atención al cliente y diseño de productos.

** Recomendaciones:**

  Retención

  Incentivar contratos de largo plazo con descuentos o beneficios.

  Promover servicios complementarios como TechSupport y OnlineSecurity.

  Ofrecer programas de fidelización para clientes nuevos (primeros 6 meses).

  Atención personalizada

  Identificar clientes con alto riesgo (contrato mensual, sin servicios extra) y contactarlos proactivamente.

  Mejorar la experiencia de soporte técnico, especialmente para usuarios de fibra óptica.

  Optimización de pagos

  Fomentar el uso de métodos de pago automáticos, que correlacionan con menor churn.


Accede a los datos de la API
  
https://github.com/alura-cursos/challenge2-data-science-LATAM.git
