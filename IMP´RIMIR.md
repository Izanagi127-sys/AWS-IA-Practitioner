# AWS Certified AI Practitioner  
**Material de Estudio – Dominio 1: Fundamentos de IA y Machine Learning**

---

## Índice

1. [Introducción](#introducción)
2. [Enunciados de Tarea](#enunciados-de-tarea)
    - [1.1 Conceptos y Terminología Básica de IA](#11-conceptos-y-terminología-básica-de-ia)
    - [1.2 Casos Prácticos de Uso de IA](#12-casos-prácticos-de-uso-de-ia)
    - [1.3 Ciclo de Vida del Desarrollo de ML](#13-ciclo-de-vida-del-desarrollo-de-ml)
3. [Glosario Explicativo](#glosario-explicativo)

---

## Introducción

Este material de estudio explica todo el **Dominio 1** de la certificación AWS Certified AI Practitioner. Aquí aprenderás desde los conceptos básicos hasta el ciclo completo de desarrollo y gestión de proyectos de Inteligencia Artificial (IA) y Machine Learning (ML), con ejemplos claros y explicaciones profundas, para que puedas dominar los fundamentos y aprobar tu examen.

---

## Enunciados de Tarea

### 1.1 Conceptos y Terminología Básica de IA

**Inteligencia Artificial (IA):**  
La IA es el área de la informática que busca crear sistemas capaces de realizar tareas que normalmente requieren inteligencia humana, como aprender, razonar, resolver problemas, comprender el lenguaje y reconocer objetos o patrones. El objetivo principal de la IA es desarrollar sistemas que puedan interpretar información, adaptarse a situaciones nuevas y tomar decisiones basadas en datos.

**Machine Learning (ML):**  
El ML es una subdisciplina de la IA que se enfoca en el desarrollo de algoritmos y modelos matemáticos para que las máquinas puedan aprender de los datos, identificar patrones y realizar predicciones sin necesidad de ser programadas explícitamente para cada tarea. Por ejemplo, un modelo de ML puede recomendar productos en una tienda online basándose en el historial de compras de los usuarios.

**Aprendizaje Profundo (Deep Learning):**  
Es un tipo avanzado de ML que utiliza redes neuronales artificiales con muchas capas. Estas redes están inspiradas en el funcionamiento del cerebro humano y son capaces de procesar grandes volúmenes de datos complejos, como imágenes, audio y texto. El aprendizaje profundo es la base tecnológica detrás de aplicaciones como el reconocimiento facial, el procesamiento de lenguaje natural y la traducción automática.

#### Ejemplos de Aplicaciones de IA

- **Chatbots:** Sistemas como Alexa o ChatGPT pueden responder preguntas, mantener conversaciones y realizar tareas por voz o texto.
- **Detección de fraudes:** Modelos que analizan transacciones en tiempo real para identificar patrones sospechosos y prevenir fraudes financieros.
- **Mantenimiento predictivo:** En manufactura, los sensores y ML pueden anticipar cuándo una máquina necesita mantenimiento antes de que falle.
- **Recomendaciones de productos:** Plataformas como Netflix o Amazon sugieren películas o productos basándose en tus gustos y comportamientos anteriores.
- **Diagnóstico médico asistido:** Algoritmos que ayudan a identificar enfermedades a partir de imágenes médicas o datos clínicos.
- **Traducción automática y procesamiento de lenguaje natural:** Herramientas capaces de traducir texto o voz entre diferentes idiomas y entender el significado de frases complejas.

#### Tipos de Datos en ML

- **Datos estructurados:** Organizados en filas y columnas, como hojas de cálculo o bases de datos relacionales. Son fáciles de procesar y analizar.
- **Datos semiestructurados:** Tienen cierta organización, como los archivos JSON o XML, pero no siguen una estructura tabular estricta.
- **Datos no estructurados:** No tienen formato fijo, por ejemplo imágenes, videos, texto libre o publicaciones en redes sociales.
- **Series temporales:** Datos con marcas de tiempo, como registros de sensores, métricas de rendimiento de sistemas, o historiales de ventas.

#### Tipos de Aprendizaje en ML

- **Aprendizaje supervisado:** El modelo se entrena con datos que ya tienen una etiqueta o resultado conocido. Ejemplo: clasificar correos como spam o no spam.
- **Aprendizaje no supervisado:** El modelo recibe datos sin etiquetas y debe identificar patrones, agrupaciones o estructuras ocultas. Ejemplo: segmentar clientes por comportamiento de compra.
- **Aprendizaje por refuerzo:** Un agente toma decisiones en un entorno y recibe recompensas o penalizaciones, aprendiendo a maximizar su desempeño mediante la experiencia. Ejemplo: un coche autónomo que aprende a conducir en una pista de carreras.

#### Problemas Comunes en ML

- **Sobreajuste:** El modelo aprende demasiado de los datos de entrenamiento, incluyendo detalles irrelevantes, y pierde capacidad de generalizar a datos nuevos.
- **Subajuste:** El modelo es incapaz de aprender patrones relevantes y tiene bajo desempeño tanto en entrenamiento como en prueba.
- **Sesgo:** El modelo favorece o discrimina a ciertos grupos debido a desequilibrios en los datos de entrenamiento, lo que puede llevar a decisiones injustas.

---

### 1.2 Casos Prácticos de Uso de IA

La IA y el ML se utilizan en una gran variedad de sectores y aplicaciones:

- **Automatización de tareas repetitivas:** Robots y sistemas automáticos que realizan tareas monótonas, liberando a los humanos para trabajos creativos.
- **Detección de fraudes y anomalías:** Identificación de transacciones sospechosas, errores médicos o fallos en sensores.
- **Recomendaciones personalizadas:** Plataformas que sugieren productos, contenidos o servicios adaptados a las preferencias de cada usuario.
- **Chatbots y asistentes virtuales:** Sistemas que atienden consultas de clientes, resuelven dudas y pueden interactuar en lenguaje natural.
- **Reconocimiento facial y procesamiento de imágenes:** Identificación de personas, objetos, defectos en productos o señales en imágenes.
- **Extracción de texto y análisis de sentimientos:** Herramientas que leen documentos, extraen información clave y analizan el tono emocional de opiniones o comentarios.
- **Traducción automática:** Sistemas que traducen texto o voz entre idiomas en tiempo real.
- **IA generativa:** Creación de contenidos originales (texto, imágenes, música, etc.) a partir de instrucciones dadas por el usuario.

**Cuándo NO usar IA:**

- Cuando el coste de desarrollo y mantenimiento es mayor que los beneficios esperados.
- Cuando se necesita transparencia total en las decisiones (IA compleja puede ser difícil de explicar).
- Cuando un sistema basado en reglas simples puede resolver el problema de manera más eficiente y económica.

---

### 1.3 Ciclo de Vida del Desarrollo de ML

El desarrollo de soluciones de ML sigue un ciclo que incluye varias etapas clave:

1. **Definición del problema y de los objetivos empresariales:**  
   Identifica claramente el problema que se quiere resolver y cómo se medirá el éxito (por ejemplo, reducir el fraude en un 20% o aumentar ventas en un 10%).

2. **Recopilación y preparación de datos:**  
   Reúne los datos necesarios y realiza tareas de limpieza, transformación y etiquetado para asegurar calidad y relevancia.

3. **Entrenamiento y ajuste de modelos:**  
   Utiliza los datos preparados para entrenar el modelo, ajustando hiperparámetros y probando diferentes algoritmos para encontrar la mejor solución.

4. **Evaluación de modelos:**  
   Mide el rendimiento del modelo usando métricas como exactitud, precisión, exhaustividad, puntuación F1, AUC, MSE y RMSE.

5. **Despliegue de modelos:**  
   Implementa el modelo en producción, ya sea para inferencias en tiempo real, por lotes o asincrónicas.

6. **Supervisión y mantenimiento:**  
   Monitorea el desempeño del modelo, detecta desviaciones y realiza reentrenamiento cuando sea necesario para mantener la calidad.

7. **Métricas empresariales y retorno de inversión:**  
   Evalúa el impacto real del modelo en la empresa, calcula beneficios, costes y riesgos para asegurar que el proyecto cumple sus objetivos.

---

## Glosario Explicativo

- **IA (Inteligencia Artificial):**  
  Área de la computación que busca diseñar sistemas capaces de emular funciones cognitivas humanas, como el razonamiento, la percepción y el aprendizaje. Permite automatizar procesos complejos y tomar decisiones inteligentes.

- **ML (Machine Learning):**  
  Rama de la IA que desarrolla métodos para que las máquinas aprendan automáticamente a partir de datos, identificando patrones y haciendo predicciones.

- **Deep Learning (Aprendizaje Profundo):**  
  Tipo de ML basado en redes neuronales artificiales que pueden tener muchas capas. Es especialmente útil para procesar datos complejos como imágenes y lenguaje natural.

- **Inferencia:**  
  Uso de un modelo entrenado para hacer predicciones sobre datos nuevos que no ha visto antes.

- **Características (Features):**  
  Son los atributos o variables de entrada que el modelo utiliza para aprender y generar predicciones. Por ejemplo, la edad y el salario de una persona en un modelo para otorgar préstamos.

- **Hiperparámetros:**  
  Configuraciones externas al modelo que se establecen antes del entrenamiento y afectan cómo aprende, como el número de capas en una red neuronal o la velocidad de aprendizaje.

- **Sobreajuste (Overfitting):**  
  Fenómeno donde el modelo aprende demasiado de los datos de entrenamiento, incluyendo detalles irrelevantes, y falla al generalizar a datos no vistos.

- **Subajuste (Underfitting):**  
  Situación donde el modelo es demasiado simple y no logra aprender los patrones importantes de los datos.

- **Sesgo (Bias):**  
  Tendencia del modelo a favorecer o perjudicar a ciertos grupos por desequilibrios en los datos de entrenamiento. Es un problema ético y técnico que debe vigilarse.

- **MLOps:**  
  Conjunto de prácticas que aplican la automatización, control de versiones y monitoreo al ciclo de vida del ML, asegurando que los modelos sean reproducibles, escalables y fáciles de mantener.

- **Clustering (Agrupamiento):**  
  Técnica de aprendizaje no supervisado que agrupa datos en conjuntos de elementos similares. Se usa para segmentar clientes, descubrir patrones ocultos y organizar información.

- **Regresión:**  
  Problema de ML que busca predecir valores numéricos continuos (como precios o temperaturas) a partir de una o varias variables.

- **Clasificación:**  
  Problema de ML que asigna cada entrada a una categoría o clase. Puede ser binaria (dos clases) o multiclase.

- **AUC (Área bajo la curva ROC):**  
  Métrica que mide la capacidad de un modelo de clasificación para distinguir entre clases. Un valor alto indica buen desempeño en discriminar entre diferentes resultados.

- **MSE (Error cuadrático medio):**  
  Métrica en regresión que calcula el promedio de los errores al cuadrado entre las predicciones y los valores reales. Penaliza más los errores grandes.

- **RMSE (Raíz del error cuadrático medio):**  
  Es la raíz cuadrada del MSE. Permite interpretar el error en las mismas unidades que la variable objetivo, facilitando la comparación.

- **Puntuación F1 (F1 Score):**  
  Métrica que combina precisión y exhaustividad en un solo valor. Es especialmente útil cuando es importante equilibrar ambos aspectos, como en la detección de enfermedades raras o correos spam.

---
