# Guía de Estudio: Seguridad, Conformidad y Gobernanza en IA con AWS - Dominio 5

Este documento resume los conceptos esenciales sobre cómo proteger los sistemas de inteligencia artificial (IA), y las normativas de gobernanza y conformidad aplicables, basándose en la información de la transcripción.

---

## 5.1 Métodos para Proteger los Sistemas de IA 🛡️

Esta sección cubre los principios de seguridad, las herramientas de AWS y las estrategias para mitigar las vulnerabilidades específicas de los sistemas de IA.

### El Modelo de Responsabilidad Compartida de AWS
La seguridad y la conformidad en AWS son una responsabilidad compartida entre AWS y el cliente.

- **Responsabilidad de AWS (Seguridad de la nube):**  
  AWS es responsable de proteger la infraestructura global que ejecuta todos los servicios de AWS. Esto incluye el hardware, el software, las redes y las instalaciones físicas que ejecutan los servicios en la nube.

- **Responsabilidad del Cliente (Seguridad en la nube):**  
  El cliente es responsable de la seguridad de todo lo que crea y pone en la nube. Esto incluye la gestión de datos, la configuración de los servicios de AWS, la gestión de acceso de los usuarios y el cifrado de datos. El nivel de responsabilidad del cliente varía según el servicio utilizado; por ejemplo, usar Amazon EC2 implica más responsabilidad (gestión del SO, parches) que un servicio totalmente administrado como la inferencia sin servidor de SageMaker.

### Gestión de Identidades y Accesos (IAM)
AWS Identity and Access Management (IAM) es el servicio fundamental para administrar de forma segura el acceso a los recursos de AWS.

- **Usuario Raíz (Root User):**  
  Identidad creada al abrir una cuenta de AWS, con acceso completo a todos los servicios. No usar para tareas diarias; crear usuarios de IAM con permisos mínimos. Para el usuario raíz, usar una contraseña segura y activar autenticación multifactor (MFA).

- **Usuarios de IAM:**  
  Identidades que representan a personas o aplicaciones. Por defecto, un nuevo usuario no tiene permisos. Crear usuarios individuales y no compartir credenciales.

- **Grupos de IAM:**  
  Conjuntos de usuarios que permiten asignar permisos a múltiples usuarios a la vez. Es recomendable adjuntar políticas a grupos en lugar de a usuarios individuales.

- **Políticas de IAM:**  
  Documentos (generalmente JSON) que definen permisos. Seguir el principio de mínimo privilegio.

- **Roles de IAM:**  
  Identidades con permisos específicos que pueden ser asumidas temporalmente por usuarios o servicios. Usan credenciales temporales que caducan.

### Seguridad de Cuentas y Datos

- **Autenticación Multifactor (MFA):**  
  Añade una capa de protección adicional al inicio de sesión. Activar MFA inmediatamente después de crear la cuenta.

- **Cifrado de Datos:**
  - *En Reposo:* Proteger datos almacenados. AWS KMS permite crear y controlar claves de cifrado. Servicios como Amazon S3 y SageMaker cifran en reposo por defecto.
  - *En Tránsito:* Proteger datos en movimiento. Todos los puntos de enlace de AWS admiten TLS para conexiones HTTPS seguras.

### Seguridad de Red con VPC
Amazon Virtual Private Cloud (VPC) permite configurar redes privadas y aisladas.

- Ejecutar recursos de SageMaker (Studio, instancias de cuaderno) dentro de una VPC para controlar tráfico y restringir acceso a Internet.
- El modo "Solo para VPC" impide que SageMaker acceda a Internet; el tráfico a otros servicios de AWS se enruta mediante puntos de enlace de interfaz de VPC (AWS PrivateLink).

### Vulnerabilidades y Mitigación en Sistemas de IA
Los sistemas de IA son susceptibles a ataques específicos que deben ser mitigados.

#### Vulnerabilidades Comunes
- **Envenenamiento de Datos (Data Poisoning):**  
  Introducción de datos corruptos o mal etiquetados en el conjunto de entrenamiento para manipular predicciones.
- **Entradas Adversarias (Adversarial Inputs):**  
  Modificaciones sutiles en datos de entrada para engañar al modelo.
- **Inversión de Modelos y Robo:**  
  Uso de salidas de un modelo para inferir información sobre datos de entrenamiento o replicar el modelo.
- **Inyección de Peticiones (Prompt Injection):**  
  Específico para LLMs; instrucciones maliciosas en el prompt para manipular resultados y eludir restricciones.

