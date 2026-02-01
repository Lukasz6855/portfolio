# Churn Prediction - Model Explainability

> Interpretacja modelu predykcji odejść klientów przy użyciu SHAP

## 📋 Opis Projektu

Piąty i ostatni krok serii Churn Prediction. Koncentruje się na interpretowalności modelu: dlaczego model przewiduje churn?

## 🎯 Cel

- Zrozumienie decyzji modelu
- Identyfikacja najważniejszych czynników churn
- Wyjaśnienie predykcji dla biznesu
- Trust & transparency w AI

## � Jupyter Notebook

<div class="grid cards" markdown>
-   [:octicons-book-16: Zobacz Notebook](../notebooks/churn_explainability.html){ .md-button .md-button--primary target="_blank" }
    
    Model explainability: SHAP values, feature importance i interpretacja decyzji AI.
</div>

<div class="grid cards" markdown>
-   [:octicons-mark-github-16: GitHub Repository](https://github.com/Lukasz6855/ML-portfolio/tree/main/08_churn_model_explainability){ .md-button .md-button--primary target="_blank" }
</div>

## �🛠️ Technologie

- **SHAP** (SHapley Additive exPlanations)
- **LIME** (Local Interpretable Model-agnostic Explanations)
- **Feature Importance** (built-in)
- **Partial Dependence Plots**

## 📊 Rodzaje Wyjaśnień

### 1. Global Explainability
- Feature importance (który feature jest najważniejszy?)
- SHAP summary plots
- Ogólne trendy w danych

### 2. Local Explainability
- SHAP values dla pojedynczej predykcji
- Dlaczego TEN klient jest churnerem?
- LIME explanations

## 📈 Key Findings

**Top 5 czynników churn:**
1. Contract type (month-to-month)
2. Total charges
3. Tenure (jak długo jest klientem)
4. Internet service type
5. Payment method

**SHAP Insights:**
- Month-to-month contract +45% churn probability
- Long tenure (>2 years) -30% churn probability
- High monthly charges +20% churn probability

## 💡 Business Actions

Na podstawie explainability:
- Promować longer contracts (discounts)
- Retention campaigns dla nowych klientów (<6 months)
- Review pricing dla high-paying customers
- Improve customer service

---

**Status:** ✅ Ukończony  
**Część serii:** 5/5 Churn Prediction  
**Tech:** SHAP + LIME
