# 📘 Guía Intensiva AWS Certified AI Practitioner (AIF-C01)

## 🧭 Introducción

El examen AWS Certified AI Practitioner (AIF-C01) valida los conocimientos fundamentales sobre Inteligencia Artificial (IA), Machine Learning (ML) e IA generativa (GenAI) en el ecosistema AWS.

- **Duración:** 90 minutos
- **Preguntas:** 65 (de opción múltiple y respuesta múltiple)
- **Puntaje mínimo de aprobación:** 700/1000
- **Formato:** Escenario + selección de servicio / técnica adecuada
- **Lenguaje:** Inglés o español (con terminología inglesa en consola AWS)

---

### 🎯 Objetivos del examen

- Comprender los conceptos básicos de IA y ML.
- Identificar servicios de AWS usados en IA, ML e IA generativa.
- Aplicar principios de IA responsable y gobernanza.
- Conocer técnicas de prompt engineering, RAG, fine-tuning y evaluación de modelos.
- Reconocer los riesgos y buenas prácticas de seguridad y cumplimiento normativo.

---

## 🧩 Estructura por dominios

| Dominio                        | Descripción                           | Peso en el examen |
|------------------------------- |---------------------------------------|------------------|
| 1. Fundamentos de IA/ML        | Conceptos, ciclo de vida, métricas.   | 20 %             |
| 2. Fundamentos de IA generativa| LLM, FMs, prompting, inferencia.      | 24 %             |
| 3. Aplicaciones de FMs en AWS  | Uso práctico, servicios y parámetros. | 28 %             |
| 4. IA Responsable y Cumplimiento| Ética, sesgos, seguridad, privacidad.| 14 %             |
| 5. Casos prácticos de IA en AWS| Escenarios reales.                    | 14 %             |

---

## 🧠 1. Fundamentos de IA y Machine Learning

### 1.1 Conceptos esenciales

- **Inteligencia Artificial (AI):** sistemas que imitan funciones cognitivas humanas.
- **Machine Learning (ML):** subcampo de la IA que aprende patrones desde datos.
- **Deep Learning (DL):** usa redes neuronales profundas.
- **NLP (Natural Language Processing):** interpretación de texto y lenguaje humano.
- **Computer Vision (CV):** comprensión de imágenes y video.
- **Inferencia:** uso del modelo ya entrenado para generar predicciones.

### 1.2 Tipos de aprendizaje

| Tipo           | Descripción             | Ejemplo                          |
|----------------|------------------------|----------------------------------|
| Supervisado    | Datos etiquetados (entrada-salida). | Clasificación de correos spam.   |
| No supervisado | Agrupa sin etiquetas.   | Segmentación de clientes.        |
| Semisupervisado| Combinación.            | Reconocer objetos con pocos datos|
| Por refuerzo (RL)| Aprende por recompensas.| Robot que mejora su desempeño.   |

### 1.3 Ciclo de vida del ML

- **Recolección y limpieza de datos:** SageMaker Data Wrangler
- **Preparación y transformación:** SageMaker Processing
- **Entrenamiento:** SageMaker Training Job
- **Ajuste de hiperparámetros:** SageMaker Tuning
- **Evaluación y explicabilidad:** SageMaker Clarify
- **Implementación:** Endpoint en SageMaker Hosting
- **Monitoreo:** SageMaker Model Monitor

### 1.4 Métricas de rendimiento

| Métrica        | Tipo         | Qué mide                  | Interpretación              |
|----------------|-------------|---------------------------|-----------------------------|
| MAE            | Regresión    | Promedio de errores absolutos. | Error medio en unidades reales. |
| MAPE           | Regresión    | Error porcentual medio.   | % medio de desviación.      |
| RMSE           | Regresión    | Raíz del error cuadrático medio. | Penaliza grandes errores.   |
| Accuracy       | Clasificación| % total de aciertos.      | Mejor si hay equilibrio de clases. |
| Precision      | Clasificación| TP / (TP + FP).           | Exactitud de positivos.     |
| Recall         | Clasificación| TP / (TP + FN).           | Cuántos verdaderos positivos se detectan. |
| F1-Score       | Clasificación| Media armónica entre precision y recall. | Balance global.     |

### 1.5 Sesgo y Varianza

| Situación         | Sesgo | Varianza | Descripción                      |
|-------------------|-------|----------|----------------------------------|
| Underfitting      | Alto  | Bajo     | Modelo muy simple, no aprende.   |
| Óptimo            | Bajo  | Bajo     | Buen equilibrio, generaliza.     |
| Overfitting       | Bajo  | Alto     | Modelo memoriza datos de entrenamiento. |

### 1.6 Servicios de AWS en ML

| Servicio           | Función                           | Palabra clave en examen         |
|--------------------|-----------------------------------|---------------------------------|
| SageMaker Studio   | Entorno integral para ML.         | “Desarrollar modelos”           |
| Data Wrangler      | Limpieza de datos sin código.      | “Preparar datos”                |
| Ground Truth       | Etiquetar datos.                   | “Datos de entrenamiento etiquetados” |
| Clarify            | Explicabilidad y sesgo.            | “Bias / explain predictions”    |
| Model Monitor      | Detectar deriva en producción.     | “Monitorear rendimiento”        |
| Model Cards        | Documentar entrenamiento.          | “Auditoría / transparencia”     |
| Model Registry     | Versionar y aprobar modelos.       | “Revisión de modelos”           |