#### Estrategias de Mitigación
- **Control de Acceso:** Aplicar mínimo privilegio para proteger datos y modelos.
- **Validación de Entradas:** Inspeccionar y validar datos de usuarios para detectar patrones maliciosos.
- **Entrenamiento Robusto:** Incluir datos diversos y contradictorios para aumentar resistencia.
- **Supervisión Continua:** Usar Amazon SageMaker Model Monitor para vigilar calidad de datos y rendimiento en producción, detectando desviaciones y anomalías.

### Trazabilidad y Reproducibilidad
Hacer seguimiento de artefactos de ML es esencial para gobernanza y reproducibilidad.

- **Amazon SageMaker Model Registry:** Catalogar, versionar y administrar modelos en un repositorio centralizado con metadatos y estado de aprobación (pendiente, aprobado, rechazado).
- **Fichas del Modelo de SageMaker:** Documentan información esencial (uso previsto, riesgos, resultados de evaluación) en un registro inmutable.
- **Seguimiento de Trazabilidad de ML de SageMaker:** Crea representaciones gráficas del flujo de trabajo ML para auditar y reproducir el historial completo del modelo.

---

## 5.2 Gobernanza y Conformidad de los Sistemas de IA ⚖️

Esta sección describe cómo cumplir con estándares normativos y aplicar una gobernanza de datos eficaz utilizando servicios de AWS.

### Conformidad en AWS
- **Modelo de Responsabilidad Compartida para la Conformidad:**  
  AWS es responsable de la conformidad de la nube (cumplimiento de estándares globales) y proporciona informes de auditoría a los clientes a través de AWS Artifact. El cliente es responsable de la conformidad en la nube, configurando correctamente sus cargas de trabajo.

### Servicios de AWS para la Conformidad
- **AWS Audit Manager:** Automatiza la recopilación de evidencias para auditorías y asigna requisitos de conformidad (por ejemplo, SOC 2) a datos de uso de AWS.
- **AWS Config:** Evalúa, audita y supervisa configuraciones de recursos continuamente; puede corregir automáticamente configuraciones no conformes.
- **Amazon Inspector:** Analiza aplicaciones y contenedores en busca de vulnerabilidades y exposiciones de red.
- **Barreras de protección para Amazon Bedrock:** Implementa políticas de seguridad para IA responsable: filtrar contenido dañino, bloquear temas no deseados y detectar PII en interacciones con LLMs.

### Gobernanza de Datos
La gobernanza de datos combina personas, procesos y tecnología para administrar disponibilidad, usabilidad, integridad y seguridad de los datos.

- **Roles Clave:**
  - *Propietario de Datos (Data Owner):* Ejecutivo que decide políticas de datos y accesos.
  - *Administrador de Datos (Data Steward):* Responsable diario del conocimiento y calidad de los datos.

- **Herramientas para la Gobernanza de Datos:**
  - *AWS Glue DataBrew:* Herramienta visual de preparación de datos para perfilar y rastrear linaje.
  - *Catálogo de datos de AWS Glue:* Repositorio centralizado de metadatos para descubrimiento y gestión.
  - *AWS Lake Formation:* Crea un lago de datos seguro en S3 y administra control de acceso a nivel columna, fila y celda.

### Administración del Ciclo de Vida de los Datos
- **Clases de Almacenamiento de Amazon S3:** Diferentes clases optimizadas por costo según frecuencia de acceso (S3 Standard, S3 Glacier, etc.).
- **Reglas de Ciclo de Vida de S3:** Automatizan la transición de datos entre clases o su eliminación (ej.: mover conjuntos de entrenamiento a archivo después de 120 días y eliminar tras 5 años).

### Implementación de una Estrategia de Gobernanza de IA
- **Identificar el Ámbito de Responsabilidad:** Determinar el nivel de responsabilidad según cómo se consume la IA. Usar servicios completamente administrados (ej., Amazon Comprehend) reduce el ámbito de responsabilidad frente a crear un modelo propio.
- **Documentar Políticas y Formar a los Empleados:** Crear políticas claras sobre gobernanza de datos, acceso y transparencia del modelo; capacitar a empleados sobre responsabilidades.
- **Definir Mecanismos de Supervisión:** Establecer cómo se monitorizará rendimiento, conformidad y sesgo, con umbrales y acciones predefinidas.
- **Revisar y Adaptar:** Revisar resultados con frecuencia y actualizar políticas para alinearlas con objetivos empresariales y nuevos desafíos de seguridad.

---
Fin de la Guía — Dominio 5
