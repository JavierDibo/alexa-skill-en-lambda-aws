# Alexa Skill - Interfaces de Usuario Multimodales

Skill de Alexa desarrollada con AWS Lambda que proporciona información sobre la asignatura, grupo, práctica y universidad.

## Requisitos

- Python 3.9+
- Cuenta de Amazon Developer
- Cuenta de AWS

## Instalación

```bash
cd skill
python -m venv skill_env
skill_env\Scripts\activate
pip install ask-sdk
```

## Despliegue

1. Copia `hello_world.py` a `skill_env\Lib\site-packages\`
2. Comprime el contenido de `site-packages` en un ZIP
3. Sube el ZIP a AWS Lambda
4. Configura el handler como `hello_world.lambda_handler`
5. Conecta la skill en Alexa Developer Console con el ARN de Lambda

## Intents

- Información de asignatura, grupo, práctica y universidad
- Definición de interfaces multimodales
- Intents del sistema: Help, Cancel, Stop

## Invocación

"Alexa, abre hola mundo cero cero dos"

