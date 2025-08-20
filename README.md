
# 📝 End to end Text-Summarizer

An end-to-end Natural Language Processing (NLP) pipeline built to summarize long text documents. This project includes modular stages for data processing, model training, and deployment via a FastAPI interface.

---

## 📚 Table of Contents

- [Features](#-features)
- [Project Structure](#-project-structure)
- [Installation](#-installation)
- [Usage](#-usage)
- [API Endpoints](#-api-endpoints)
- [Configuration](#-configuration)
- [Dependencies](#-dependencies)
- [Examples](#-examples)
- [Troubleshooting](#-troubleshooting)
- [Contributors](#-contributors)
- [License](#-license)

---

## 🚀 Features

- Modularized training pipeline for ingestion, validation, transformation, training, and evaluation
- FastAPI server with endpoints to train or predict
- Custom YAML-based configuration system
- Docker support for containerized deployment
- Clean code structure for production-grade use

---

## 🏗 Project Structure

```
├── app.py                  # FastAPI app
├── main.py                 # Training pipeline orchestrator
├── Dockerfile              # For containerization
├── params.yaml             # Model parameters
├── config/config.yaml      # Path and data configurations
├── src/textSummarizer/
│   ├── config/             # Configuration management
│   ├── conponents/         # Pipeline components (data ingestion, transformation, etc.)
│   ├── constants/          # Constants
│   ├── entity/             # Data schema/entities
│   ├── logging/            # Logging module
│   ├── pipeline/           # Stage-wise training and prediction scripts
│   └── utils/              # Utility functions
└── research/               # Jupyter notebooks for experimentation
```

---

## 🛠 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/AryanGupta5084/Text-Summarizer-Project.git
cd Text-Summarizer-Project
```

### 2. Create and Activate Environment

```bash
conda create -n summary python=3.9 -y
conda activate summary
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Usage

### Run FastAPI Server

```bash
python app.py
```

Open your browser at: [http://localhost:8000/docs](http://localhost:8000/docs) to access the Swagger UI.

---

## 📡 API Endpoints

| Method | Endpoint     | Description                        |
|--------|--------------|------------------------------------|
| GET    | `/train`     | Triggers the full training pipeline |
| POST   | `/predict`   | Returns summary for given text     |
| GET    | `/`          | Redirects to docs                  |

---

## ⚙ Configuration

- `config/config.yaml`: Paths to data directories
- `params.yaml`: Hyperparameters for model training

---

## 📦 Dependencies

- `FastAPI`
- `uvicorn`
- `pydantic`
- `PyYAML`
- `transformers` or any summarization-compatible NLP library
- `scikit-learn`, `pandas`, `numpy`

> Install using:  
```bash
pip install -r requirements.txt
```

---

## 🧪 Examples

Example `POST` request to `/predict`:

```json
{
  "text": "Text summarization is a Natural Language Processing (NLP) task..."
}
```

Response:
```json
{
  "summary": "Text summarization is an NLP task..."
}
```

---

## 🛠 Troubleshooting

- ⚠ **No response from `/predict`**: Ensure the model is trained (`/train`) before predicting.
- ⚠ **Module errors**: Double-check environment paths and virtual environment activation.
- ⚠ **Docker issues**: Ensure Docker is installed and build the container with `docker build -t summarizer .`

---

## 👨‍💻 Contributors

- **Aryan Gupta**  
  📧 ag5787842@gmail.com

---

## 📄 License

This project is licensed under the terms of the [LICENSE](./LICENSE) file in this repository.

> © 2025 Aryan Gupta. All rights reserved.