---

## 📘 Guía completa: Amazon SageMaker en el examen AWS Certified AI Practitioner

### 🧩 1. Ecosistema completo de SageMaker

| Servicio / Componente         | Propósito principal                                      | Palabra clave o pista de examen           | Cuándo usarlo                                                         | Nivel de sobrecarga operativa |
|-------------------------------|---------------------------------------------------------|-------------------------------------------|-----------------------------------------------------------------------|------------------------------|
| SageMaker Studio              | Entorno de desarrollo integrado (IDE) basado en la nube para todo el ciclo de ML. | “Plataforma unificada / entorno visual / interfaz Jupyter.” | Cuando un científico de datos necesita experimentar y construir modelos desde un mismo lugar. | Medio                        |
| SageMaker Canvas              | Herramienta no-code para crear modelos ML sin escribir código. | “Usuarios sin experiencia en codificación.” | Cuando el usuario no sabe programar pero debe entrenar modelos predicitvos. | Muy baja                     |
| SageMaker JumpStart           | Galería de modelos preentrenados y plantillas listas para usar. | “Comenzar rápidamente / usar modelos preentrenados.” | Cuando necesitas prototipar o probar modelos sin entrenar desde cero. | Baja                         |
| SageMaker Data Wrangler       | Limpieza, preparación y transformación de datos sin escribir código. | “Preparar / limpiar / transformar datos.” | Antes del entrenamiento, cuando faltan datos o hay valores atípicos.  | Baja                         |
| SageMaker Feature Store       | Almacén centralizado de features (variables) para reutilizarlas. | “Compartir características entre equipos.” | Cuando diferentes modelos necesitan los mismos atributos calculados.   | Media                        |
| SageMaker Training Jobs       | Entrenamiento de modelos ML en contenedores administrados. | “Entrenamiento de modelos / jobs distribuidos.” | Al entrenar un modelo personalizado (XGBoost, Scikit-learn, PyTorch). | Media                        |
| SageMaker Autopilot           | Entrenamiento automático (AutoML).                      | “Automatizar entrenamiento y selección de modelos.” | Cuando no se quiere elegir manualmente hiperparámetros o algoritmos.  | Muy baja                     |
| SageMaker Hyperparameter Tuning (Ajuste) | Busca los mejores hiperparámetros de un modelo.    | “Optimización / ajuste de hiperparámetros.” | Después de definir un modelo base, antes de su evaluación.            | Media                        |
| SageMaker Clarify             | Detecta sesgos y explica predicciones.                  | “Sesgo / explicabilidad / fairness.”       | Después del entrenamiento o durante el monitoreo de sesgo.             | Media                        |
| SageMaker Model Monitor       | Supervisa modelos en producción (drift, desempeño).     | “Detectar deriva de datos o concepto.”     | Cuando el modelo ya está implementado.                                 | Media                        |
| SageMaker Model Cards         | Documenta detalles de entrenamiento, datasets y métricas del modelo. | “Transparencia / auditoría / documentación.” | Para reportes de cumplimiento y trazabilidad.                          | Muy baja                     |
| SageMaker Model Registry      | Catálogo centralizado de versiones de modelos aprobados.| “Aprobación / control de versiones de modelos.” | Cuando varios equipos comparten modelos entre entornos.                | Media                        |
| SageMaker Pipelines           | Automatiza el flujo de trabajo de ML de principio a fin.| “Automatización / canalización ML / CI-CD.” | Cuando quieres reproducibilidad y control de etapas.                   | Alta                         |
| SageMaker Inference (Endpoints)| Hospeda modelos para inferencias en tiempo real o por lotes. | “Predicciones en vivo / tiempo real / batch.” | Cuando se despliega un modelo al entorno productivo.                   | Media                        |
| SageMaker Ground Truth        | Anotación y etiquetado de datos con asistencia humana.  | “Etiquetado de datos / anotaciones / intervención humana.” | Para generar datasets de entrenamiento supervisado.                     | Media                        |
| SageMaker Debugger            | Monitorea el entrenamiento para detectar cuellos de botella. | “Depurar / optimizar entrenamiento.”       | Durante la fase de entrenamiento intensivo.                             | Alta                         |
| SageMaker Studio Lab          | Versión gratuita reducida de Studio (para educación).   | “Aprendizaje o pruebas educativas gratuitas.” | Practicar o enseñar ML sin costo.                                      | Muy baja                     |

### 🧮 2. Fases del ciclo de vida de ML con SageMaker

