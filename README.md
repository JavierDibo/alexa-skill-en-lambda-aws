# Alexa Skill - Interfaces de Usuario Multimodales

Skill de Alexa desarrollada con AWS Lambda que proporciona información sobre la asignatura, grupo, práctica y universidad.

## Código (`hello_world.py`)

El archivo implementa handlers para cada intent usando el patrón `AbstractRequestHandler` del SDK de Alexa. Cada handler procesa una petición específica y genera una respuesta de voz. El `SkillBuilder` registra todos los handlers y exporta `lambda_handler` como punto de entrada para AWS Lambda.

## Instalación

```bash
cd skill
python -m venv skill_env
skill_env\Scripts\activate
pip install ask-sdk
```

## Despliegue

1. Copia `hello_world.py` a `skill_env\Lib\site-packages\`.
2. Comprimido el contenido en `full-lambda.zip`.
3. Subir el zip como `code` en el lambda de AWS.
4. Configura el handler como `hello_world.lambda_handler`.
5. Conecta la skill en Alexa Developer Console con el ARN de Lambda.

## Intents

- Información de asignatura, grupo, práctica y universidad
- Definición de interfaces multimodales
- Intents del sistema: Help, Cancel, Stop

## Invocación

"Alexa, abre hola mundo cero cero dos"

# Memoria de práctica
## Puesta en marcha de una skill de Alexa sobre AWS Lambda
### *Interfaces de usuario multimodales*

---

### **Autores**
*   **Juan Antonio Rodríguez Fernández**
*   **Javier Francisco Dibo Gómez**

---

## **Índice**
- [1. Introducción](#1-introducción)
- [2. Arquitectura](#2-arquitectura)
    - [2.1. Visión general](#21-visión-general)
    - [2.2. Flujo](#22-flujo)
- [3. Alexa en Funcionamiento](#3-alexa-en-funcionamiento)
    - [3.1. Información Asignatura](#31-información-asignatura)
    - [3.2. Información Grupo](#32-información-grupo)
    - [3.3. Información Prácticas](#33-información-prácticas)
    - [3.4. Información Universidad](#34-información-universidad)
    - [3.5. Definición Multimodal](#35-definición-multimodal)
- [4. Notas](#4-notas)
- [5. Anexo](#5-anexo)
- [6. Conclusión](#6-conclusión)

---

## **1. Introducción**
El objetivo de esta práctica es desarrollar y poner en marcha una skill básica para **Alexa**, utilizando **AWS Lambda** como backend. Para ello, se debe comprender y aplicar todo el flujo completo de creación de una skill: 

*   **Configuración** de las cuentas necesarias.  
*   **Definición** del modelo de interacción en Amazon Developer Console.  
*   **Implementación** del código en Python utilizando el SDK de Alexa.  
*   **Despliegue** del servicio en AWS y su posterior vinculación con la skill creada.

Al finalizar, se debe ser capaz de crear un asistente de diálogo sencillo, manejar los componentes fundamentales del ecosistema Alexa y desplegar soluciones en la infraestructura de Amazon Web Services.

Esta práctica se enmarca dentro de la asignatura **Interfaces de Usuario Multimodales** del Máster en Ingeniería Informática, y está orientada a introducir al estudiante en el desarrollo de interfaces conversacionales mediante asistentes virtuales.

---

## **2. Arquitectura**
En esta sección se resume el funcionamiento técnico de la solución implementada.

### **2.1. Visión general**
El archivo `hello_world.py` organiza el código siguiendo las mejores prácticas del SDK:
1.  **Logging:** Configuración para depuración.
2.  **Handlers:** Definición de clases que heredan de `AbstractRequestHandler`.
3.  **SkillBuilder:** Registro de los handlers para procesar las peticiones.
4.  **Lambda Handler:** Exportación de la función principal para AWS Lambda.

### **2.2. Flujo de ejecución**
El proceso de atención de una solicitud sigue estos pasos:

1.  **Petición:** AWS Lambda recibe el JSON desde *Alexa Skills Kit*.
2.  **Invocación:** Se ejecuta el `lambda_handler`.
3.  **Enrutamiento:** El `SkillBuilder` evalúa los handlers en orden de registro.
4.  **Procesamiento:** El handler seleccionado genera la respuesta usando `response_builder`.
5.  **Excepciones:** Si algo falla, el `CatchAllExceptionHandler` captura el error.
6.  **Serialización:** La respuesta se transforma a JSON y se envía de vuelta.
7.  **Salida:** Alexa reproduce la voz y mantiene la sesión si se requiere un *reprompt*.

---

## **3. Alexa en Funcionamiento**
Tras configurar los *intents* de la skill y la función Lambda, podemos interactuar con el asistente.

### **3.1. Información Asignatura**
> **Intent:** `InformacionAsignaturaIntent`

Proporciona detalles sobre "Interfaces de Usuario Multimodales", destacando su pertenencia al Máster en Ingeniería Informática de la **Universidad de Jaén**.
*   *Ejemplo de uso:* "Alexa, cuéntame sobre la asignatura"

### **3.2. Información Grupo**
> **Intent:** `InformacionGrupoIntent`

Informa sobre los integrantes del equipo de desarrollo.
*   *Ejemplo de uso:* "Alexa, quiénes forman el grupo"

### **3.3. Información Prácticas**
> **Intent:** `InformacionPracticaIntent`

Detalle técnico sobre la **Práctica 2**, explicando la integración entre Alexa Skills Kit y AWS Lambda.
*   *Ejemplo de uso:* "Alexa, cuéntame sobre la práctica"

### **3.4. Información Universidad**
> **Intent:** `InformacionUniversidadIntent`

Datos sobre la Universidad de Jaén (UJA) y el contexto académico del máster.
*   *Ejemplo de uso:* "Alexa, cuéntame sobre la universidad"

### **3.5. Definición Multimodal**
> **Intent:** `DefinicionMultimodalIntent`

Explica el concepto de interfaces multimodales (voz, gestos, texto, táctil) y sitúa a Alexa como un ejemplo clave.
*   *Ejemplo de uso:* "Alexa, qué son las interfaces multimodales"


---


## **4. Notas de Implementación**

### **4.1. Versión de Python en AWS Lambda**
Durante la creación de la función Lambda, se observó que la versión **Python 3.7** (mencionada en el guion) ya no está disponible en AWS. En su lugar, se ha utilizado **Python 3.9** para garantizar compatibilidad y soporte.


---


## **5. Anexo**

### **Código fuente**
El desarrollo completo, incluyendo el modelo de interacción y el código de la Lambda, está disponible en:
[**Repositorio de GitHub**](https://github.com/JavierDibo/alexa-skill-en-lambda-aws)

## **6. Conclusión**
La realización de esta práctica ha permitido consolidar los conocimientos sobre el ecosistema de Amazon Alexa y la arquitectura serverless de AWS Lambda. Se ha logrado integrar con éxito un modelo de interacción basado en lenguaje natural con un backend funcional en Python, comprendiendo la importancia de los *handlers* para la gestión de peticiones y respuestas.

El desarrollo de esta skill demuestra la eficiencia de separar la capa de interacción (Alexa Skills Kit) de la lógica de negocio (AWS Lambda), lo que facilita el escalado y mantenimiento de aplicaciones de voz. Finalmente, la adaptación a las versiones actuales de Python en AWS subraya la necesidad de mantener una mentalidad flexible y actualizada en el desarrollo de soluciones basadas en la nube.****
