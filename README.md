# Emotion Detector – AI-based Web Application

🇪🇸 [Leer en español](README_es.md)

Final project for the IBM course **Developing AI Applications with Python and Flask** (IBM Skills Network / Coursera).

## What it does

This application analyzes a piece of English text and detects the emotions it expresses. It sends the text to the **Watson NLP Emotion Predict** service and returns a score for each of five emotions:

- anger
- disgust
- fear
- joy
- sadness

It also reports the **dominant emotion**, which is the one with the highest score.

Example output for *"I am glad this happened"*:

> For the given statement, the system response is 'anger': 0.006, 'disgust': 0.002, 'fear': 0.009, 'joy': 0.968 and 'sadness': 0.049. The dominant emotion is joy.

If the text is empty or invalid, the app replies with `Invalid text! Please try again!`.

## Project structure

```
├── EmotionDetection/
│   ├── __init__.py              # Exposes emotion_detector
│   └── emotion_detection.py     # Calls the Watson NLP API and formats the result
├── static/mywebscript.js        # Sends the text to the server and shows the response
├── templates/index.html         # Web interface
├── server.py                    # Flask server
└── test_emotion_detection.py    # Unit tests
```

## How to run it

1. Install the dependencies:
   ```bash
   pip install flask requests
   ```
2. Start the server:
   ```bash
   python server.py
   ```
3. Open `http://localhost:5000` in your browser, type a sentence and click the button.

You can also call the endpoint directly:

```
GET /emotionDetector?textToAnalyze=I%20love%20this
```

## Tests

```bash
python -m unittest test_emotion_detection.py
```

> **Note:** the Watson NLP endpoint (`sn-watson-emotion.labs.skills.network`) is provided by the IBM Skills Network lab environment. The app and the tests may not work outside of that environment.

## Course skills covered

- Using a Watson NLP library through its REST API
- Formatting the API output
- Packaging the application as a Python package
- Writing unit tests
- Deploying the app with Flask
- Error handling
- Static code analysis with pylint

## License

This project is licensed under the [Apache License 2.0](LICENSE).