| Fase                       | Herramientas de SageMaker                       | Objetivo                                     | Servicios relacionados      |
|----------------------------|-------------------------------------------------|----------------------------------------------|-----------------------------|
| Preparación de datos       | Data Wrangler, Feature Store, Ground Truth      | Limpieza, transformación, etiquetado.        | Amazon S3, Glue             |
| Entrenamiento y ajuste     | Training Jobs, Autopilot, Hyperparameter Tuning | Crear modelo óptimo.                         | EC2, ECR                    |
| Evaluación y explicabilidad| Clarify, Debugger                               | Validar métricas y evitar sesgos.            | Model Monitor               |
| Implementación / despliegue| Inference, Endpoints, Model Registry            | Publicar modelo en producción.               | Lambda, API Gateway         |
| Monitoreo y mejora continua| Model Monitor, Model Cards, Pipelines           | Detectar drift, registrar rendimiento.       | CloudWatch, CloudTrail      |

### ⚖️ 3. Comparación rápida con otros servicios de AWS

| Servicio            | Qué hace                                              | Cómo se diferencia de SageMaker                                  |
|---------------------|------------------------------------------------------|------------------------------------------------------------------|
| Amazon Bedrock      | Plataforma para modelos fundacionales (texto, imagen, IA generativa). | No entrena modelos desde cero; usa modelos preentrenados (Titan, Claude, Llama). |
| Amazon Comprehend   | Analiza texto (NLP).                                 | Servicio listo, no necesita entrenamiento. SageMaker se usa para modelos personalizados. |
| Amazon Rekognition  | Analiza imágenes y video.                            | Servicio ya entrenado, mientras que SageMaker permite entrenar modelos propios. |
| Amazon Personalize  | Recomendaciones personalizadas.                      | Solución específica preconstruida, no general.                   |
| Amazon Lex          | Chatbots y voz natural.                              | No requiere pipelines ni entrenamiento de ML manual.             |
| Amazon Q Business   | Chat empresarial con IA generativa sobre documentos internos. | Se basa en FMs (Bedrock), no en ML tradicional.                  |

### 🧰 4. Preguntas típicas del examen sobre SageMaker

| Pregunta (parafraseada)                                       | Respuesta correcta     | Justificación                          |
|---------------------------------------------------------------|-----------------------|----------------------------------------|
| “Un analista no sabe programar y debe crear un modelo predictivo.” | SageMaker Canvas      | No-code / interfaz visual.             |
| “Se quiere detectar sesgo en los datos o predicciones.”       | SageMaker Clarify     | Evaluación de equidad y sesgo.         |
| “Se requiere documentar los datos y rendimiento de un modelo para auditoría.” | Model Cards           | Transparencia y compliance.            |
| “Se necesita automatizar el pipeline de ML.”                  | SageMaker Pipelines   | CI/CD para flujos ML.                  |
| “Se quiere preparar y limpiar datos sin escribir código.”      | Data Wrangler         | Preparación visual.                    |
| “El modelo muestra desviación de datos en producción.”         | Model Monitor         | Detección de drift.                    |
| “Se quiere iniciar rápidamente con un modelo preentrenado.”    | JumpStart             | Plantillas y modelos listos.           |
| “Se quiere almacenar features calculadas para reutilizar.”     | Feature Store         | Reuso de características.              |
| “Se quiere compartir y aprobar modelos entrenados.”            | Model Registry        | Versionamiento de modelos.             |
| “Entrenamiento automático sin intervención humana.”            | Autopilot             | AutoML administrado.                   |

### 📊 5. Diagrama conceptual rápido

```
[ S3 ] → [ Data Wrangler / Ground Truth ] → [ Training Jobs / Autopilot ] 
      → [ Clarify + Debugger ] → [ Model Registry ] 
      → [ Inference Endpoint ] → [ Model Monitor ] → (retroalimenta datos a S3)
```

### 🧠 6. Claves de examen (memoria rápida)

| Clave                                   | Significado                    |
|-----------------------------------------|--------------------------------|
| “No-code” o “usuarios no técnicos”      | Canvas                         |
| “Sesgo o explicabilidad”                | Clarify                        |
| “Monitorear deriva o desempeño”         | Model Monitor                  |
| “Documentar rendimiento o cumplimiento” | Model Cards                    |
| “Pipelines automáticos”                 | Pipelines                      |
| “Preparar o limpiar datos”              | Data Wrangler                  |
| “Modelos preentrenados”                 | JumpStart                      |
| “Reutilizar características”            | Feature Store                  |
| “Etiquetado de datos”                   | Ground Truth                   |
| “Ajuste de hiperparámetros”             | Tuning                        |
| “Aprobación y versionamiento”           | Model Registry                 |

### 🧩 7. Diferencia entre Clarify, Model Monitor y Model Cards

| Servicio      | Foco                              | Etapa del ciclo de vida        | Ejemplo práctico                                |
|---------------|-----------------------------------|-------------------------------|-------------------------------------------------|
| Clarify       | Detección de sesgo y explicabilidad| Durante entrenamiento o evaluación | “Detectar si el modelo discrimina por género.”  |
| Model Monitor | Monitoreo continuo en producción  | Post-implementación           | “El modelo empieza a fallar con nuevos datos.”  |
| Model Cards   | Documentación y transparencia     | Después del despliegue / auditorías | “Registrar métricas y datasets usados.”     |

### 🧩 8. Mini-simulacro de SageMaker (5 preguntas)

