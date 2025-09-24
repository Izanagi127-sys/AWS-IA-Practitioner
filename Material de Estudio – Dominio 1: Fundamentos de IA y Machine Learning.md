# AWS Certified AI Practitioner  
**Material de Estudio – Dominio 1: Fundamentos de IA y Machine Learning**

---

## Índice

1. [Introducción](#introducción)
2. [Enunciados de Tarea](#enunciados-de-tarea)
    - [1.1 Conceptos y Terminología Básica de IA](#11-conceptos-y-terminología-básica-de-ia)
    - [1.2 Casos Prácticos de Uso de IA](#12-casos-prácticos-de-uso-de-ia)
    - [1.3 Ciclo de Vida del Desarrollo de ML](#13-ciclo-de-vida-del-desarrollo-de-ml)
3. [Glosario Detallado](#glosario-detallado)
4. [Referencias y Recursos Adicionales](#referencias-y-recursos-adicionales)

---

## Introducción

Este material de estudio cubre el **Dominio 1** de la certificación AWS Certified AI Practitioner, que aborda los fundamentos de la Inteligencia Artificial (IA) y el Machine Learning (ML). El dominio está dividido en tres enunciados de tareas principales, que se detallan a continuación.

---

## Enunciados de Tarea

### 1.1 Conceptos y Terminología Básica de IA

- **Inteligencia Artificial (IA)**  
  Campo de la informática dedicado a resolver problemas cognitivos asociados a la inteligencia humana, como el aprendizaje, la creación y el reconocimiento de imágenes.
- **Machine Learning (ML)**  
  Rama de la IA centrada en el uso de datos y algoritmos para imitar la forma en que aprenden los humanos, identificando patrones y haciendo predicciones.
- **Aprendizaje Profundo (Deep Learning)**  
  Tipo de ML que utiliza redes neuronales con múltiples capas para procesar información, inspiradas en el cerebro humano.

#### Ejemplos de Aplicaciones de IA

- Chatbots (Alexa, ChatGPT)
- Detección de fraudes en tiempo real
- Supervisión y mantenimiento predictivo en manufactura
- Recomendaciones de productos
- Diagnóstico médico asistido por IA
- Traducción automática y procesamiento de lenguaje natural

#### Tipos de Datos en ML

- **Datos estructurados:** Tablas, bases de datos relacionales (Amazon RDS, Redshift)
- **Datos semiestructurados:** JSON, bases de datos NoSQL (DynamoDB, DocumentDB)
- **Datos no estructurados:** Imágenes, vídeos, textos libres
- **Series temporales:** Datos secuenciales con marcas temporales

#### Tipos de Aprendizaje en ML

- **Supervisado:** Entrenamiento con datos etiquetados
- **No supervisado:** Entrenamiento con datos no etiquetados
- **Por refuerzo:** Aprendizaje basado en recompensas por acciones tomadas en un entorno

#### Problemas Comunes en ML

- **Sobreajuste:** El modelo funciona bien con los datos de entrenamiento pero mal con datos nuevos
- **Subajuste:** El modelo no logra aprender patrones significativos
- **Sesgo:** El modelo favorece o desfavorece ciertos grupos debido a los datos de entrenamiento

---

### 1.2 Casos Prácticos de Uso de IA

- Automatización de tareas repetitivas
- Detección de fraudes y anomalías
- Recomendaciones personalizadas (Discovery, TicketEk, Pinterest, Booking.com)
- Chatbots y asistentes virtuales (Amazon Lex, DoorDash)
- Reconocimiento facial y procesamiento de imágenes (Amazon Rekognition)
- Extracción de texto y análisis de sentimientos (Amazon Textract, Comprehend)
- Traducción automática (Amazon Translate)
- Detección de actividades fraudulentas (Amazon Fraud Detector)
- IA generativa (Amazon Bedrock)

#### Cuando NO Usar IA

- Cuando el coste supera los beneficios esperados
- Cuando se requiere interpretabilidad total de las decisiones
- Problemas donde sistemas deterministas o basados en reglas son suficientes

---

### 1.3 Ciclo de Vida del Desarrollo de ML

**Fases:**
1. Definición del problema y objetivos empresariales
2. Recopilación y preparación de datos (ETL, AWS Glue, DataBrew)
3. Entrenamiento y ajuste de modelos (SageMaker, Experimentos, Hiperparámetros)
4. Evaluación de modelos (exactitud, precisión, exhaustividad, puntuación F1, AUC, MSE, RMSE)
5. Despliegue de modelos (por lotes, tiempo real, asincrónico, sin servidor)
6. Supervisión y mantenimiento del modelo (Model Monitor, MLOps, SageMaker Pipelines)
7. Métricas empresariales y retorno de inversión

---

## Glosario Detallado

- **IA (Inteligencia Artificial):**
  - **Definición:** Campo de la informática que busca crear sistemas capaces de realizar tareas que requieren inteligencia humana, como aprender, razonar, reconocer patrones, procesar lenguaje y tomar decisiones.
  - **Transcripción:** "La inteligencia artificial (IA) es el campo de la informática que se dedica a resolver problemas cognitivos que habitualmente se asocian con la inteligencia humana, como el aprendizaje, la creación y el reconocimiento de imágenes."
  - **Ejemplo:** Alexa responde preguntas; ChatGPT genera texto e imágenes.
  - [Referencia Oficial AWS](https://aws.amazon.com/what-is/artificial-intelligence/)

- **ML (Machine Learning):**
  - **Definición:** Rama de la IA que se enfoca en el desarrollo de algoritmos y modelos para que los sistemas aprendan a partir de datos, sin instrucciones explícitas para cada tarea.
  - **Transcripción:** "El machine learning es una rama de la IA... se centra en el uso de datos y algoritmos para imitar la forma en que aprenden los humanos."
  - **Ejemplo:** Recomendaciones de productos en tiendas online según tu historial de compras.
  - [Referencia Oficial AWS](https://aws.amazon.com/what-is/machine-learning/)

- **Deep Learning (Aprendizaje Profundo):**
  - **Definición:** Subcampo de ML que utiliza redes neuronales artificiales con muchas capas (deep = profundo) para aprender de grandes cantidades de datos complejos, como imágenes, audio y lenguaje natural.
  - **Transcripción:** "El aprendizaje profundo es un tipo de modelo de machine learning que se inspira en el cerebro humano y que utiliza capas de redes neuronales para procesar la información."
  - **Ejemplo:** Reconocimiento de voz, clasificación de imágenes, traducción automática.
  - [Transformers y modelos generativos](https://aws.amazon.com/what-is/transformers-in-artificial-intelligence/)
  - [Modelos de lenguaje extensos](https://aws.amazon.com/what-is/large-language-model/)

- **Inferencia:**
  - **Definición:** Es el proceso de generar una predicción usando un modelo de ML ya entrenado, con datos nuevos.
  - **Transcripción:** "Las predicciones que hace la IA se denominan inferencias. Ten en cuenta que una inferencia es básicamente una conjetura fundamentada."
  - **Ejemplo:** Pronosticar cuántos clientes estarán en una tienda en un día determinado usando datos históricos.
  - [Referencia AWS](https://docs.aws.amazon.com/sagemaker/latest/dg/deploy-model.html)

- **Características (Features):**
  - **Definición:** Son los atributos o variables de entrada que el modelo usa para aprender y hacer predicciones.
  - **Transcripción:** "Las características son como las columnas de una tabla o los píxeles de una imagen."
  - **Ejemplo:** Edad, ingresos, historial crediticio en un modelo para préstamos.
  - [Feature Store AWS](https://docs.aws.amazon.com/sagemaker/latest/APIReference/API_FeatureStore.html)

- **Hiperparámetros:**
  - **Definición:** Son parámetros externos definidos antes del entrenamiento que afectan el comportamiento y la eficacia del aprendizaje de un modelo.
  - **Transcripción:** "Cada algoritmo tiene un conjunto de parámetros externos que afectan a su rendimiento, que se conocen como hiperparámetros."
  - **Ejemplo:** Número de capas en una red neuronal, tasa de aprendizaje.
  - [Ajuste de hiperparámetros AWS](https://docs.aws.amazon.com/sagemaker/latest/dg/automatic-model-tuning.html)

- **Sobreajuste (Overfitting):**
  - **Definición:** Ocurre cuando el modelo aprende demasiado bien los datos del entrenamiento, incluso el ruido, perdiendo capacidad de generalizar a datos nuevos.
  - **Transcripción:** "Cuando un modelo funciona mejor con datos de entrenamiento que con datos nuevos, se denomina sobreajuste."
  - **Ejemplo:** Un modelo que reconoce sólo los peces del entrenamiento y falla al ver peces en ambientes distintos.
  - [Sobreajuste AWS](https://aws.amazon.com/what-is/overfitting/)

- **Subajuste (Underfitting):**
  - **Definición:** Cuando el modelo no logra captar patrones relevantes y arroja resultados inexactos tanto en el conjunto de entrenamiento como en datos nuevos.
  - **Transcripción:** "El subajuste es un tipo de error que se produce cuando el modelo no puede determinar una relación significativa entre los datos de entrada y de salida."
  - **Ejemplo:** Entrenar con pocos datos o poco tiempo y el modelo no aprende nada útil.

- **Sesgo (Bias):**
  - **Definición:** Tendencia del modelo a favorecer o discriminar grupos, debido a desequilibrios en los datos de entrenamiento o en las características usadas.
  - **Transcripción:** "El sesgo se produce cuando hay disparidades en el rendimiento de un modelo entre diferentes grupos."
  - **Ejemplo:** Un modelo que rechaza préstamos a mujeres jóvenes porque no recibió ejemplos de ese grupo en el entrenamiento.
  - [Mitigación de sesgo AWS](https://aws.amazon.com/blogs/publicsector/framework-mitigate-bias-improve-outcomes-new-age-ai/)

- **MLOps:**
  - **Definición:** Es la aplicación de prácticas DevOps a ML: automatización, control de versiones, monitoreo y retraining para mejorar la calidad, reproducibilidad y conformidad de los modelos.
  - **Transcripción:** "MLOps consiste en utilizar estas prácticas recomendadas... y aplicarlas al desarrollo de modelos de machine learning."
  - **Ejemplo:** Automatizar el reentrenamiento de modelos cada vez que llegan nuevos datos usando SageMaker Pipelines.
  - [MLOps AWS](https://aws.amazon.com/what-is/mlops/)

- **Clustering (Agrupamiento):**
  - **Definición:** Técnica de aprendizaje no supervisado donde el objetivo es agrupar datos en grupos (clusters) que sean similares entre sí.
  - **Transcripción:** "El análisis de clústeres es una clase de técnicas que se utilizan para clasificar los objetos de datos en grupos, denominados clústeres."
  - **Ejemplo:** Agrupar clientes por hábitos de compra.

- **Regresión:**
  - **Definición:** Problema de ML donde el objetivo es predecir un valor numérico continuo en función de una o varias variables de entrada.
  - **Transcripción:** "La regresión calcula el valor de la variable objetivo dependiente en función de una o varias variables o atributos que están correlacionados con ella."
  - **Ejemplo:** Predecir el precio de una vivienda según su ubicación y tamaño.

- **Clasificación:**
  - **Definición:** Problema de ML donde el objetivo es asignar una entrada a una categoría o clase. Puede ser binaria (dos clases) o multiclase (varias clases).
  - **Transcripción:** "La clasificación binaria asigna una entrada a una de las dos clases predefinidas y mutuamente excluyentes en función de sus atributos."
  - **Ejemplo:** Diagnóstico médico: ¿enfermo/sano?; Clasificación de correos: ¿spam/no spam?

- **AUC (Área bajo la curva ROC):**
  - **Definición:** Métrica que mide la capacidad de un modelo para distinguir entre clases. Valores cercanos a 1 indican buen desempeño; 0.5 indica un modelo aleatorio.
  - **Transcripción:** "El área que hay debajo la curva, que también se conoce como métrica AUC, se usa para comparar y evaluar la clasificación binaria mediante algoritmos que devuelven probabilidades."
  - **Ejemplo:** Evaluar un modelo para detectar fraudes comparando la tasa de verdaderos positivos vs. falsos positivos.

- **MSE (Error cuadrático medio):**
  - **Definición:** Métrica en regresión que calcula el promedio de los errores al cuadrado entre las predicciones del modelo y los valores reales; penaliza errores grandes.
  - **Transcripción:** "Para calcularlo, tomamos la diferencia entre la predicción y el valor real, elevamos la diferencia al cuadrado y, a continuación, calculamos el promedio de todas las diferencias cuadráticas."
  - **Ejemplo:** Medir el error al predecir precios de casas.

- **RMSE (Raíz del error cuadrático medio):**
  - **Definición:** Es la raíz cuadrada del MSE. Permite interpretar el error en las mismas unidades que la variable objetivo.
  - **Transcripción:** "La ventaja de usar esta raíz cuadrada del MSE es que las unidades coinciden con la variable dependiente."
  - **Ejemplo:** Si la variable es el precio en dólares, el RMSE también estará en dólares.

- **Puntuación F1 (F1 Score):**
  - **Definición:** Métrica que combina precisión y exhaustividad en un solo valor. Es útil para problemas donde es importante equilibrar ambos aspectos.
  - **Transcripción:** "La puntuación F1 equilibra la precisión y la exhaustividad al combinarlas en una sola métrica."
  - **Ejemplo:** Evaluar un modelo de detección de spam donde es importante detectar correos spam y no marcar legítimos como spam.

---

## Referencias y Recursos Adicionales

- [Marco para mitigar sesgo en IA](https://aws.amazon.com/blogs/publicsector/framework-mitigate-bias-improve-outcomes-new-age-ai/)
- [Transformers en IA](https://aws.amazon.com/what-is/transformers-in-artificial-intelligence/)
- [Sobreajuste en ML](https://aws.amazon.com/what-is/overfitting/)
- [Modelos extensos de lenguaje](https://aws.amazon.com/what-is/large-language-model/)
- [Servicios de IA en AWS](https://aws.amazon.com/ai/services/)
- [MLOps en AWS](https://aws.amazon.com/what-is/mlops/)
- [Workshop Machine Learning AWS](https://catalog.us-east-1.prod.workshops.aws/workshops/741835d3-a2bf-4cb6-81f0-d0bb4a62edca/en-US)
- [AWS Well-Architected Machine Learning Lens](https://docs.aws.amazon.com/wellarchitected/latest/machine-learning-lens/machine-learning-lens.html)

---

> **Consejo de estudio:**  
> Revisa cada definición, conecta la explicación con los ejemplos de la transcripción y consulta los enlaces de AWS para profundizar. Estas palabras y conceptos forman la base de todo el examen, y entenderlas te permitirá analizar cualquier pregunta de opción múltiple, caso práctico o escenario de certificación.
