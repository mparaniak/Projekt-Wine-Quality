# Przewidywanie Jakości Wina - Projekt
Projekt zrealizowany w ramach zajęć Programowanie 2

## 1. Opis danych i cel projektu
Zbiór danych (`WineQT.csv`) pochodzi z platformy Kaggle i zawiera informacje o fizykochemicznych właściwościach różnych wariacji wina (m.in. kwasowość, zawartość alkoholu, pH, cukier resztkowy).
**Celem projektu** było stworzenie modelu typu **regresja**, który na podstawie chemii wina potrafi przewidzieć jego ostateczną ocenę jakości (kolumna `quality` w skali od 3 do 8).

## 2. Zastosowane kroki i modele
W ramach projektu przeprowadzono:
* Eksplorację danych oraz analizę macierzy korelacji.
* Czyszczenie i skalowanie danych przy pomocy narzędzia `Pipeline` oraz `StandardScaler`.
* Implementację i porównanie trzech algorytmów uczenia maszynowego:
  1. Linear Regression (Regresja Liniowa)
  2. Decision Tree Regressor (Drzewo Decyzyjne)
  3. Random Forest Regressor (Las Losowy)

## 3. Optymalizacja i Wyniki
Najlepszym okazał się model **Random Forest Regressor**. 
Został poddany procesowi dostrajania hiperparametrów za pomocą dwóch technik: `GridSearchCV` oraz `RandomizedSearchCV`.

Najlepsze rezultaty przyniósł **Randomized Search** (hiperparametry: `n_estimators = 88`, `max_features = 3`).
Ostateczny błąd średniokwadratowy pierwiastkowy (**RMSE**) na ukrytym zbiorze testowym wyniósł **~0.53**. 
Oznacza to, że model jest bardzo precyzyjny i myli się średnio o zaledwie ~0.5 punktu podczas przewidywania oceny jakości nowych, nieznanych wcześniej win.
