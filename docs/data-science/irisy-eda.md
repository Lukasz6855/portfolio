# Analiza EDA - Irisy

> Klasyczna eksploracyjna analiza danych zbioru Iris - podstawy EDA i wizualizacji

## 📋 Opis Projektu

Kompleksowa analiza eksploracyjna (EDA) klasycznego zbioru danych Iris, zawierającego pomiary 150 kwiatów irysów należących do trzech gatunków. Projekt przedstawia fundamentalne techniki analizy danych i wizualizacji.

## 🎯 Cel Analizy

Poznanie struktury i charakterystyki zbioru Iris poprzez:
- Analizę statystyk opisowych
- Wizualizację rozkładów cech
- Identyfikację zależności między zmiennymi
- Ocenę separowalności gatunków

## � Jupyter Notebook

<div class="grid cards" markdown>
-   [:octicons-book-16: Zobacz Notebook](../notebooks/Zad.1_Iris_EDA_raport_presentation.html){ .md-button .md-button--primary target="_blank" }
    
    Interaktywny notebook z pełną analizą eksploratoraćjną zbioru Iris.
    
-   [:octicons-file-16: Zobacz Prezentację](../notebooks/Zad.1_Iris_EDA_raport_presentation.slides.html){ .md-button target="_blank" }
    
    Prezentacja w formacie slajdów HTML.
</div>

## �📊 Dataset

**Zbiór Iris** (Ronald Fisher, 1936):
- **150 obserwacji** (50 na gatunek)
- **3 gatunki:** Setosa, Versicolor, Virginica
- **4 cechy:** 
  - Długość działki kielicha (sepal length)
  - Szerokość działki kielicha (sepal width)
  - Długość płatka (petal length)
  - Szerokość płatka (petal width)

## 🛠️ Technologie

- **Python** - język programowania
- **Pandas** - manipulacja danymi
- **NumPy** - operacje numeryczne
- **Matplotlib** - wizualizacje podstawowe
- **Seaborn** - zaawansowane wizualizacje statystyczne
- **Jupyter Notebook** - interaktywna analiza

## 📈 Przeprowadzone Analizy

### 1. Wstępny Przegląd Danych
```python
# Podstawowe informacje
df.info()
df.describe()
df.head()

# Rozkład klas
df['species'].value_counts()
```

### 2. Analiza Jednowymiarowa (Univariate)

**Statystyki opisowe dla każdej cechy:**
- Średnia, mediana, odchylenie standardowe
- Minimum, maksimum, kwartyle
- Histogramy rozkładów

**Wizualizacje:**
- Histogramy dla każdej zmiennej
- Box plots dla identyfikacji outliers
- Density plots (rozkłady gładkie)

### 3. Analiza Dwuwymiarowa (Bivariate)

**Relacje między cechami:**
- Scatter plots (długość vs szerokość)
- Korelacje między zmiennymi
- Rozkłady dla każdego gatunku osobno

**Kluczowe obserwacje:**
- Petal length i petal width są silnie skorelowane
- Setosa jest łatwo separowalna od innych gatunków
- Versicolor i Virginica częściowo się pokrywają

### 4. Analiza Wielowymiarowa (Multivariate)

**Pair Plot:**
```python
sns.pairplot(df, hue='species')
```
- Wszystkie kombinacje par zmiennych
- Kodowanie kolorami według gatunku
- Histogramy na przekątnej

**Correlation Heatmap:**
```python
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
```
- Macierz korelacji między cechami
- Najsilniejsza korelacja: petal length ↔ petal width (0.96)

### 5. Analiza Separowalności Klas

**Box plots według gatunku:**
- Setosa ma wyraźnie mniejsze petal measurements
- Virginica ma największe wartości
- Versicolor pośrodku

**Violin plots:**
- Rozkłady wartości dla każdego gatunku
- Setosa najbardziej zwarta grupa
- Największa variability w Virginica

## 📊 Kluczowe Wnioski

!!! success "Separowalność Gatunków"
    - **Setosa** jest łatwo rozpoznawalna (małe petals)
    - **Versicolor i Virginica** trudniejsze do rozróżnienia
    - **Petal measurements** są lepszymi cechami niż sepal

!!! info "Korelacje"
    - **Petal length ↔ Petal width:** 0.96 (bardzo silna)
    - **Sepal length ↔ Petal length:** 0.87 (silna)
    - **Sepal width** słabo skorelowana z innymi cechami

!!! tip "Feature Selection"
    - Petal length i petal width są najbardziej informatywne
    - Możliwa redukcja wymiarów bez utraty informacji
    - 2D visualization (petal length vs width) wystarczy do separacji

## 📁 Zawartość Projektu

- **`Zad.1_Iris_EDA_raport_presentation.ipynb`** - główny notebook z analizą
- **`Zad.1_Iris_EDA_raport.pdf`** - raport w PDF
- **`Zad.1_Iris_EDA_raport_presentation.slides.html`** - prezentacja HTML
- **`25__iris.csv`** - zbiór danych

## 🎓 Czego się Nauczyłem

- **Podstawy EDA** - systematyczne podejście do analizy danych
- **Pandas & NumPy** - efektywna manipulacja danymi
- **Matplotlib & Seaborn** - tworzenie profesjonalnych wizualizacji
- **Statystyki opisowe** - interpretacja mean, median, std, quartiles
- **Analiza korelacji** - identyfikacja zależności między zmiennymi
- **Data storytelling** - wyciąganie wniosków z danych

## 📝 Metodologia EDA

1. **Załaduj dane** i sprawdź podstawowe informacje
2. **Posprzątaj dane** (braki, duplikaty, outliers)
3. **Analiza jednowymiarowa** - każda zmienna osobno
4. **Analiza dwuwymiarowa** - relacje między parami zmiennych
5. **Analiza wielowymiarowa** - kompleksowe wzorce
6. **Wnioski i hipotezy** - co dane nam mówią?

## 🔗 Powiązane Projekty

- [Titanic EDA](titanic-eda.md) - bardziej zaawansowana analiza
- [Titanic Classification](../machine-learning/titanic-classification.md) - modelowanie ML

---

**Status projektu:** ✅ Ukończony  
**Notebook:** Jupyter (Python)  
**Poziom:** Podstawowy  
**Czas analizy:** ~2 godziny  
**Dataset:** Iris (Fisher, 1936)
