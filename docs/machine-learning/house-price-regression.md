# House Price Regression

> Przewidywanie cen domów przy użyciu zaawansowanych technik regresji

## 📋 Opis Projektu

Projekt predykcji cen nieruchomości na podstawie ich cech fizycznych i lokalizacyjnych. Wykorzystuje AutoML (PyCaret) do automatycznego porównania algorytmów regresji i wyboru najlepszego modelu.

## 🎯 Cel

Zbudowanie modelu ML, który przewiduje cenę domu na podstawie jego charakterystyk: liczba pokoi, powierzchnia, lokalizacja, rok budowy, itd.

## � Jupyter Notebook

<div class="grid cards" markdown>
-   [:octicons-book-16: Zobacz Notebook](../notebooks/house_price_regression.html){ .md-button .md-button--primary target="_blank" }
    
    Kompleksowa analiza predykcji cen nieruchomości z PyCaret.
</div>

<div class="grid cards" markdown>
-   [:octicons-mark-github-16: GitHub Repository](https://github.com/Lukasz6855/ML-portfolio/tree/main/02_house_price_regression)
</div>

## �📊 Dataset

**House Prices Dataset** (Kaggle):
- **1460 obserwacji** treningowych
- **79 zmiennych** wyjaśniających
- **Target:** SalePrice (cena sprzedaży)
- Zróżnicowane cechy: numeryczne i kategoryczne

## 🛠️ Technologie

- Python, PyCaret, Scikit-learn
- Pandas, NumPy
- Matplotlib, Seaborn
- Feature Engineering

## 📈 Wyniki

**Najlepszy Model:** Gradient Boosting Regressor

| Metryka | Wartość |
|---------|---------|
| **MAE** | **17,276.35** |
| **RMSE** | **28,313.92** |
| R² | 0.89 |

Model pozwala oszacować cenę domu z rozsądnym błędem predykcji.

## 💡 Kluczowe Cechy

Top features wpływające na cenę:
1. Overall Quality
2. Total Square Footage
3. Year Built / Remodeled
4. Garage Area
5. Full Bathrooms

## 🎓 Czego się Nauczyłem

- Regresja z PyCaret AutoML
- Feature Engineering dla danych nieruchomości
- Handling outliers i missing values
- Log transformation dla skewed target

---

**Status:** ✅ Ukończony  
**Data:** 02.01.2026  
**Model:** Gradient Boosting Regressor