1️⃣ ¿Qué componente usarías para crear un modelo sin escribir código?  
→ Canvas

2️⃣ ¿Qué herramienta sirve para limpiar datos antes del entrenamiento?  
→ Data Wrangler

3️⃣ ¿Qué componente detecta sesgo en los datos?  
→ Clarify

4️⃣ ¿Qué herramienta automatiza el flujo de ML de punta a punta?  
→ Pipelines

5️⃣ ¿Qué herramienta documenta rendimiento y datasets?  
→ Model Cards

---

## ⚙️ 2. Fundamentos de IA Generativa

### 2.1 Conceptos básicos

- **Modelo Fundacional (Foundation Model, FM):** entrenado con grandes volúmenes de datos y adaptable a múltiples tareas.
- **LLM (Large Language Model):** modelo de lenguaje de gran tamaño.
- **Token:** unidad mínima de texto procesada.
- **Ventana de contexto:** número máximo de tokens que el modelo puede procesar en una sola interacción.
- **Embeddings (Incorporaciones):** vectores numéricos que representan significado semántico.

### 2.2 Parámetros de inferencia

| Parámetro     | Qué controla            | Efecto                        |
|---------------|------------------------|-------------------------------|
| Temperatura   | Aleatoriedad / creatividad. | Alta = creativo; baja = preciso. |
| Top-K         | Número fijo de palabras candidatas. | Más alto → más diversidad.    |
| Top-P (Nucleus)| Probabilidad acumulada límite. | Controla variedad de salida.  |
| Max Tokens    | Longitud máxima de respuesta. | Limita tamaño del output.     |

### 2.3 Técnicas de prompting

| Técnica          | Descripción                    | Ejemplo                        |
|------------------|-------------------------------|--------------------------------|
| Zero-Shot        | Solo instrucción, sin ejemplos.| “Resume el texto en 3 frases.” |
| Few-Shot         | Incluye ejemplos previos.      | “Ejemplo 1: … Ejemplo 2: …”    |
| Chain-of-Thought (CoT)| Pide razonamiento paso a paso.| “Piensa paso a paso antes de responder.” |
| ReAct (Reason + Act)| Razonar y ejecutar acciones externas.| Buscar datos y luego responder. |
| RAG (Retrieval-Augmented Generation)| Consultar fuentes externas y generar.| Chatbot con documentos S3. |
| RLHF             | Ajuste con feedback humano.    | Mejorar tono o empatía.        |

### 2.4 Métodos de personalización

| Método                 | Descripción                       | Costo     | Uso recomendado           |
|------------------------|-----------------------------------|-----------|--------------------------|
| Prompt Engineering     | Ajustar la instrucción.           | Bajo      | Tareas simples.          |
| RAG                    | Añadir contexto externo.          | Medio     | Información actualizada. |
| Fine-Tuning            | Reentrenar con datos del dominio. | Alto      | Terminología específica. |
| Continual Pre-training | Extender vocabulario con datos nuevos. | Alto | Nuevos sectores.         |
| RLHF                   | Ajustar comportamiento con feedback humano. | Muy alto | Conversación natural.   |

### 2.5 Servicios de AWS para GenAI

| Servicio                   | Propósito                          | Clave en examen                |
|----------------------------|------------------------------------|--------------------------------|
| Amazon Bedrock             | Acceso a FMs (Titan, Claude, Cohere). | “IA generativa administrada”.  |
| Amazon Q Business / Developer| Chatbots empresariales y asistentes de código. | “Responder con datos internos”.|
| PartyRock                  | Laboratorio de práctica de prompts. | “Pruebas de GenAI sin código”. |

---

## 🧩 3. Aplicaciones de Modelos Fundacionales (FMs)

### 3.1 Diseño y parámetros de inferencia

Los FMs (Foundation Models) se adaptan a muchas tareas a través de sus parámetros de inferencia.  
Estos controlan el comportamiento del modelo durante la generación de texto, imagen o código.

| Parámetro     | Descripción                     | Impacto                       |
|---------------|--------------------------------|-------------------------------|
| Temperatura   | Controla la aleatoriedad.       | 0.1 = respuestas consistentes; 1.0 = creativas. |
| Top-K         | Limita a las K palabras más probables. | Menor K = más precisión.    |
| Top-P (nucleus)| Selecciona palabras cuya suma de probabilidad ≤ P. | Mejora coherencia.          |
| Max Tokens    | Longitud máxima de salida.      | Evita respuestas largas.      |
| Stop Sequences| Señales para detener generación.| “\n\n” o “### END ###”.       |

### 3.2 Ingeniería de peticiones (Prompt Engineering)

La petición (prompt) es la instrucción que guía al modelo.  
Un prompt efectivo tiene 4 componentes:

- **Contexto** — marco general o rol del modelo.
- **Instrucción** — acción solicitada.
- **Entrada** — datos o texto a procesar.
- **Formato de salida** — estructura esperada.

**Ejemplo:**

> Eres un analista de datos. Resume el siguiente informe en 3 puntos claros:  
> ---  
> [Texto del informe]  
> ---  
> Respuesta en formato JSON.

