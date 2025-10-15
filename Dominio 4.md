Guía de Estudio: AWS Certified AI Practitioner - Dominio 2
Este documento resume los conceptos esenciales sobre los aspectos básicos de la IA generativa, sus aplicaciones empresariales y las herramientas de AWS correspondientes, basándose en la información de la transcripción.

2.1 Conceptos Básicos de la IA Generativa 🧠
Esta sección cubre la definición, los componentes y el funcionamiento de la inteligencia artificial generativa.

Definición y Diferencias Clave
IA Generativa: Es un subconjunto del aprendizaje profundo que se enfoca en generar contenido nuevo y original (texto, imágenes, audio, código), en lugar de solo clasificar o predecir sobre datos existentes.
IA Tradicional: Se centra principalmente en clasificar o hacer predicciones basadas en datos de entrada.
Modelos Fundacionales (FM): Son la base de la IA generativa. Son modelos de redes neuronales muy grandes y complejos, con miles de millones de parámetros, entrenados con enormes cantidades de datos. Cuantos más parámetros, más memoria y capacidad tiene el modelo para realizar tareas avanzadas.
Arquitectura Clave: El Transformador
El elemento principal de la IA generativa moderna es la red de transformadores, introducida en el artículo de 2017 "Attention is All You Need".

LLMs como ChatGPT se basan en esta arquitectura.
Una innovación clave es el mecanismo de autoatención, que permite al modelo ponderar la importancia de diferentes partes de la entrada, capturando así relaciones contextuales y dependencias a largo plazo.
La arquitectura consiste en un codificador (que genera una representación vectorial o embedding para cada token) y un decodificador.
Terminología Esencial
Petición (Prompt): La entrada (instrucciones y contenido) que se envía a un modelo generativo para que genere un resultado.
Inferencia: El proceso de usar un modelo entrenado para generar un resultado o "finalización" a partir de una petición.
Token: Una unidad de información (palabra, carácter, etc.). El modelo usa un tokenizador para convertir texto humano en un vector de IDs de tokens.
Vectores y Embeddings: Un vector es una lista de números que representa características de un concepto. Las incrustaciones (embeddings) son representaciones vectoriales que capturan el significado semántico de los tokens. Cuanto más cerca están dos vectores en el espacio, más similar es su significado.
Aprendizaje en Contexto (In-context learning): Técnica para mejorar la respuesta del modelo incluyendo ejemplos de la tarea deseada directamente en la petición (prompt).
Tipos de Modelos y Casos de Uso
Unimodal vs. Multimodal:

Unimodal: Trabaja con un solo tipo de datos, como los LLM que solo usan texto.
Multimodal: Procesa y genera varios tipos de datos combinados (texto, imagen, video, audio), permitiendo un razonamiento más complejo.
Modelos de Difusión:

Son una clase de modelos generativos que aprenden a revertir un proceso de ruido para crear un resultado de alta calidad, como una imagen.
Tienden a producir resultados de mayor calidad y son más estables de entrenar que otras arquitecturas como las GANs.
Ejemplos incluyen Stable Diffusion, DALL-E y Midjourney.
Casos de Uso Principales:

Generación y resumen de texto.
Generación de código fuente para acelerar el desarrollo de software.
Extracción de información, chatbots, traducción y motores de recomendación.
2.2 Capacidades y Limitaciones para Negocios 📈
Esta sección explora las ventajas, los riesgos y las métricas para evaluar la IA generativa en un contexto empresarial.

Ventajas Empresariales
Simplicidad y Accesibilidad: La IA generativa hace que muchas aplicaciones de IA sean más sencillas y rápidas de crear a un menor coste.
Adaptabilidad: Se puede aplicar a muchas tareas y dominios diferentes sin necesidad de un reentrenamiento completo.
Limitaciones y Riesgos
Alucinaciones: El modelo puede inventar información de forma convincente cuando no conoce la respuesta correcta. Es crucial contrastar las respuestas con fuentes autorizadas.
Contenido Dañino y Sesgos: Los modelos se entrenan con datos masivos de internet, por lo que pueden reproducir lenguaje tóxico, sesgos o información peligrosa.
Falta de Memoria: Un LLM no recuerda conversaciones anteriores por defecto; cada petición es tratada de forma independiente.
Razonamiento y Matemáticas: Tienen una capacidad limitada para el razonamiento complejo y las matemáticas.
Evaluación y Selección de Modelos
Métricas de Evaluación:

