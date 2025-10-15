# Guía de Estudio: Directrices para la IA Responsable — Dominio 4

Este documento resume los conceptos esenciales para el desarrollo de sistemas de IA responsables, la importancia de la transparencia y las herramientas de AWS que ayudan a implementar estas prácticas, basándose en la transcripción proporcionada.

## Tabla de contenidos
- [4.1 Desarrollo de Sistemas de IA Responsable 🛡️](#41-desarrollo-de-sistemas-de-ia-responsable-🛡️)  
  - [El desafío del sesgo y la fiabilidad](#el-desafío-del-sesgo-y-la-fiabilidad)  
  - [Amazon SageMaker Clarify](#amazon-sagemaker-clarify)  
  - [Métricas de sesgo clave](#métricas-de-sesgo-clave)  
  - [Riesgos específicos de la IA generativa](#riesgos-específicos-de-la-ia-generativa)  
  - [Herramientas de mitigación en AWS](#herramientas-de-mitigación-en-aws)  
- [4.2 Modelos Transparentes y Explicables 🔍](#42-modelos-transparentes-y-explicables-🔍)  
  - [Fomentando la transparencia](#fomentando-la-transparencia)  
  - [Herramientas para la explicabilidad](#herramientas-para-la-explicabilidad)  
  - [Diseño centrado en el ser humano](#diseño-centrado-en-el-ser-humano)  

---

## 4.1 Desarrollo de Sistemas de IA Responsable 🛡️

Esta sección aborda cómo construir sistemas de IA justos y fiables, identificando y mitigando sesgos y riesgos.

### El desafío del sesgo y la fiabilidad
- Sesgo (Bias): desequilibrios en los datos o diferencias de rendimiento de un modelo entre distintos grupos.  
  - Un conjunto de datos desequilibrado puede provocar errores y predicciones inexactas para ciertos grupos.

### Amazon SageMaker Clarify
Amazon SageMaker Clarify es la herramienta clave de AWS para mitigar sesgos. Ayuda a:
- Detectar sesgos:
  - Antes del entrenamiento (en los datos).
  - Después del entrenamiento.
  - En modelos ya desplegados.
- Mejorar la explicabilidad: trata el modelo como "caja negra" para determinar la importancia relativa de cada característica en una predicción.

### Métricas de sesgo clave
SageMaker Clarify mide diferentes tipos de sesgo, por ejemplo:
- Disparidad demográfica: indica si un grupo tiene una proporción de resultados negativos mayor que la de resultados positivos.
- Diferencia de exactitud: mide la diferencia en la precisión del modelo entre distintas clases o grupos.
- Igualdad de trato: evalúa si la proporción de falsos negativos y falsos positivos difiere entre clases (puede indicar sesgo aun cuando la exactitud global sea similar).

### Riesgos específicos de la IA generativa
- Alucinaciones: el modelo inventa información que parece real pero es falsa; puede tener consecuencias graves (ej.: citas o hechos fabricados).
- Derechos de autor y propiedad intelectual: obras generadas por IA pueden no ser protegibles por derechos de autor; además, los modelos pueden generar contenido derivado de material protegido con el que fueron entrenados.
- Resultados discriminatorios: sesgos en los modelos pueden llevar a trato injusto y riesgos legales (ej.: sistemas de selección de personal que discriminan por edad).
- Contenido tóxico: modelos pueden generar contenido ofensivo, dañino u obsceno si tales ejemplos estuvieron en sus datos de entrenamiento.
- Privacidad de los datos: PII u otra información confidencial presente en datos de entrenamiento o en peticiones puede filtrarse en las salidas del modelo.

### Herramientas de mitigación en AWS
- Barreras de protección en Amazon Bedrock (Guardrails):  
  - Configuración de filtros que bloquean contenido inapropiado en peticiones y respuestas.  
  - Definición de umbrales para temas como odio, insultos, contenido sexual y violencia, o bloqueo total de determinados temas.
- Evaluación de LLMs con SageMaker Clarify: permite comparar modelos en dimensiones clave para asegurar fiabilidad:
  - Estereotipos: probabilidad de que el modelo reproduzca sesgos (raza, género, religión, etc.).
  - Toxicidad: detección de contenido ofensivo, grosero, odioso o agresivo.
  - Conocimiento fáctico: comprobación de veracidad de las respuestas.
  - Solidez semántica: evaluación de si pequeñas alteraciones en la entrada (errores tipográficos, espacios) cambian el resultado.
  - Exactitud: comparación del resultado del modelo con respuestas esperadas.

---

## 4.2 Modelos Transparentes y Explicables 🔍

Esta sección se centra en la importancia de entender cómo funcionan los modelos de IA y en herramientas que promueven la confianza y la participación humana.

### Fomentando la transparencia
- Software de código abierto:  
  - El desarrollo abierto maximiza la transparencia porque el funcionamiento interno es público.  
  - La diversidad de desarrolladores ayuda a detectar y reducir sesgos.  
  - Nota: algunas empresas limitan el uso por motivos de seguridad.
- Tarjetas de Servicio de IA de AWS (AI Service Cards):  
  - Documentos que centralizan información sobre el uso responsable de servicios de IA (ej.: Amazon Rekognition, Textract, Titan).  
  - Incluyen casos de uso previstos, limitaciones y mejores prácticas.
- Fichas de modelo de SageMaker (SageMaker Model Cards):  
  - Permiten documentar el ciclo de vida de los modelos (detalles de entrenamiento, conjuntos de datos, contenedores usados).

### Herramientas para la explicabilidad
- SageMaker Clarify (explicabilidad):  
  - Valores de Shapley (SHAP): asignan una puntuación a cada característica para determinar su contribución a la predicción.  
  - Gráficos de dependencia parcial: muestran cómo varían las predicciones al cambiar el valor de una característica específica (p. ej., edad).

### Diseño centrado en el ser humano
- IA centrada en el ser humano: enfoque de diseño que prioriza necesidades y valores humanos; busca mejorar capacidades humanas en lugar de reemplazarlas. Involucra colaboración multidisciplinaria (psicólogos, especialistas en ética, etc.).
- Amazon Augmented AI (A2I): servicio que incorpora revisión humana en el flujo de trabajo de la IA:
  - Permite enviar predicciones con baja confianza (o muestras aleatorias para auditoría) a revisores humanos antes de entregarlas al cliente.
- Aprendizaje por Refuerzo a partir de la Retroalimentación Humana (RLHF):  
  - Técnica para alinear modelos de lenguaje con preferencias humanas.  
  - Consiste en entrenar un "modelo de recompensa" con clasificaciones humanas y luego ajustar el LLM para maximizar la puntuación de dicho modelo de recompensa.
- Amazon SageMaker Ground Truth: puede usarse para recopilar las preferencias humanas necesarias para entrenar el modelo de recompensa en RLHF.

---