**Buenas prácticas:**

- Usa verbos claros (resume, explica, clasifica).
- Indica formato de salida (lista, JSON, tabla).
- Añade ejemplos (few-shot) cuando el modelo no comprende el estilo.
- Reafirma comportamiento: “Si no sabes, responde ‘No tengo datos suficientes’.”

### 3.3 Comparación de técnicas de prompting

| Técnica        | Fortalezas              | Debilidades                    |
|--------------- |------------------------|------------------------------- |
| Zero-Shot      | Rápido y flexible.      | Puede ser inconsistente.       |
| Few-Shot       | Mejora formato y estilo.| Usa más tokens.                |
| Chain of Thought| Explicaciones detalladas.| Mayor latencia.               |
| ReAct          | Combina pensamiento + acción.| Requiere herramientas externas.|
| RAG            | Contexto actualizado y factual.| Necesita base vectorial.     |

### 3.4 Fine-Tuning, RAG y RLHF — Diferencias

| Técnica         | Qué hace                                 | Cuándo usar                        |
|-----------------|------------------------------------------|------------------------------------|
| Fine-Tuning     | Ajusta pesos internos con datos etiquetados. | Cuando necesitas adaptar lenguaje técnico. |
| RAG             | Agrega contexto en tiempo real (sin reentrenar). | Cuando necesitas datos actualizados. |
| RLHF            | Ajusta comportamiento con feedback humano. | Cuando buscas tono empático o coherente. |

### 3.5 Evaluación de modelos generativos

**Automática:**

- ROUGE / BLEU: compara similitud entre textos generados y referencia.
- BERTScore: mide similitud semántica con embeddings.
- Perplejidad: mide qué tan plausible es un texto.

**Humana:**

- Coherencia
- Relevancia
- Fluidez
- Precisión factual

**Ejemplo:**

Un resumen con alto BLEU pero baja precisión factual indica buena redacción, pero posible alucinación.

---

## 🔐 4. Seguridad, Cumplimiento y Gobernanza

### 4.1 Conceptos clave

| Término                | Descripción                                         |
|------------------------|-----------------------------------------------------|
| PII (Personally Identifiable Information) | Datos que identifican a una persona (nombre, RUT, dirección, correo, etc.). |
| PHI (Protected Health Information)        | Información médica confidencial.           |
| GDPR / HIPAA           | Normas internacionales de protección de datos.      |
| Shared Responsibility Model | AWS gestiona la seguridad de la nube; el cliente, la seguridad en la nube.|

### 4.2 Servicios AWS de seguridad y cumplimiento

| Servicio          | Función                                        | Palabra clave         |
|-------------------|------------------------------------------------|-----------------------|
| AWS IAM           | Controla usuarios, roles, grupos y permisos.   | “Permisos / autenticación”. |
| Amazon Macie      | Detecta y clasifica datos sensibles en S3 (PII).| “Protección de datos”.|
| AWS KMS           | Cifrado en reposo y tránsito.                  | “Encriptación / llaves”.|
| AWS CloudTrail    | Registra todas las llamadas API.               | “Auditoría / logs”.   |
| AWS Artifact      | Documentación de cumplimiento (ISO, SOC, PCI). | “Compliance / evidencias”.|
| AWS Config        | Monitorea configuraciones y desviaciones.      | “Cumplimiento continuo”.|
| S3 Gateway Endpoint| Mantiene tráfico interno sin pasar por Internet.| “Seguridad / VPC”.   |

### 4.3 Gobernanza de IA

- **Residencia de datos:** mantener información en una región específica.
- **Retención y linaje:** trazabilidad de datos.
- **Control de acceso:** segmentar datos por nivel de usuario.
- **Generative AI Security Scoping Matrix:** herramienta AWS para clasificar riesgos de IA.

**Modelo de responsabilidad compartida aplicado a IA:**

| AWS                                 | Cliente                       |
|--------------------------------------|-------------------------------|
| Infraestructura segura, redes, hardware.| Entrenamiento, prompts, datos de entrada, gobernanza. |

---

## ⚖️ 5. IA Responsable

### 5.1 Principios fundamentales

| Principio        | Definición                               | Herramienta AWS             |
|------------------|------------------------------------------|-----------------------------|
| Equidad          | Sin sesgos ni discriminación.            | SageMaker Clarify           |
| Explicabilidad   | Entender cómo decide un modelo.          | Clarify / Model Cards       |
| Transparencia    | Registrar y documentar.                  | Model Cards / Artifact      |
| Solidez          | Comportamiento predecible y estable.     | Model Monitor               |
| Privacidad       | Proteger PII / PHI.                      | Macie / KMS                 |

### 5.2 Herramientas para IA responsable

| Herramienta               | Propósito                                        |
|---------------------------|--------------------------------------------------|
| SageMaker Clarify         | Detecta sesgo y explica decisiones.              |
| SageMaker Model Cards     | Documenta modelo, métricas y riesgos.            |
| Amazon A2I (Augmented AI) | Intervención humana en predicciones.             |
| Bedrock Guardrails        | Controla salida de modelos (bloqueo de temas sensibles).|
| AWS AI Service Cards      | Fichas públicas con transparencia sobre FM de AWS.|

