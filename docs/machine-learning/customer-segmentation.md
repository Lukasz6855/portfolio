# Customer Segmentation

> Segmentacja klientów centrum handlowego przy użyciu K-Means clustering

## 📋 Opis Projektu

Projekt segmentacji klientów wykorzystujący algorytm K-Means i PyCaret. Model automatycznie dzieli klientów na grupy o podobnych zachowaniach zakupowych, umożliwiając targetowane kampanie marketingowe.

## 🎯 Cel Biznesowy

- Identyfikacja grup klientów o podobnych zachowaniach
- Personalizacja ofert marketingowych
- Optymalizacja strategii sprzedaży
- Lepsze zrozumienie bazy klientów

## � Jupyter Notebook

<div class="grid cards" markdown>
-   [:octicons-book-16: Zobacz Notebook](../notebooks/customer_segmentation.html){ .md-button .md-button--primary target="_blank" }
    
    Segmentacja klientów z K-Means: analiza, clustering i business insights.
</div>

## �📊 Dataset

**Mall Customers Dataset**

Cechy:
- Customer ID
- Gender (płeć)
- Age (wiek)
- Annual Income (roczny dochód w k$)
- Spending Score (punkty wydatków 1-100)

## 🛠️ Technologie

- Python, PyCaret (Clustering)
- Scikit-learn (K-Means)
- Pandas, NumPy
- Matplotlib, Seaborn

## 📈 Wyniki

**Optymalna liczba klastrów:** 5 segmentów

### Zidentyfikowane Segmenty:

1. **High Value Customers** 💎
   - Wysoki dochód + High spending
   - Premium target group

2. **Potential Customers** 🎯
   - Wysoki dochód + Low spending
   - Opportunity for upselling

3. **Average Customers** 👥
   - Średni dochód + Średnie spending
   - Largest segment

4. **Young Shoppers** 👦
   - Niski dochód + High spending
   - Future high-value customers

5. **Budget Conscious** 💰
   - Niski dochód + Low spending
   - Require promotional offers

## 💡 Insights Biznesowe

**Rekomendacje marketingowe:**
- Segment 1: Luxury products, VIP programs
- Segment 2: Upselling campaigns, product recommendations
- Segment 3: Loyalty programs, seasonal promotions
- Segment 4: Youth-oriented products, flexible payment
- Segment 5: Discounts, budget options

## 🎓 Czego się Nauczyłem

- K-Means clustering i wybór optymalnej liczby klastrów
- PyCaret dla unsupervised learning
- Business interpretation of clusters
- Visualization of segmentation results

---

**Status:** ✅ Ukończony  
**Segmenty:** 5 grup klientów  
**Algorytm:** K-Means (PyCaret)
