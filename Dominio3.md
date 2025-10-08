# Guía de Estudio: AWS Certified AI Practitioner - Dominio 3

Este documento detalla la aplicación práctica de los modelos fundacionales (FM), incluyendo consideraciones de diseño, ingeniería de peticiones (prompt engineering), refinamiento y evaluación.

---

## 3.1 Consideraciones de Diseño de Aplicaciones con FM (Modelos Fundacionales) ⚙️

Esta sección cubre los criterios para seleccionar un modelo, el impacto de los parámetros de inferencia y arquitecturas de diseño como RAG.

### Criterios para seleccionar un modelo previamente entrenado

Al elegir un FM, es crucial balancear varios factores para que se ajuste a los requisitos del proyecto:

- Coste vs. rendimiento  
  - Debes encontrar un equilibrio entre el coste de entrenamiento/despliegue y la precisión/ calidad. A veces un modelo menos preciso pero mucho más barato y rápido es la opción correcta.

- Latencia y velocidad de inferencia  
  - Para aplicaciones en tiempo real (ej. vehículos autónomos o chat en vivo) la velocidad es crítica. Modelos grandes pueden ofrecer mejor calidad pero con mayor latencia.

- Modalidades  
  - Considera si la aplicación necesita una sola modalidad (texto) o varias (multimodal: texto, imagen, audio). También valora capacidades multilingües.

- Arquitectura y complejidad  
  - Diferentes arquitecturas se adaptan mejor a distintas tareas (ej. CNN para imágenes, transformadores para lenguaje). Modelos con más parámetros suelen requerir más recursos.

- Disponibilidad y compatibilidad  
  - Verifica la licencia, documentación, soporte y compatibilidad con tu infraestructura (frameworks, hardware).

- Interpretabilidad vs. explicabilidad  
  - Los FM suelen ser cajas negras; si necesitas interpretabilidad matemática o explicaciones detalladas, evalúa técnicas complementarias (explainers, LIME/SHAP, etc.).

### Parámetros de inferencia

Son valores ajustables que controlan cómo el modelo genera respuestas:

- Para aleatoriedad y diversidad:
  - Temperatura: controla creatividad (valores más altos → más aleatorio).
  - Top-k / Top-p (nucleus sampling): limitan la selección de tokens a los más probables o al conjunto acumulado de probabilidad.
  - Amazon Bedrock y otros servicios soportan estos parámetros para controlar la generación.

- Para limitar la longitud:
  - Máximo de tokens / longitud de respuesta.
  - Penalizaciones por repetición y por longitud.
  - Secuencias de parada (stop sequences) para cortar la salida en puntos concretos.

### Generación Aumentada por Recuperación (RAG)

RAG mejora la fidelidad del FM conectándolo a fuentes externas de conocimiento.

- ¿Qué es?  
  - Técnica que recupera información relevante (por ejemplo, desde una base de conocimiento vectorial) y la concatena a la petición antes de enviarla al LLM.

- ¿Por qué usar RAG?
  - Mitiga alucinaciones al proporcionar evidencia factual.
  - Permite acceso a conocimiento actualizado sin reentrenar el modelo completo.

- Bases de datos vectoriales  
  - Almacenan incrustaciones (embeddings) que representan semánticamente texto o contenido multimedia para búsquedas rápidas por similitud.

- Servicios de AWS que pueden usarse como parte de una solución RAG:
  - Amazon OpenSearch Service (con plugins/vector search)
  - Amazon Aurora con extensión pgvector
  - Amazon Neptune
  - Amazon RDS para PostgreSQL (con pgvector u otras extensiones)
  - (Complementos: pipelines ETL y servicios de embeddings)

### Agentes para tareas con varios pasos

- ¿Qué son?  
  - Programas que organizan flujos de trabajo, usan FM para razonar y llaman a APIs o servicios para ejecutar acciones (reservar un vuelo, procesar órdenes).

- ¿Cómo funcionan?  
  - Dividen tareas complejas en pasos, consultan fuentes externas, llaman a sistemas externos y gestionan estado y errores.

- Servicio de AWS relacionado:  
  - Agents para Amazon Bedrock — capacidad administrada para crear y orquestar agentes que interactúan con modelos y APIs externas.

---

## 3.2 Técnicas de Ingeniería de Peticiones (Prompt Engineering) ✍️

Esta sección se enfoca en cómo comunicarse eficazmente con un LLM.

### Conceptos fundamentales

- Petición (prompt): conjunto de entradas que guían la respuesta del LLM (instrucciones, contexto, ejemplos).
- Espacio latente: conocimiento y patrones estadísticos codificados en el modelo. La petición explora ese espacio para generar la salida.