### 5.3 Riesgos comunes

- **Alucinaciones:** respuestas falsas o inventadas.
- **Fuga de datos:** exposición accidental de información interna.
- **Sesgos:** resultados injustos o desbalanceados.
- **Uso indebido:** prompts maliciosos, jailbreaks.

**Cómo mitigarlos:**

- Reforzar contexto: usar RAG con fuentes verificadas.
- Reducir temperatura.
- Filtrar prompts e inyecciones.
- Revisar resultados con A2I o validación humana.

---

## 🤖 6. Servicios de IA en AWS (casos prácticos)

| Servicio             | Uso                               | Ejemplo típico                 |
|----------------------|-----------------------------------|------------------------------- |
| Amazon Bedrock       | IA generativa (texto, imagen, código). | Crear artículos o resúmenes.   |
| Amazon Q Business    | Asistente empresarial con datos internos.| Preguntar sobre políticas internas.|
| Amazon Lex           | Chatbot de texto/voz.             | Atención al cliente.           |
| Amazon Kendra        | Búsqueda semántica contextual.    | Buscar documentos técnicos.    |
| Amazon Comprehend    | Análisis de texto y sentimientos. | Clasificar opiniones.          |
| Amazon Textract      | Extraer texto de PDFs e imágenes. | Procesar facturas escaneadas.  |
| Amazon Rekognition   | Analizar imágenes, moderar contenido.| Detectar rostros o caricaturas.|
| Amazon Personalize   | Recomendaciones personalizadas.   | Sugerir productos o noticias.  |
| Amazon Transcribe    | Convertir audio a texto.          | Transcripciones automáticas.   |
| Amazon Polly         | Texto a voz natural.              | Generar audioguías.            |
| Amazon Translate     | Traducción automática.            | Documentos multilingües.       |

### 6.1 Casos de uso típicos de examen

| Escenario                              | Solución correcta      |
|-----------------------------------------|------------------------|
| “Analizar sentimientos en reseñas.”     | Amazon Comprehend      |
| “Buscar respuestas en documentos PDF.”  | Amazon Kendra          |
| “Extraer texto de tablas e imágenes.”   | Amazon Textract        |
| “Recomendaciones para usuarios.”        | Amazon Personalize     |
| “Chatbot conversacional.”               | Amazon Lex             |
| “Asistente con información de empresa.” | Amazon Q Business      |
| “Moderar imágenes o animaciones.”       | Amazon Rekognition     |
| “Generar texto o resumen.”              | Amazon Bedrock         |

---

## 🎯 7. Áreas Débiles Personalizadas (refuerzo intensivo)

Estas son las 5 áreas donde tus resultados de pre-test mostraron menor precisión. Cada sección incluye teoría extendida + mini-test con respuestas razonadas.

---

### 🧩 A. Evaluación y monitoreo de modelos

#### 1. Evaluar ≠ Monitorear

- **Evaluar →** Se hace después del entrenamiento (offline).
- **Monitorear →** Se hace en producción (online).

| Etapa       | Servicio           | Qué hace                       |
|-------------|--------------------|------------------------------- |
| Evaluación  | SageMaker Clarify  | Detecta sesgos, explica predicciones. |
| Documentación| Model Cards       | Resume entrenamiento, datos y métricas.|
| Monitoreo   | Model Monitor      | Detecta deriva de datos o precisión. |
| Auditoría   | AWS Artifact       | Guarda evidencias de cumplimiento.   |

#### 2. Deriva (Drift)

- **Data Drift:** distribución de entrada cambia.
- **Concept Drift:** relación entre entrada y salida cambia.
- **Label Drift:** proporción de clases cambia.

**Mini-test (respuestas al final)**

1️⃣ ¿Qué servicio detecta sesgo en un modelo?  
2️⃣ ¿Qué significa “concept drift”?  
3️⃣ ¿Qué herramienta genera un resumen auditable de entrenamiento?  
4️⃣ ¿Qué servicio registra las llamadas API a SageMaker?

*(Respuestas: 1-Clarify, 2-Cambio relación X→Y, 3-Model Cards, 4-CloudTrail).*

---

### 🧠 B. Prompt Engineering y RAG

#### 1. Diseño de prompts

**Estructura ideal:**

- Rol: Eres un asistente técnico experto en AWS.
- Instrucción: Explica la diferencia entre Bedrock y SageMaker.
- Formato: Responde en una tabla.

#### 2. Técnicas clave

| Técnica | Cuándo usar               | Ventajas            |
|---------|--------------------------|---------------------|
| Few-shot| Necesitas formato o tono fijo.| Mejora coherencia.|
| ReAct   | Debes razonar y consultar fuentes.| Reduce alucinaciones.|
| RAG     | Requieres datos actualizados.   | Mantiene factualidad.|

#### 3. Buenas prácticas

- Evita prompts ambiguos.
- Usa delimitadores claros (---).
- Reitera el formato esperado.
- Añade límites (“máx 100 palabras”).

**Mini-test**

