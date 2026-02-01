# Churn Prediction - Model Deployment

> Wdrożenie modelu predykcji odejść klientów do produkcji

## 📋 Opis Projektu

Czwarty krok serii Churn Prediction. Skupia się na deployment modelu: serializacja, API, monitoring i serving.

## 🎯 Cel

- Deployment modelu do produkcji
- REST API dla predykcji
- Batch predictions dla całej bazy klientów
- Monitoring modelu w realnym świecie

## � Jupyter Notebooks

<div class="grid cards" markdown>
-   [:octicons-book-16: Train Notebook](../notebooks/train.html){ .md-button .md-button--primary target="_blank" }
    
    Training pipeline: preprocessing, model training i serializacja.

-   [:octicons-book-16: Predict Notebook](../notebooks/predict.html){ .md-button .md-button--primary target="_blank" }
    
    Prediction pipeline: loading model i batch predictions.
</div>

<div class="grid cards" markdown>
-   [:octicons-mark-github-16: GitHub Repository](https://github.com/Lukasz6855/ML-portfolio/tree/main/07_churn_model_deployment){ .md-button .md-button--primary target="_blank" }
</div>

## �🛠️ Technologie

- **Flask/FastAPI** - REST API
- **Docker** - konteneryzacja
- **Pickle/Joblib** - serializacja modelu
- **MLflow** - tracking i registry

## 📊 Architecture

```
User Request → API Endpoint → Load Model → Preprocess → Predict → Return JSON
```

## 🚀 Features

1. **REST API** z endpointem `/predict`
2. **Batch predictions** dla CSV
3. **Model versioning**
4. **Health checks**
5. **Logging i monitoring**

## 📈 Deployment Process

1. Serializacja modelu (pickle)
2. Utworzenie API (FastAPI)
3. Dockerization
4. CI/CD pipeline
5. Cloud deployment (AWS/Azure/GCP)

---

**Status:** ✅ Ukończony  
**Część serii:** 4/5 Churn Prediction  
**Tech Stack:** FastAPI + Docker
