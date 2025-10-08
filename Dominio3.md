Guía de Estudio: AWS Certified AI Practitioner - Dominio 3
Este documento detalla la aplicación práctica de los modelos fundacionales (FM), incluyendo consideraciones de diseño, ingeniería de peticiones, refinamiento y evaluación.

3.1 Consideraciones de Diseño de Aplicaciones con FM  (Modelos Fundacionales) ⚙️
Esta sección cubre los criterios para seleccionar un modelo, el impacto de los parámetros de inferencia y las arquitecturas de diseño como RAG.

Criterios para Seleccionar un Modelo Previamente Entrenado
Al elegir un FM, es crucial balancear varios factores para que se ajuste a los requisitos del proyecto.


Coste vs. Rendimiento: Debes encontrar un equilibrio entre el coste de entrenamiento/mantenimiento y el rendimiento del modelo. Un modelo ligeramente menos preciso puede ser significativamente más barato.



Latencia y Velocidad de Inferencia: Para aplicaciones en tiempo real (ej. vehículos autónomos), la velocidad a la que un modelo genera predicciones es crítica. Modelos complejos pueden tener tiempos de inferencia mayores, lo que podría no cumplir los requisitos de latencia.




Modalidades: Considera si tu aplicación necesita procesar un solo tipo de datos (texto) o múltiples (multimodal). También, si requieres capacidades multilingües, debes elegir modelos entrenados en los idiomas pertinentes.



Arquitectura y Complejidad: Diferentes arquitecturas son mejores para distintas tareas (ej. CNN para imágenes, RNN para NLP). Modelos más complejos (más parámetros, más capas) pueden ser más precisos pero requieren más recursos computacionales.




Disponibilidad y Compatibilidad: Verifica que el modelo sea compatible con tu entorno y que tenga la licencia y documentación adecuadas. Revisa si el modelo se mantiene y actualiza regularmente.



Interpretabilidad vs. Explicabilidad: Los FM son "cajas negras" extremadamente complejas, lo que los hace no interpretables. Si la capacidad de interpretar matemáticamente las decisiones del modelo es un requisito, los FM podrían no ser la mejor opción.


Parámetros de Inferencia
Son valores ajustables que controlan cómo el modelo genera una respuesta.

Para Aleatoriedad y Diversidad:

Temperatura: Controla la creatividad.

Top K / Top P: Limitan la selección de tokens a los más probables.

Amazon Bedrock soporta estos parámetros para controlar la respuesta del modelo.

Para Limitar la Longitud:


Longitud de la respuesta, penalizaciones y secuencias de parada son parámetros que se pueden usar para controlar el tamaño del resultado generado.

Generación Aumentada por Recuperación (RAG)
RAG es una técnica clave para mejorar los FM conectándolos a bases de conocimiento externas.



¿Qué es? Es una técnica que aumenta la petición del usuario con información relevante recuperada de una fuente de datos externa (como una base de datos vectorial) antes de enviarla al LLM.

¿Por qué usar RAG?


Mitiga Alucinaciones: Proporciona al modelo datos fácticos y contextuales para basar sus respuestas, reduciendo la generación de información incorrecta.



Combate el Conocimiento Desactualizado: Permite al modelo acceder a información actualizada sin necesidad de un costoso reentrenamiento.


Bases de Datos Vectoriales: Son un componente central de RAG. Almacenan datos (texto, imágenes) como representaciones numéricas llamadas incrustaciones (embeddings). Esto permite una búsqueda rápida y eficiente de información semánticamente similar a la consulta del usuario.




Servicios de AWS para Bases de Datos Vectoriales: Incluyen Amazon OpenSearch Service, Amazon Aurora (con la extensión pgvector), Amazon Neptune y Amazon RDS para PostgreSQL.


Agentes para Tareas con Varios Pasos

¿Qué son? Son programas que organizan flujos de trabajo y permiten a los FM ejecutar tareas reales que requieren interactuar con sistemas externos, como reservar un vuelo o procesar una orden de compra.



¿Cómo funcionan? Desglosan tareas complejas, llaman a APIs para efectuar acciones y consultan bases de conocimiento para obtener información adicional.



Servicio de AWS: Agents para Amazon Bedrock es una capacidad administrada que facilita la creación de estos agentes.

3.2 Técnicas de Ingeniería de Peticiones (Prompt Engineering) ✍️
Esta sección se enfoca en cómo comunicarse eficazmente con un LLM.

Conceptos Fundamentales

Petición (Prompt): Es el conjunto de entradas que un usuario proporciona para guiar al LLM a generar una respuesta adecuada. Puede contener una instrucción, un contexto y un texto de entrada.



Espacio Latente: Es el conocimiento estadístico y los patrones de lenguaje codificados dentro del modelo. Una petición consulta este espacio latente. Si el espacio latente del modelo carece de información sobre un tema, es más probable que alucine.



Técnicas Comunes de Peticiones

Peticiones con Cero Muestras (Zero-shot): Se pide al modelo que realice una tarea sin darle ningún ejemplo previo.


