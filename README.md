# Algorytmy sztucznej inteligencji do automatycznego usuwania czaszki z obrazów MRI T1-zależnych
Praca magisterska - **Bartosz Pragacz**

Ten projekt jest licencjonowany na zasadach [MIT License](https://github.com/Bartek46/Praca_magisterska/blob/main/LICENSE).

## Użycie
Plik `Trening_U_Net_3D_.ipynb` pozwala przeprowadzić szkolenie modeli, zawiera architekturę modelu, przygotowanie danych oraz proces uczenia.

Plik `Predykcja_U_Net_3D.ipynb` służy do przeprowadzenia predykcji, pozwala porównać maskę mózgu z predykcji z oryginalną maską.

Wagi modeli z uwagi na swój rozmiar znajdują się na [dysku Google](https://drive.google.com/drive/folders/1MXlrCcy5mtmkSDpyKm77uWePz4GvoqGH?usp=sharing), folder `Modele` należy umieścić w tym samym miejscu co pliki z kodem.

### Zastrzeżenie
Zarówno algorytmy uczenia jak i predykcji zostały przygotowane do uruchamiania na platformie `Kaggle`, dostępne tam zasoby pozwalają wczytać wszystkie dane jednocześnie.\
Natomiast sprzęt osobisty zazwyczaj nie jest wystarczający, dlatego powinno się wczytywać tylko wycinek zbioru.\
Kod nie został przygotowany w tym celu zatem nie można wczytywać wybranych plików, jedynie określoną liczbę pierwszych plików. Dlatego chcąc wczytać np. trzynasty skan zbioru testowego należy wczytać co najmniej trzynaście skanów. 

## Architektura modelu
Model stworzono w oparciu o architekturę  U-Net. Składa się z 25.9 mln parametrów. 
![4  mój U-Net v3](https://github.com/user-attachments/assets/022db2d4-bccb-43a5-98e7-98e62221f498)



## Wyniki
Z uwagi na zidentyfikowany problem, zaproponowano stworzenie trzech takich samych modeli wzdłuż każdej osi skanu (czołowej, poprzecznej i strzałkowej), połączono trzy modele w jeden `model łączony`.

Otrzymując następujące wyniki.

![image](https://github.com/user-attachments/assets/d4d21477-2793-4961-a49c-a6eaa2dce643)

Wyniki algorytmu porównano z wynikami z artykułu naukowego [3D U-Net for skull stripping in brain MRI](https://www.researchgate.net/publication/331017012_3D_U-Net_for_skull_stripping_in_brain_MRI).

![6  pornowanie metryk modeli](https://github.com/user-attachments/assets/b1f27bf9-e1e2-486a-8f1e-d513fe6a6580)
