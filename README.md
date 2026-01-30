# Portfolio Projektów AI & Data Science

> Strona portfolio prezentująca moje projekty z zakresu Data Science, Machine Learning i Aplikacji AI

## 📖 O Projekcie

To moje **portfolio online** stworzone przy użyciu **MkDocs Material** - statycznego generatora dokumentacji. Strona powstała w celu prezentacji moich projektów, umiejętności oraz doświadczenia w dziedzinie analizy danych, uczenia maszynowego i sztucznej inteligencji.

### 🎯 Cel

Głównym celem tej strony jest:
- **Prezentacja projektów** - uporządkowana kolekcja moich najlepszych prac
- **Dokumentacja techniczna** - szczegółowe opisy implementacji i rozwiązań
- **Portfolio zawodowe** - wizytówka dla potencjalnych pracodawców i klientów
- **Dzielenie się wiedzą** - inspirowanie innych poprzez prezentację realnych case studies

## 📊 Zawartość Portfolio

### 🤖 Aplikacje AI
Zaawansowane aplikacje wykorzystujące sztuczną inteligencję:
- **Podsumowanie Audio/Video** - automatyczne generowanie podsumowań z treści multimedialnych (Whisper API, GPT-4)
- **Pomocnik Prezentowy AI** - inteligentny asystent w wyborze prezentów (Next.js, OpenAI, Ceneo API)
- **Znajdywacz Zdjęć** - semantyczne wyszukiwanie obrazów w naturalnym języku (Vision API, Qdrant)

### 🧠 Machine Learning
Projekty predykcyjne i analityczne:
- **Titanic Classification** - przewidywanie przeżycia pasażerów (AutoML, PyCaret)
- **House Price Regression** - predykcja cen nieruchomości (Gradient Boosting)
- **Customer Segmentation** - clustering klientów (K-Means, DBSCAN)
- **Churn Prediction** - seria projektów o predykcji odejścia klientów (overfitting, tuning, deployment)
- **Half Marathon Prediction** - prognozowanie czasów biegowych (aplikacja Streamlit)
- **Prognoza Ubezpieczeń** - przewidywanie kosztów ubezpieczenia zdrowotnego

### 📈 Data Science
Eksploracyjna analiza danych i wizualizacje:
- **Irisy EDA** - klasyczna analiza zbioru Iris (Seaborn, Matplotlib)
- **Titanic EDA** - dogłębna analiza danych Titanica

## 📁 Struktura Projektu

```
Portfolio projektów/
├── docs/                          # Dokumentacja Markdown
│   ├── index.md                   # Strona główna
│   ├── o-mnie.md                  # Informacje o mnie
│   ├── kontakt.md                 # Dane kontaktowe
│   │
│   ├── aplikacje-ai/              # 🤖 Aplikacje AI
│   │   ├── index.md               # Przegląd aplikacji
│   │   ├── podsumowanie-audio-video.md
│   │   ├── pomocnik-prezentowy.md
│   │   └── znajdywacz-zdjec.md
│   │
│   ├── machine-learning/          # 🧠 Machine Learning
│   │   ├── index.md               # Przegląd projektów ML
│   │   ├── titanic-classification.md
│   │   ├── house-price-regression.md
│   │   ├── customer-segmentation.md
│   │   ├── churn-overfitting.md
│   │   ├── churn-model-tuning.md
│   │   ├── churn-recall-threshold.md
│   │   ├── churn-model-deployment.md
│   │   ├── churn-explainability.md
│   │   ├── halfmarathon-prediction.md
│   │   └── prognoza-ubezpieczen.md
│   │
│   ├── data-science/              # 📈 Data Science
│   │   ├── index.md               # Przegląd analiz
│   │   ├── irisy-eda.md
│   │   └── titanic-eda.md
│   │
│   ├── notebooks/                 # 📓 Jupyter Notebooks (HTML)
│   │   ├── Zad.1_Iris_EDA_raport_presentation.html
│   │   ├── titanic_classification.html
│   │   └── ... (16 notebooków)
│   │
│   ├── img/                       # 🖼️ Obrazy i screenshoty
│   ├── stylesheets/              # 🎨 Custom CSS
│   └── javascripts/              # ⚙️ Custom JavaScript
│
├── projekty/                      # 📦 Źródłowe projekty (gitignore)
├── mkdocs.yml                     # ⚙️ Konfiguracja MkDocs
├── requirements.txt               # 📋 Zależności Python
├── .gitignore                     # 🚫 Ignorowane pliki
└── README.md                      # 📖 Ten plik
```

## 🎨 Stack Technologiczny

### Frontend & Design
- **MkDocs** - generator statycznych stron
- **Material for MkDocs** - nowoczesny, responsywny theme
- **Python Markdown Extensions** - zaawansowane formatowanie
- **Custom CSS/JS** - personalizacja wyglądu

### Funkcjonalności
- **Nawigacja z kartami** - przejrzysta struktura sekcji
- **Tryb ciemny/jasny** - automatyczne przełączanie motywów
- **Wyszukiwarka** - szybkie znajdowanie treści
- **Jupyter Notebooks** - osadzone notebooki jako HTML
- **Responsive Design** - optymalizacja mobilna
- **SEO** - optymalizacja dla wyszukiwarek

### Pluginy MkDocs
- `mkdocs-material` - theme
- `mkdocs-git-revision-date-localized-plugin` - daty aktualizacji
- `mkdocs-minify-plugin` - minifikacja HTML/CSS/JS
- `mkdocs-awesome-pages-plugin` - zarządzanie stronami

## 🌐 Strona Live

Portfolio dostępne pod adresem: **[https://Lukasz6855.github.io/portfolio/](https://Lukasz6855.github.io/portfolio/)**

## 📄 Licencja

MIT

---

**Autor:** Łukasz Sachmerda
**Rok:** 2026  
**Technologia:** MkDocs Material

