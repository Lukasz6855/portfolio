# Churn Prediction - Recall & Threshold Optimization

> Optymalizacja threshold klasyfikacji dla maksymalizacji recall

## 📋 Opis Projektu

Trzeci krok serii Churn Prediction. Koncentruje się na optymalizacji decision threshold dla biznesowego celu: catch all churners.

## 🎯 Cel

- Maksymalizacja recall (catch więcej churnerów)
- Analiza trade-off precision vs recall
- Business-oriented threshold selection
- ROC curve i precision-recall curve analysis

## � Jupyter Notebook

<div class="grid cards" markdown>
-   [:octicons-book-16: Zobacz Notebook](../notebooks/churn_recall_threshold.html){ .md-button .md-button--primary target="_blank" }
    
    Optymalizacja threshold: ROC curves, precision-recall analysis i business-driven decisions.
</div>

<div class="grid cards" markdown>
-   [:octicons-mark-github-16: GitHub Repository](https://github.com/Lukasz6855/ML-portfolio/tree/main/06_churn_recall_threshold){ .md-button .md-button--primary target="_blank" }
</div>

## �📊 Business Context

**Cost of False Negatives > False Positives**
- Utrata klienta = $1000+ lifetime value
- Niepotrzebna retention campaign = $50
- Priorytet: złapać wszystkich potencjalnych churnerów

## 🛠️ Techniki

1. **ROC Curve** - analiza różnych thresholds
2. **Precision-Recall Curve** - dla imbalanced data
3. **Business Cost Function** - custom optimization
4. **Threshold Moving** - od default 0.5 do optimal

## 📈 Wyniki

- Recall zwiększony z 65% do 85%
- Precision spadł z 70% do 60% (akceptowalne)
- Znacząco mniej missed churners

---

**Status:** ✅ Ukończony  
**Część serii:** 3/5 Churn Prediction
