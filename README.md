![Python](https://img.shields.io/badge/Python-3.7%2B-blue?logo=python)
![Flask](https://img.shields.io/badge/Framework-Flask-lightgrey?logo=flask)
![Scikit-learn](https://img.shields.io/badge/ML-Scikit--learn-orange?logo=scikit-learn)
![License](https://img.shields.io/badge/License-MIT-green)

# Iris Flower ML — Flask

A beginner-friendly machine learning web application that predicts the species of an Iris flower based on four morphological measurements. The trained scikit-learn model is served via a lightweight Flask API with an HTML form frontend.

## Features

- Predicts one of three Iris species: **Setosa**, **Versicolor**, or **Virginica**
- Four numerical inputs: sepal length, sepal width, petal length, petal width
- Trained model serialized as `iri.pkl` (scikit-learn classifier)
- Clean two-page Flask app: input form (`home.html`) and results page (`after.html`)
- Debug mode enabled for local development

## Tech Stack

| Component | Technology |
|-----------|-----------|
| Language | Python 3.7+ |
| Web Framework | Flask |
| ML Model | Scikit-learn (serialized with Pickle) |
| Data Processing | NumPy |
| Frontend | HTML (Jinja2 templates) |
| Dataset | UCI Iris (`iris.data`) |

## Model Architecture

- **Dataset:** UCI Iris Dataset (150 samples, 4 features, 3 classes)
- **Model type:** Scikit-learn classifier (serialized in `iri.pkl`)
- **Training script:** `iris.py` / `basics.py`
- **Features:** Sepal Length, Sepal Width, Petal Length, Petal Width (all in cm)

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | Render the input form (`home.html`) |
| POST | `/predict` | Accept form data and return predicted species |

### POST `/predict` — Form Fields

| Field | Type | Description |
|-------|------|-------------|
| `a` | float | Sepal length (cm) |
| `b` | float | Sepal width (cm) |
| `c` | float | Petal length (cm) |
| `d` | float | Petal width (cm) |

**Response:** Renders `after.html` with the predicted class name.

## Getting Started

### Prerequisites

```bash
pip install flask scikit-learn numpy
```

### Run the App

```bash
python app.py
```

Open your browser at [http://localhost:5000](http://localhost:5000).

### Retrain the Model

```bash
python iris.py
# or
python basics.py
```

This will regenerate `iri.pkl`.

## File / Folder Structure

```
Iris-Flower-ML-Flask/
├── app.py              # Flask application
├── iris.py             # Model training script
├── basics.py           # Exploratory / alternative training
├── iri.pkl             # Serialized trained model
├── iris.data           # UCI Iris dataset
├── templates/
│   ├── home.html       # Input form
│   └── after.html      # Prediction result page
└── static/             # CSS / JS assets
```

## License

MIT License — see [LICENSE](LICENSE) for details.
