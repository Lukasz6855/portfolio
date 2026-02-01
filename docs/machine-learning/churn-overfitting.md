# Churn Prediction - Analiza Overfittingu

> Identyfikacja i zapobieganie overfittingowi w modelach predykcji odejść klientów

## 📋 Opis Projektu

Pierwszy krok w serii projektów Churn Prediction. Koncentruje się na analizie zjawiska overfittingu i technikach jego zapobiegania.

## 🎯 Cel

- Zrozumienie overfittingu w kontekście churn prediction
- Porównanie performance na train vs validation
- Implementacja technik regularyzacji
- Analiza learning curves

## � Jupyter Notebook

<div class="grid cards" markdown>
-   [:octicons-book-16: Zobacz Notebook](../notebooks/churn_prediction.html){ .md-button .md-button--primary target="_blank" }
    
    Analiza overfittingu: learning curves, regularizacja i techniki zapobiegania.
</div>

<div class="grid cards" markdown>
-   [:octicons-mark-github-16: GitHub Repository](https://github.com/Lukasz6855/ML-portfolio/tree/main/04_churn_overfitting){ .md-button .md-button--primary target="_blank" }
</div>

## �📊 Problem Overfitting

**Objawy:**
- Wysoka accuracy na train (>95%)
- Niska accuracy na validation (<75%)
- Model "zapamiętuje" dane treningowe
- Słaba generalizacja

## 🛠️ Techniki Zapobiegania

1. **Regularization** (L1, L2)
2. **Cross-validation**
3. **Feature selection**
4. **Early stopping**
5. **Ensemble methods**

## 📈 Wyniki

- Redukcja overfittingu o 15%
- Lepsza generalizacja modelu
- Stabilniejsze predykcje

---

**Status:** ✅ Ukończony  
**Część serii:** 1/5 Churn Prediction