Evaluar LLMs es complejo porque su salida no es determinista.
ROUGE (Recall-Oriented Understudy for Gisting Evaluation): Se usa para evaluar la calidad de resúmenes de texto.
BLEU (Bilingual Evaluation Understudy): Se usa para evaluar la calidad de traducciones automáticas.
Técnicas de Mejora:

Refinamiento (Fine-tuning): Entrenar aún más un modelo pre-entrenado con datos específicos para mejorar su rendimiento en una tarea concreta.
Aprendizaje por Refuerzo a partir de Comentarios Humanos (RLHF): Una técnica de refinamiento para alinear mejor el comportamiento del modelo con las preferencias humanas y aumentar la amabilidad, honestidad e inocuidad.
Métricas Empresariales Clave (KPIs):

Para medir el éxito de una aplicación de IA, se deben usar métricas como la calidad de los resultados (relevancia, exactitud), la eficiencia (tasas de finalización de tareas), el retorno de la inversión (ROI) y el valor del ciclo de vida del cliente (CLTV).
2.3 Infraestructura y Tecnologías de AWS ☁️
Esta sección describe los servicios y la infraestructura que AWS ofrece para construir aplicaciones de IA generativa.

La Pila de IA Generativa de AWS
AWS divide su oferta en tres capas clave:

Capa Inferior (Infraestructura):

Proporciona hardware especializado para entrenamiento e inferencia, como los chips AWS Trainium y AWS Inferentia, y seguridad a nivel de hardware con AWS Nitro System.
Capa Intermedia (Herramientas y Modelos):

Permite acceder a modelos y herramientas para construir y escalar aplicaciones. Aquí se encuentra Amazon SageMaker.
Capa Superior (Aplicaciones):

Incluye servicios que usan los FM para tareas específicas, como la generación de código o contenido.
Servicios Clave de AWS para IA Generativa
Amazon Bedrock:

Un servicio totalmente administrado que ofrece acceso a una variedad de modelos fundacionales (de Amazon y terceros como Cohere, Stability AI) a través de una única API.
Permite experimentar con diferentes modelos en sus "zonas de juego" (Playgrounds) para encontrar el más adecuado para un caso de uso.
PartyRock es una zona de juegos de Bedrock que facilita la creación de aplicaciones de IA generativa para aprender sus fundamentos.
Amazon SageMaker JumpStart:

Actúa como un centro de modelos (model hub) que facilita el despliegue y refinamiento de modelos fundacionales de código abierto.
Proporciona recursos como cuadernos de ejemplo y blogs para acelerar el desarrollo.
Amazon Titan:

Es la familia de modelos fundacionales creada por Amazon, disponible a través de Bedrock.
Amazon Q Developer (antes CodeWhisperer):

Un asistente de codificación con IA que genera sugerencias de código en tiempo real, desde fragmentos hasta funciones completas.
Ventajas y Consideraciones de Coste
Beneficios de AWS: Usar AWS para IA generativa ofrece ventajas como accesibilidad, rentabilidad, seguridad de nivel empresarial, conformidad y rapidez en la comercialización.

Modelos de Precios:

Alojar tu propio modelo: Implica pagar por la infraestructura de computación (GPU) y, a veces, una licencia por el modelo. Requiere inversión y mantenimiento.
Pago por Token: Se paga según el número de tokens procesados (tanto en la entrada como en la salida). Es un modelo escalable ofrecido por servicios como Bedrock.
Optimización de Costes: Es fundamental eliminar los puntos de enlace (endpoints) de los modelos de SageMaker cuando no se usan y seguir las prácticas recomendadas de supervisión de costes.

