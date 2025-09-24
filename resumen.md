# Guía de Preparación para la Certificación AWS Certified AI Practitioner

A continuación se detalla la información necesaria para prepararse para la certificación AWS Certified AI Practitioner, organizada según los dominios del examen.

---

## Dominio 1: Fundamentos de la IA y el Machine Learning (20% del examen)

Este dominio abarca los conceptos, la terminología y los casos de uso fundamentales de la IA y el ML, así como el ciclo de vida del desarrollo de ML.

### Conceptos y Terminología Básica de la IA

- **Inteligencia Artificial (IA):** Campo amplio enfocado en crear sistemas que realizan tareas que requieren inteligencia humana.
- **Machine Learning (ML):** Subcampo de la IA que permite a los sistemas aprender de los datos sin ser programados explícitamente.
- **Aprendizaje Profundo:** Subcampo del ML que utiliza redes neuronales con múltiples capas para aprender de grandes cantidades de datos.
- **Redes Neuronales:** Modelos computacionales inspirados en el cerebro humano, utilizados en el aprendizaje profundo.
- **Procesamiento del Lenguaje Natural (PLN):** Rama de la IA que se ocupa de la interacción entre computadoras y lenguaje humano.
- **Visión por Computadora:** Campo de la IA que permite a las computadoras "ver" e interpretar el contenido de imágenes y videos.
- **Modelos y Algoritmos:** Los algoritmos son los procedimientos que se ejecutan en los datos para crear un modelo de ML.
- **Entrenamiento e Inferencia:** El entrenamiento es el proceso de enseñar a un modelo utilizando un conjunto de datos, mientras que la inferencia es el uso del modelo entrenado para hacer predicciones. La inferencia puede ser por lotes o en tiempo real.

#### Tipos de Aprendizaje

- **Supervisado:** El modelo aprende a partir de datos etiquetados.
- **No supervisado:** El modelo aprende de datos no etiquetados para encontrar patrones.
- **Por refuerzo:** El modelo aprende a través de la prueba y el error para lograr un objetivo.

#### Tipos de Datos
Los modelos de IA utilizan diversos tipos de datos, como etiquetados, no etiquetados, tabulares, de series temporales, de imágenes, de texto, estructurados y no estructurados.

---

### Casos de Uso de la IA

La IA y el ML pueden aportar valor en diversas aplicaciones, incluyendo la ayuda en la toma de decisiones humanas, la escalabilidad de soluciones y la automatización.  
**Ejemplos:** sistemas de recomendación, detección de fraudes, reconocimiento de voz.  
Es crucial determinar cuándo las soluciones de IA no son apropiadas, por ejemplo, cuando el análisis de costo-beneficio no es favorable.

---

### Ciclo de Vida del Desarrollo de ML

1. **Recopilación y preprocesamiento de datos.**
2. **Ingeniería de características.**
3. **Entrenamiento y ajuste de hiperparámetros del modelo.**
4. **Evaluación, implementación y monitoreo del modelo.**

---

### Operaciones de Machine Learning (MLOps)

MLOps son prácticas para implementar y mantener modelos de ML en producción de manera confiable y eficiente. Incluye:

- **Experimentación:** Gestión estructurada del ciclo de vida del ML (seguimiento de experimentos, versiones, flujos de trabajo automatizados, colaboración y escalabilidad). CI/CD es esencial.
- **Procesos repetibles:** Automatización y estandarización para garantizar consistencia y eficiencia.
- **Sistemas escalables:** Capaces de gestionar demandas crecientes, modelos complejos y grandes volúmenes de datos.
- **Monitoreo y reentrenamiento:** Vigilancia continua para mantener el rendimiento. La deriva del modelo requiere reentrenamiento con datos nuevos. AWS recomienda automatizar este proceso.

---

### Métricas de Rendimiento del Modelo

- **Exactitud:** Proporción de predicciones correctas.
- **Puntuación F1:** Media armónica de precisión y recall (útil para datos desequilibrados).  
  $$F1 = 2 \times \frac{Precisión \times Recall}{Precisión + Recall}$$
- **AUC (Área bajo la curva ROC):** Evalúa el rendimiento de un clasificador en todos los umbrales de clasificación.
- **Métricas empresariales:** Impacto en el negocio, costos, retroalimentación de clientes, ROI.

---

## Dominio 2: Fundamentos de la IA Generativa (24% del examen)

Se centra en conceptos, capacidades, limitaciones e infraestructura para construir aplicaciones de IA generativa.

### Conceptos Básicos de la IA Generativa

