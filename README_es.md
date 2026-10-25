# Detector de Emociones – Aplicación web basada en IA

🇬🇧 [Read in English](README.md)

Proyecto final del curso de IBM **Developing AI Applications with Python and Flask** (IBM Skills Network / Coursera).

## Qué hace

La aplicación analiza un texto en inglés y detecta las emociones que expresa. Envía el texto al servicio **Watson NLP Emotion Predict** y devuelve una puntuación para cada una de estas cinco emociones:

- ira (anger)
- asco (disgust)
- miedo (fear)
- alegría (joy)
- tristeza (sadness)

También indica la **emoción dominante**, que es la de mayor puntuación.

Ejemplo de salida para *"I am glad this happened"*:

> For the given statement, the system response is 'anger': 0.006, 'disgust': 0.002, 'fear': 0.009, 'joy': 0.968 and 'sadness': 0.049. The dominant emotion is joy.

Si el texto está vacío o no es válido, la aplicación responde `Invalid text! Please try again!`.

## Estructura del proyecto

```
├── EmotionDetection/
│   ├── __init__.py              # Expone emotion_detector
│   └── emotion_detection.py     # Llama a la API de Watson NLP y formatea el resultado
├── static/mywebscript.js        # Envía el texto al servidor y muestra la respuesta
├── templates/index.html         # Interfaz web
├── server.py                    # Servidor Flask
└── test_emotion_detection.py    # Tests unitarios
```

## Cómo ejecutarlo

1. Instala las dependencias:
   ```bash
   pip install flask requests
   ```
2. Arranca el servidor:
   ```bash
   python server.py
   ```
3. Abre `http://localhost:5000` en el navegador, escribe una frase y pulsa el botón.

También puedes llamar directamente al endpoint:

```
GET /emotionDetector?textToAnalyze=I%20love%20this
```

## Tests

```bash
python -m unittest test_emotion_detection.py
```

> **Nota:** el endpoint de Watson NLP (`sn-watson-emotion.labs.skills.network`) lo proporciona el entorno de laboratorio de IBM Skills Network. Es posible que la aplicación y los tests no funcionen fuera de ese entorno.

## Competencias trabajadas en el curso

- Uso de una librería de Watson NLP a través de su API REST
- Formateo de la salida de la API
- Empaquetado de la aplicación como paquete de Python
- Tests unitarios
- Despliegue con Flask
- Gestión de errores
- Análisis estático de código con pylint

## Licencia

Este proyecto está bajo la [Licencia Apache 2.0](LICENSE).