Peticiones con Pocas Muestras (Few-shot): Se proporcionan algunos ejemplos en la petición para ayudar al modelo a entender mejor la tarea y el formato de salida esperado.


Cadena de Pensamiento (Chain-of-Thought): Para tareas complejas, se le pide al modelo que divida el proceso de razonamiento en pasos intermedios, mejorando la calidad del resultado final.

Prácticas Recomendadas

Sé Específico: Proporciona instrucciones claras, incluyendo formato, estilo, tono y longitud deseada.


Usa Ejemplos: Incluye ejemplos del resultado que esperas.


Experimenta: La ingeniería de peticiones es un proceso iterativo; prueba diferentes enfoques.


Conoce las Limitaciones del Modelo: Evalúa qué tan bien conoce el modelo un tema antes de crear peticiones complejas sobre él.

Riesgos y Mitigación

Inyección de Peticiones: Un ataque donde un usuario malicioso inserta instrucciones en una petición para generar una respuesta no deseada.


Jailbreaking: Intentar eludir las medidas de seguridad o barreras de protección del modelo.


Secuestro (Hijacking): Manipular la petición original con nuevas instrucciones.


Mitigación: Usar barreras de protección (guardrails) para definir temas no deseados, bloquear palabras clave y filtrar contenido dañino o confidencial.

3.3 Entrenamiento y Refinamiento de Modelos 🛠️
Esta sección describe cómo se crean y adaptan los modelos fundacionales.

Procesos Clave

Entrenamiento Previo (Pre-training): Es el proceso inicial y masivo donde el modelo aprende de terabytes de datos no estructurados mediante aprendizaje autosupervisado. Es extremadamente costoso y requiere una enorme capacidad de cómputo (millones de horas de GPU).




Refinamiento (Fine-tuning): Es un proceso de aprendizaje supervisado que adapta un modelo pre-entrenado a una tarea específica usando un conjunto de datos etiquetados más pequeño y específico. Ayuda a que el modelo se especialice en un dominio o caso de uso particular.


Técnicas de Refinamiento

Olvido Catastrófico: Ocurre cuando refinar un modelo para una sola tarea hace que pierda rendimiento en otras tareas.


Refinamiento con Eficiencia de Parámetros (PEFT): Un conjunto de técnicas que congelan los parámetros del LLM original y solo entrenan un pequeño número de capas o parámetros nuevos. Esto reduce significativamente los costes de computación y memoria. LoRA (Low-Rank Adaptation) es una técnica popular de PEFT.




Adaptación de Dominio: Refinar el modelo con datos específicos para que aprenda la jerga de un sector o términos técnicos.


Aprendizaje por Refuerzo a partir de Comentarios Humanos (RLHF): Utiliza la retroalimentación humana para alinear mejor el modelo con las preferencias y valores humanos, mejorando la calidad de las respuestas.


Preparación de Datos para el Refinamiento
La preparación de datos consiste en recopilar, preprocesar y organizar los datos para el modelo.

El conjunto de datos se divide en divisiones de entrenamiento, validación y prueba.

Servicios de AWS para Preparación de Datos:


Amazon SageMaker Clarify: Para detectar sesgos en los datos.


Amazon SageMaker Ground Truth: Para administrar flujos de trabajo de etiquetado de datos.


Amazon SageMaker Canvas: Para flujos de datos con poco código.

3.4 Evaluación del Rendimiento del Modelo 📊
Esta sección cubre cómo medir si un modelo fundacional es eficaz y cumple los objetivos.

Desafíos de la Evaluación
El resultado de los modelos generativos no es determinista, lo que hace que su evaluación sea más compleja que la de los modelos de ML tradicionales.

Métricas y Puntos de Referencia (Benchmarks)
Métricas Específicas de Tareas:


ROUGE: Se usa para evaluar la calidad de resúmenes de texto.


BLEU: Se usa para evaluar la calidad de traducciones automáticas.

Benchmarks Generales:

Se utilizan para comparar el rendimiento de diferentes LLMs en una amplia gama de tareas.

Ejemplos incluyen: GLUE y SuperGLUE (comprensión general del lenguaje) , MMLU (conocimiento y resolución de problemas en múltiples dominios) , BIG-bench (tareas que superan las capacidades actuales) y HELM (para mejorar la transparencia de los modelos).





Métodos y Herramientas de Evaluación

Evaluación Humana: Utilizar personas para evaluar y comparar manualmente las respuestas de los modelos.

Herramientas de AWS:


Amazon Bedrock Model Evaluation: Permite comparar automáticamente las respuestas de los modelos con una referencia humana y calcular puntuaciones (ej. BERTscore) para evaluar la fidelidad y las alucinaciones.


Amazon SageMaker Clarify: Se puede utilizar para crear trabajos de evaluación de modelos para LLMs.

Alineación con Objetivos Empresariales
Antes de implementar, define claramente los objetivos empresariales y las métricas de éxito.

Considera la arquitectura completa de la aplicación, desde la infraestructura y el almacenamiento hasta la interfaz de usuario.


Es fundamental medir, supervisar y revisar continuamente las métricas para evaluar si el modelo está cumpliendo sus objetivos y proporcionando valor.