1️⃣ ¿Qué técnica combina razonamiento y acción?  
2️⃣ ¿Qué método agrega contexto externo sin reentrenar?  
3️⃣ ¿Qué parámetro reduce creatividad excesiva?  
*(Respuestas: 1-ReAct, 2-RAG, 3-Temperatura baja).*

---

### 🔐 C. Seguridad y cumplimiento

#### 1. PII y PHI

- **PII:** datos personales (nombre, RUT, email).
- **PHI:** datos médicos protegidos.

| Requisito         | Servicio AWS   |
|-------------------|---------------|
| Detectar PII      | Amazon Macie  |
| Control de accesos| IAM           |
| Cifrado           | KMS           |
| Auditoría de llamadas | CloudTrail |
| Documentos de compliance | Artifact|

#### 2. Privacidad de red

- **Gateway Endpoint:** tráfico S3→EC2 sin salir a Internet.
- **PrivateLink:** conecta servicios VPC a VPC.

**Mini-test**

1️⃣ ¿Qué servicio detecta PII?  
2️⃣ ¿Cuál evita que datos S3 salgan a Internet?  
3️⃣ ¿Dónde obtener informes ISO y SOC?  
*(Respuestas: 1-Macie, 2-Gateway Endpoint, 3-Artifact).*

---

### 🤖 D. Servicios de IA Generativa (comparativa)

| Escenario                           | Servicio correcto  | Palabra clave        |
|------------------------------------- |-------------------|----------------------|
| Crear contenido textual, imagen, código| Amazon Bedrock   | “Generar”            |
| Chat empresarial con documentos internos| Amazon Q Business| “Datos corporativos” |
| Chatbot conversacional texto/voz     | Amazon Lex        | “Conversar”          |
| Búsqueda semántica contextual        | Amazon Kendra     | “Buscar información” |
| Analizar texto y sentimientos        | Comprehend        | “Opiniones”          |

**Claves de examen:**

- Si dice “mínima sobrecarga operativa” → servicio administrado (Bedrock, Lex, Q).
- Si dice “extraer texto de imágenes” → Textract.
- Si dice “moderar contenido visual” → Rekognition.

**Mini-test**

1️⃣ ¿Qué servicio genera texto?  
2️⃣ ¿Cuál modera caricaturas?  
3️⃣ ¿Cuál analiza sentimientos?  
*(Respuestas: 1-Bedrock, 2-Rekognition, 3-Comprehend).*

---

### ⚙️ E. Ciclo de vida del ML y canalizaciones

**Pipeline típico (SageMaker Pipelines):**  
1️⃣ Procesamiento → 2️⃣ Entrenamiento → 3️⃣ Ajuste → 4️⃣ Evaluación → 5️⃣ Implementación → 6️⃣ Monitoreo.

| Paso         | Acción           | Herramienta            |
|--------------|------------------|------------------------|
| Preprocesar  | Limpieza y features| Data Wrangler         |
| Entrenar     | Ajuste de parámetros| Training Jobs         |
| Tuning       | Hiperparámetros   | Automatic Model Tuning |
| Evaluar      | Métricas, sesgos  | Clarify                |
| Desplegar    | Endpoint          | Deploy Model           |
| Monitorear   | Drift             | Model Monitor          |

**Mini-test**

1️⃣ ¿En qué paso se aplica Clarify?  
2️⃣ ¿Qué sigue tras el entrenamiento?  
3️⃣ ¿Qué herramienta crea el endpoint?  
*(Respuestas: 1-Evaluación, 2-Evaluación/Despliegue, 3-SageMaker Deploy).*

---

## 🧪 8. Simulacro Final (20 preguntas tipo examen)

**Instrucciones:** intenta responder sin mirar notas (1 min por pregunta).  
Las respuestas correctas están al final de esta sección.