### Técnicas comunes de petición

- Zero-shot: pedir al modelo realizar una tarea sin ejemplos.
- Few-shot: incluir algunos ejemplos en la petición para guiar el formato y estilo de salida.
- Chain-of-Thought (Cadena de pensamiento): pedir al modelo que describa pasos intermedios para mejorar razonamiento en tareas complejas.

### Prácticas recomendadas

- Sé específico: define formato, estilo, longitud y restricciones.
- Usa ejemplos: los ejemplos concretos suelen mejorar el resultado.
- Experimenta: la ingeniería de prompts es iterativa; prueba y mide.
- Conoce las limitaciones del modelo: evita pedir tareas para las cuales el modelo no está bien entrenado.

### Riesgos y mitigación

- Inyección de peticiones: un usuario malicioso inserta instrucciones en el contexto.
- Jailbreaking: intentos de eludir restricciones del modelo.
- Secuestro (hijacking): manipular la petición original con nuevas instrucciones.

Mitigaciones:
- Implementar guardrails, filtros de contenido y saneamiento de inputs.
- Restringir y sanear datos que se incluyen en prompts.
- Validar y aplicar políticas de seguridad y privacidad antes de ejecutar acciones críticas.

---

## 3.3 Entrenamiento y Refinamiento de Modelos 🛠️

Describe cómo se crean y adaptan los modelos fundacionales.

### Procesos clave

- Pre-training (Entrenamiento previo): fase masiva y no supervisada donde el modelo aprende de grandes volúmenes de datos; es costosa en recursos.
- Fine-tuning (Refinamiento): adaptar el FM a tareas específicas con datasets etiquetados más pequeños.

### Técnicas de refinamiento

- Olvido catastrófico: riesgo de que al afinar para una tarea se degrade rendimiento en otras tareas.
- PEFT (Parameter-Efficient Fine-Tuning): técnicas que congelan la mayoría de parámetros y entrenan solo un conjunto pequeño (p. ej. adapters, LoRA), reduciendo costes y preservando conocimiento general.
- Adaptación de dominio: refinar con datos específicos del sector para que el modelo aprenda jerga y términos técnicos.
- RLHF (Reinforcement Learning from Human Feedback): usar calificaciones humanas para alinear salidas del modelo con preferencias y valores humanos.

### Preparación de datos para el refinamiento

- Recolección y preprocesamiento: limpieza, normalización y anonimización si aplica.
- Divisiones: entrenamiento, validación y prueba.
- Servicios de AWS para preparación y etiquetado:
  - Amazon SageMaker Clarify: detección de sesgos y explicabilidad.
  - Amazon SageMaker Ground Truth: flujos de trabajo de etiquetado de datos.
  - Amazon SageMaker Canvas: herramientas low-code/no-code para flujos de datos.

---

## 3.4 Evaluación del Rendimiento del Modelo 📊

Cómo medir si un modelo fundacional cumple los objetivos.

### Desafíos de la evaluación

- Modelos generativos son no deterministas: evaluación automática puede ser insuficiente.
- Necesidad de métricas cualitativas y evaluación humana para tareas abiertas.

### Métricas y benchmarks

- Métricas específicas de tareas:
  - ROUGE: evaluación de resúmenes.
  - BLEU: evaluación de traducciones.
- Benchmarks generales:
  - GLUE y SuperGLUE: comprensión del lenguaje.
  - MMLU: conocimientos y resolución multidominio.
  - BIG-bench: tareas avanzadas que prueban límites de los modelos.

### Métodos y herramientas de evaluación

- Evaluación humana: revisores que juzgan fidelidad, utilidad y seguridad.
- Herramientas de AWS:
  - Amazon Bedrock Model Evaluation: comparar respuestas de modelos con referencias humanas y calcular métricas (ej. BERTScore).
  - Amazon SageMaker Clarify: soporte para evaluar aspectos relacionados con sesgos y calidad de datos/modelos.

### Alineación con objetivos empresariales

- Define objetivos y métricas de éxito antes del despliegue.
- Considera toda la arquitectura: infraestructuras, almacenamiento, latencia, UX.
- Mide y supervisa continuamente: telemetría, alertas, pruebas A/B y revisiones periódicas.

---

Notas finales
- Antes de producción, realiza pruebas de seguridad, privacidad y cumplimiento.
- Implementa observabilidad y pipelines de retraining o actualización de conocimiento (por ejemplo, actualizar índices RAG).
- Mantén un proceso iterativo de mejora: pruebas, métricas, feedback humano y refinamiento continuo.
