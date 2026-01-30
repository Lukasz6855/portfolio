# Titanic Classification

> Przewidywanie przeżycia pasażerów Titanica przy użyciu AutoML (PyCaret)

## 📋 Opis Projektu

Klasyczny problem klasyfikacji binarnej: przewidywanie, czy pasażer Titanica przeżył katastrofę, na podstawie danych demograficznych i informacji o podróży. Projekt wykorzystuje AutoML (PyCaret) do automatycznego porównania i optymalizacji wielu algorytmów ML.

## 🎯 Cel

Zbudowanie modelu ML, który na podstawie danych pasażera (wiek, płeć, klasa, cena biletu) przewidzi, czy przeżył katastrofę Titanica.

**Business Value:**
- Analiza czynników wpływających na przeżycie
- Identyfikacja grup ryzyka
- Zrozumienie znaczenia cech w podejmowaniu decyzji życiowych

## � Jupyter Notebook

<div class="grid cards" markdown>
-   [:octicons-book-16: Zobacz Notebook](../notebooks/titanic_classification.html){ .md-button .md-button--primary target="_blank" }
    
    Pełny pipeline: EDA, preprocessing, AutoML z PyCaret, tuning i ewaluacja.
</div>

## �📊 Dataset

**Titanic Dataset** (Kaggle):
- **891 obserwacji** w zbiorze treningowym
- **418 obserwacji** w zbiorze testowym
- **Target:** Survived (0/1)
- **Features:** Pclass, Sex, Age, SibSp, Parch, Fare, Embarked, Cabin

## 🛠️ Technologie

- **Python** - język programowania
- **PyCaret** - AutoML framework dla klasyfikacji
- **Scikit-learn** - algorytmy ML
- **Pandas** - przetwarzanie danych
- **NumPy** - operacje numeryczne
- **Matplotlib/Seaborn** - wizualizacje

## 🔄 Pipeline ML

### 1. Eksploracyjna Analiza Danych (EDA)
- Analiza rozkładów zmiennych
- Identyfikacja braków danych
- Analiza korelacji
- Wykrywanie outliers

### 2. Preprocessing
```python
# Braki danych
Age: mediana według Pclass i Sex
Embarked: najczęstsza wartość
Cabin: usunięto (>77% braków)

# Feature Engineering
FamilySize = SibSp + Parch + 1
IsAlone = (FamilySize == 1)
Title = ekstrakcja z Name (Mr, Mrs, Miss, Master, etc.)

# Encoding
Sex: Label Encoding (male=1, female=0)
Embarked: One-Hot Encoding
Pclass: pozostawiono numeryczne
```

### 3. AutoML z PyCaret

```python
from pycaret.classification import *

# Setup środowiska
clf = setup(data=train, 
            target='Survived',
            session_id=123,
            normalize=True,
            transformation=True,
            remove_outliers=True)

# Porównanie modeli
best_models = compare_models(n_select=5)

# Najlepszy model
best = compare_models()[0]  # Logistic Regression

# Tuning hiperparametrów
tuned_model = tune_model(best)

# Finalizacja i zapis
final_model = finalize_model(tuned_model)
save_model(final_model, 'titanic_model')
```

## 📈 Wyniki

### Najlepszy Model: **Logistic Regression**

| Metryka | Wartość |
|---------|---------|
| **Accuracy** | **82.09%** |
| Precision | 79.5% |
| Recall | 73.2% |
| F1-Score | 76.2% |
| AUC | 0.871 |

### Top 5 Modeli (PyCaret AutoML)

1. **Logistic Regression** - 82.09% ✅
2. Random Forest - 81.23%
3. Gradient Boosting - 80.78%
4. Extra Trees - 80.11%
5. LightGBM - 79.89%

### Feature Importance

```
1. Sex (female)          ████████████████████ 54.2%
2. Pclass (1st)          ████████████ 34.1%
3. Age                   ███████ 23.5%
4. Fare                  ██████ 19.8%
5. FamilySize            ████ 12.3%
6. Title (Mrs/Miss)      ███ 9.7%
7. Embarked (C)          ██ 6.4%
```

## 💡 Kluczowe Insights

!!! success "Co działało dobrze"
    - **Logistic Regression** okazała się najlepsza (prostota > complexity)
    - **Feature Engineering** (FamilySize, Title) poprawiło accuracy o ~3%
    - **PyCaret AutoML** szybko porównało 15+ modeli
    - **Cross-validation** zapewniła stabilne wyniki

!!! warning "Wyzwania"
    - **Imbalanced dataset** (61.6% nie przeżyło)
    - **Missing values** w Age i Cabin
    - **Small dataset** (tylko 891 obserwacji)
    - **Overfitting risk** przy complex models

!!! info "Wnioski Biznesowe"
    - Płeć to zdecydowanie najsilniejszy predyktor (kobiety >4x więcej przeżyło)
    - Klasa podróży znacząco wpływała (status społeczny)
    - Małe rodziny (2-4 osoby) lepiej przeżyły niż samotni/duże rodziny
    - Model potwierdza historyczną regułę "kobiety i dzieci pierwsze"

## 📁 Struktura Projektu

```
01_titanic_classification/
├── data/
│   ├── train.csv           # Dane treningowe
│   └── test.csv            # Dane testowe
├── models/
│   └── titanic_model.pkl   # Zapisany model
├── titanic_classification.ipynb  # Główny notebook
├── titanic_classification.py     # Skrypt Python
├── logs.log                # Logi PyCaret
└── README.MD
```

## 🎓 Czego się Nauczyłem

- **AutoML z PyCaret** - szybkie porównanie wielu modeli
- **Feature Engineering** - tworzenie nowych cech poprawia performance
- **Cross-validation** - ważna dla oceny stabilności modelu
- **Interpretability** - prosty model (Logistic Regression) często wygrywa
- **Domain Knowledge** - znajomość kontekstu historycznego pomogła w FE
- **Pipeline ML** - od EDA przez preprocessing do deployment

## 📝 Wnioski

**Techniczne:**
- Logistic Regression to świetny baseline i często końcowy model
- Feature Engineering > Complex Models
- PyCaret znacznie przyspiesza eksperymentowanie
- 82% accuracy to solidny wynik na tym datasecie

**Biznesowe:**
- Model potwierdza historyczne fakty o priorytecie kobiet i dzieci
- Status społeczny (Pclass) miał ogromny wpływ na przeżycie
- Można wykorzystać do analizy zachowania w sytuacjach kryzysowych

## 🔗 Powiązane Projekty

- [Titanic EDA](../data-science/titanic-eda.md) - eksploracyjna analiza danych
- [House Price Regression](house-price-regression.md) - regresja z PyCaret
- [Customer Segmentation](customer-segmentation.md) - clustering z PyCaret

---

**Status projektu:** ✅ Ukończony  
**Data:** 02.01.2026  
**Accuracy:** 82.09%  
**Model:** Logistic Regression (PyCaret)  
**Framework:** PyCaret + Scikit-learn
