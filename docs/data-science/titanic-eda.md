# Analiza EDA - Titanic

> Eksploracyjna analiza danych pasażerów Titanica - zaawansowane techniki EDA

## 📋 Opis Projektu

Kompleksowa analiza eksploracyjna (EDA) zbioru danych pasażerów RMS Titanic. Projekt bada czynniki wpływające na przeżycie katastrofy poprzez szczegółową analizę danych demograficznych, społeczno-ekonomicznych i struktury podróży.

## 🎯 Cel Analizy

Zrozumienie czynników wpływających na przeżycie katastrofy Titanica:
- Analiza rozkładu przeżywalności według różnych cech
- Identyfikacja grup ryzyka
- Odkrycie ukrytych wzorców w danych
- Przygotowanie insightów do modelowania ML

## � Jupyter Notebook

<div class="grid cards" markdown>
-   [:octicons-book-16: Zobacz Notebook](../notebooks/Zad.2_Titanic_EDA.html){ .md-button .md-button--primary target="_blank" }
    
    Interaktywny notebook z kompleksową analizą eksploracyjną Titanica.
</div>

## �📊 Dataset

**Titanic Dataset** (Kaggle):
- **891 pasażerów** w zbiorze treningowym
- **12 zmiennych** (6 numerycznych, 5 kategorycznych, 1 target)
- **Przeżyło:** 342 (38.4%)
- **Nie przeżyło:** 549 (61.6%)

### Zmienne:
- **PassengerId** - ID pasażera
- **Survived** - czy przeżył (0/1) - TARGET
- **Pclass** - klasa podróży (1/2/3)
- **Name** - imię i nazwisko
- **Sex** - płeć
- **Age** - wiek
- **SibSp** - liczba rodzeństwa/małżonków na pokładzie
- **Parch** - liczba rodziców/dzieci na pokładzie
- **Ticket** - numer biletu
- **Fare** - cena biletu
- **Cabin** - numer kabiny
- **Embarked** - port zaokrętowania (C/Q/S)

## 🛠️ Technologie

- **Python** - język programowania
- **Pandas** - manipulacja danymi
- **NumPy** - operacje numeryczne
- **Matplotlib & Seaborn** - wizualizacje
- **Jupyter Notebook** - interaktywna analiza

## 📈 Przeprowadzone Analizy

### 1. Przegląd i Czyszczenie Danych

**Braki danych:**
```python
df.isnull().sum()

Age:        177 (19.9%)
Cabin:      687 (77.1%)
Embarked:   2 (0.2%)
```

**Strategia uzupełniania:**
- Age: mediana według Pclass i Sex
- Embarked: najczęstsza wartość (S)
- Cabin: pozostawiono jako missing (high cardinality)