| #  | Pregunta                                                           | Opciones                    |
|----|---------------------------------------------------------------------|-----------------------------|
| 1  | ¿Qué servicio detecta sesgos y explica predicciones?                | A Clarify B Model Monitor C Ground Truth D Artifact |
| 2  | ¿Cuál reduce alucinaciones sin reentrenar el modelo?                | A Fine-Tuning B RAG C RLHF D Few-Shot              |
| 3  | ¿Qué controla la creatividad de un LLM?                             | A Top-K B Temperatura C Embeddings D Contexto      |
| 4  | ¿Qué servicio proporciona documentación de cumplimiento ISO/SOC?    | A CloudTrail B Artifact C Macie D IAM              |
| 5  | ¿Qué servicio es ideal para resumir correos electrónicos?           | A Comprehend B Bedrock C Textract D Lex            |
| 6  | En IA responsable, ¿qué herramienta genera fichas transparentes de modelos AWS?| A AI Service Cards B Guardrails C Clarify D A2I |
| 7  | ¿Qué tipo de aprendizaje usa etiquetas conocidas?                   | A No supervisado B Supervisado C Por refuerzo D Semisupervisado |
| 8  | ¿Qué parámetro afecta longitud de respuesta?                        | A Top-P B Tokens máx C Temperatura D Embeddings    |
| 9  | ¿Qué servicio genera voz natural desde texto?                       | A Transcribe B Comprehend C Polly D Translate      |
| 10 | ¿Qué herramienta integra humanos en el ciclo de revisión de IA?     | A A2I B Clarify C Model Monitor D Kendra           |
| 11 | ¿Qué define el “Shared Responsibility Model”?                       | A Distribución de seguridad entre AWS y cliente    |
| 12 | ¿Qué servicio recomienda productos personalizados?                  | A Personalize B Kendra C Lex D Textract            |
| 13 | ¿Cuál evita fuga de datos al mantener tráfico S3 interno?           | A VPC Endpoint B PrivateLink C Gateway Endpoint D Macie |
| 14 | ¿Qué modelo tiene sesgo bajo y varianza alta?                       | A Bien ajustado B Sobreajuste C Subajuste D Underfit |
| 15 | ¿Qué métrica mide error porcentual medio?                           | A MAE B MAPE C RMSE D F1                           |
| 16 | ¿Qué servicio detecta y modera imágenes explícitas?                 | A Rekognition B Bedrock C Textract D Comprehend    |
| 17 | ¿Qué técnica usa ejemplos previos en el prompt?                     | A Few-Shot B Zero-Shot C CoT D RAG                 |
| 18 | ¿Qué servicio analiza texto para detectar entidades?                | A Comprehend B Textract C Kendra D Bedrock         |
| 19 | ¿Qué métrica evalúa resúmenes generados?                            | A F1 B ROUGE-N C Accuracy D MAPE                   |
| 20 | ¿Qué servicio documenta modelo con métricas y riesgos?              | A Model Cards B Clarify C A2I D Artifact           |

### ✅ Respuestas

1-A 2-B 3-B 4-B 5-B 6-A 7-B 8-B 9-C 10-A 11-A 12-A 13-C 14-B 15-B 16-A 17-A 18-A 19-B 20-A

---

## 📚 9. Glosario AWS AI Practitioner (EN/ES)

| Término                  | Definición                                       |
|--------------------------|--------------------------------------------------|
| AI – Artificial Intelligence | Simulación de inteligencia humana.            |
| ML – Machine Learning    | Aprendizaje automático desde datos.              |
| DL – Deep Learning       | Red neuronal profunda.                           |
| LLM – Large Language Model | Modelo fundacional de lenguaje.                |
| Token                    | Unidad mínima de texto.                          |
| Embedding                | Representación vectorial del significado.        |
| RAG                      | Retrieval-Augmented Generation – agrega contexto externo. |
| Fine-Tuning              | Reentrenar modelo con datos específicos.         |
| RLHF                     | Reinforcement Learning from Human Feedback.      |
| Prompt Engineering       | Diseño de instrucciones efectivas.               |
| Temperature / Top-K / Top-P | Parámetros de inferencia.                     |
| PII / PHI                | Información personal / médica.                   |
| SageMaker Clarify        | Detecta sesgos y explica resultados.             |
| Model Monitor            | Vigila rendimiento de modelos.                   |
| Model Cards              | Documenta entrenamiento.                         |
| Bedrock                  | Plataforma de IA generativa administrada.        |
| Lex                      | Chatbot conversacional.                          |
| Kendra                   | Búsqueda semántica.                              |
| Comprehend               | NLP – análisis de texto.                         |
| Textract                 | Extracción de texto de PDFs/imágenes.            |
| Rekognition              | Análisis y moderación de imágenes.               |
| Personalize              | Recomendaciones personalizadas.                  |
| Polly / Transcribe / Translate | Texto-voz / voz-texto / traducción.        |
| Macie / IAM / KMS / CloudTrail / Artifact | Seguridad, cifrado y auditoría. |

---

## 🧭 10. Estrategia de Examen Final

### Palabras clave rápidas

| Pista en la pregunta          | Servicio correcto                       |
|-------------------------------|-----------------------------------------|
| “Sin pasar por Internet”      | Gateway Endpoint                        |
| “Cumplimiento / auditoría”    | Artifact / Clarify / Model Cards        |
| “Recomendaciones personalizadas” | Personalize                           |
| “Resumen de texto”            | Bedrock / Comprehend                    |
| “Análisis de sentimiento”     | Comprehend                              |
| “Moderación de imagen / animación”| Rekognition                         |
| “Asistente con datos internos”| Q Business                              |
| “Chatbot conversacional”      | Lex                                     |
| “Parámetro de creatividad”    | Temperatura                             |
| “Reducir alucinaciones”       | RAG + contexto confiable                |

### Consejos

- Lee primero el verbo de acción: “crear”, “analizar”, “detectar”… indica tipo de servicio.
- Descarta opciones con palabras irrelevantes.
- Piensa en sobrecarga operativa: si menciona “mínima configuración”, elige servicios administrados.
- Si menciona cumplimiento o ética, busca Clarify, Model Cards o Artifact.

---

## 🏁 Conclusión

Has completado la Guía Intensiva AWS Certified AI Practitioner (AIF-C01).  
Si repasas cada dominio, practicas con el simulacro y reconoces las palabras clave, estarás preparado para aprobar en tu primer intento.
