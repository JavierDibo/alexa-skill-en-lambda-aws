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