**Outliers:**
- Fare: kilka bardzo wysokich wartości (suite'y)
- Age: rozkład normalny, brak ekstremalnych wartości

### 2. Analiza Przeżywalności

**Ogólna przeżywalność: 38.4%**

**Według płci:**
```
Kobiety:  74.2% przeżyło 🔥
Mężczyźni: 18.9% przeżyło
```

**Według klasy:**
```
1st class: 62.9% przeżyło 🎩
2nd class: 47.3% przeżyło
3rd class: 24.2% przeżyło
```

**Według wieku:**
```
Dzieci (< 18):  54% przeżyło 👶
Dorośli (18-60): 38% przeżyło
Seniorzy (> 60): 22% przeżyło
```

### 3. Feature Engineering

**Nowe cechy utworzone:**

```python
# Rodzina na pokładzie
df['FamilySize'] = df['SibSp'] + df['Parch'] + 1

# Czy samotny pasażer
df['IsAlone'] = (df['FamilySize'] == 1).astype(int)

# Tytuł z imienia
df['Title'] = df['Name'].str.extract(' ([A-Za-z]+)\.', expand=False)

# Kategoria wieku
df['AgeGroup'] = pd.cut(df['Age'], bins=[0, 18, 60, 100], 
                        labels=['Child', 'Adult', 'Senior'])

# Kategoria ceny biletu
df['FareGroup'] = pd.qcut(df['Fare'], q=4, 
                          labels=['Low', 'Medium', 'High', 'VeryHigh'])
```

### 4. Korelacje i Zależności

**Najsilniejsze korelacje z Survival:**
1. **Sex** (female) → +0.54
2. **Pclass** (1st) → +0.34
3. **Fare** (higher) → +0.26
4. **Embarked** (C - Cherbourg) → +0.17

**Insights:**
- Kobiety miały >4x większą szansę przeżycia
- 1st class >2.5x większą szansę niż 3rd class
- Rodziny 2-4 osobowe lepsze przeżycie niż samotni/duże rodziny
- Dzieci miały priorytet w łodziach ratunkowych

### 5. Analiza Grup

**"Women and children first":**
```python
# Kobiety i dzieci
women_children = df[(df['Sex'] == 'female') | (df['Age'] < 18)]
survival_rate = women_children['Survived'].mean()  # 69.3%

# Mężczyźni dorośli
adult_men = df[(df['Sex'] == 'male') & (df['Age'] >= 18)]
survival_rate = adult_men['Survived'].mean()  # 16.7%
```

**Efekt klasy społecznej:**
- 1st class female: 96.8% przeżyło! 🎩👸
- 3rd class male: 13.5% przeżyło
- Różnica: 83.3 punktów procentowych

## 📊 Kluczowe Wnioski

!!! success "Główne Czynniki Przeżycia"
    1. **Płeć** - najsilniejszy predyktor (kobiety >4x więcej)
    2. **Klasa podróży** - status społeczno-ekonomiczny
    3. **Wiek** - dzieci miały priorytet
    4. **Rozmiar rodziny** - małe/średnie rodziny lepiej

!!! warning "Grupy Wysokiego Ryzyka"
    - Mężczyźni w 3rd class (tylko 13.5% przeżyło)
    - Samotni pasażerowie
    - Osoby starsze (> 60 lat)
    - Pasażerowie z Southampton (port zaokrętowania)

!!! info "Feature Importance"
    - **Sex, Pclass, Age** - najbardziej informatywne
    - **Fare** - koreluje z Pclass
    - **Embarked** - słaby predyktor
    - **Cabin** - za dużo braków, mało użyteczne

## 📁 Zawartość Projektu

- **`Zad.2_Titanic_EDA.ipynb`** - główny notebook z analizą
- **`26__titanic.csv`** - zbiór danych

## 🎓 Czego się Nauczyłem

- **Zaawansowane EDA** - kompleksowa analiza z feature engineering
- **Braki danych** - strategie imputacji w zależności od typu zmiennej
- **Feature Engineering** - tworzenie nowych cech z istniejących
- **Storytelling z danych** - odkrywanie narracji w danych historycznych
- **Analiza grup** - segmentacja i porównanie subpopulacji
- **Domain Knowledge** - wykorzystanie wiedzy historycznej (women and children first)

## 📝 Wnioski Biznesowe

**Gdyby powtórzyć podróż:**
1. Zapewnić więcej łodzi ratunkowych
2. Lepsze procedury ewakuacji dla 3rd class
3. Priorytet dla kobiet, dzieci i rodzin
4. Lepsza komunikacja między klasami
5. Szkolenia załogi w ewakuacji

**Machine Learning Insights:**
- Sex, Pclass, Age to top 3 features
- FamilySize i Title (z Name) to dobre engineered features
- Cabin można pominąć (za dużo braków)
- Imbalanced dataset - potrzeba stratified sampling

## 🔗 Powiązane Projekty

- [Iris EDA](irisy-eda.md) - podstawy EDA
- [Titanic Classification](../machine-learning/titanic-classification.md) - modelowanie ML

---

**Status projektu:** ✅ Ukończony  
**Notebook:** Jupyter (Python)  
**Poziom:** Średniozaawansowany  
**Czas analizy:** ~3-4 godziny  
**Dataset:** Titanic (Kaggle)  
**Insights:** 8 głównych wniosków, 15+ wizualizacji