- **IA Generativa:** Crea contenido nuevo (texto, imágenes, música).
- **Tokens:** Unidades de texto (palabras, partes de palabras o caracteres) procesadas por modelos generativos.
- **Fragmentación (Chunking):** Divide grandes documentos en secciones pequeñas para procesamiento eficiente.
- **Incrustaciones (Embeddings):** Representaciones numéricas de objetos del mundo real para comprensión compleja.
- **Vectores:** Representaciones numéricas que capturan relaciones/propriedades de los datos.
- **Peticiones (Prompts) e Ingeniería de Peticiones:** Textos en lenguaje natural que solicitan tareas a la IA; la ingeniería de peticiones optimiza su calidad.
- **Modelos de Lenguaje Grandes (LLM) basados en Transformadores:** Arquitectura que comprende relaciones entre palabras en secuencias.
- **Modelos Fundacionales (FM):** Grandes redes neuronales entrenadas en datos masivos como punto de partida para ML.
- **Modelos Multimodales:** Manejan e integran datos de diferentes modalidades (texto, imagen, audio).
- **Modelos de Difusión:** Producen imágenes fotorrealistas a partir de texto/imágenes usando ruido gaussiano y difusión inversa.

---

### Capacidades y Limitaciones de la IA Generativa

**Ventajas:**
- Adaptabilidad
- Capacidad de respuesta
- Simplicidad

**Desventajas:**
- Alucinaciones (resultados no basados en datos del mundo real)
- Interpretabilidad limitada ("caja negra")
- Inexactitud
- Falta de determinismo (distintos resultados con la misma entrada)

---

### Creación de Aplicaciones de IA Generativa con AWS

AWS ofrece servicios y herramientas como Amazon SageMaker JumpStart, Amazon Bedrock y Amazon Q. La infraestructura AWS aporta seguridad, cumplimiento y responsabilidad.

---

## Dominio 3: Aplicaciones de los Modelos Fundacionales (28% del examen)

Cubre el ciclo de vida de los modelos fundacionales: selección de datos, entrenamiento, ajuste y evaluación.

### Ciclo de Vida de los Modelos Fundacionales

1. **Selección de Datos:** Calidad y diversidad impactan el rendimiento.
2. **Selección del Modelo:** Considerar personalización, tamaño, latencia, licencias.
3. **Entrenamiento Previo:** Preparación del modelo con datos diversos y de alta calidad.
4. **Ajuste (Fine-Tuning):** Entrenamiento adicional en datos relevantes y específicos.
5. **Evaluación:** Verificar que los modelos cumplen estándares.
6. **Implementación:** Puesta en producción y configuración de infraestructura.
7. **Retroalimentación:** Recopilación y análisis para mejorar el modelo.

---

### Consideraciones de Diseño y Técnicas de Ingeniería de Peticiones

- **Generación Aumentada por Recuperación (RAG):** Mejora respuestas conectando el modelo a fuentes de conocimiento externas y actualizadas.

#### Técnicas de Ingeniería de Peticiones

- **Chain-of-thought:** Guía al modelo por pasos intermedios de razonamiento.
- **Zero-shot:** El modelo realiza tareas sin ejemplos previos.
- **One-shot/Few-shot:** Se le da uno o varios ejemplos para guiar la respuesta.

---

### Evaluación del Rendimiento de los Modelos Fundacionales

- **Evaluación humana y benchmarks.**
- **Métricas específicas:** ROUGE (Recall-Oriented Understudy for Gisting Evaluation) y BLEU (Bilingual Evaluation Understudy).

---

## Dominio 4: Directrices para una IA Responsable (14% del examen)

Se enfoca en el desarrollo y uso ético y responsable de la IA.

### Características de una IA Responsable

- **Equidad y Sesgo:** Evitar perpetuar sesgos injustos. Herramientas como Amazon SageMaker Clarify ayudan a detectarlos y mitigarlos.
- **Inclusividad:** Accesible y beneficiosa para todos los usuarios.
- **Solidez y Seguridad:** Sistemas fiables, seguros y resistentes a ataques.
- **Veracidad:** Proporcionar información precisa y fiable.
- **Transparencia y Explicabilidad:** Comprender cómo los modelos toman decisiones. Las tarjetas de modelo de SageMaker favorecen la transparencia.

---

## Dominio 5: Seguridad, Cumplimiento y Gobernanza para Soluciones de IA (14% del examen)

Protección, cumplimiento normativo y gobernanza de datos en sistemas de IA.

### Seguridad de los Sistemas de IA

- Proteger contra amenazas (inyección de peticiones, envenenamiento de datos, apropiación/jailbreak).
- Servicios de AWS: roles de IAM, cifrado, AWS PrivateLink.

### Gobernanza y Cumplimiento

- **Citación de Fuentes y Linaje de Datos:** Documentar el origen de los datos para transparencia y trazabilidad (tarjetas de modelo, catalogación).
- **Estándares de Cumplimiento:** Cumplir normativas como ISO y SOC. Herramientas: AWS Audit Manager, AWS Artifact.
- **Estrategias de Gobernanza de Datos:** Registro, residencia, monitoreo, observación, retención y ciclos de vida de los datos.

---
