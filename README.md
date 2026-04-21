# Przewidywanie temperatury we wrześniu w mieście Zamość
## Pliki
Projekt znajudję się w pliku weather_forecast_Zamosc.ipynb natomiast dane wykorzystane do projektu znajdują się w pliku pogoda_zamosc.csv.
## Cel projketu
Ten projekt polegał na stworzeniu modelu nauczania maszynowego opertego na sieciach neuronowych służącego do przewidywania pogody w mieście Zamość w miesiący wrzesień.
## Charakterystyka danych:
Do wykonania zadania wykorzystano temperatury średnie [°C] i opady [mm] w mieście Zamość we wrześniach w latach 2023, 2024 oraz 2025.Dane podzielono na trzy zbiory: (1) zbiórtreningowy (wrzesień 2023 oraz pierwsza połowa września 2024), (2) zbiór walidacyjny (druga połowa września 2024) oraz (3) zbiór testowy (wrzesień 2025).

Wykres z przedstawionymi realnymi temperaturami we wrześniu w poszczególnych latach zamieszczono poniżej:
<img width="682" height="410" alt="image" src="https://github.com/user-attachments/assets/39daa85d-897b-4189-9c11-fd861d30a824" />

## Opis modeli:
Stworzono 5 modeli:
1) model regresji liniowej – zastosowano optymalizator Adam oraz learning_rate = 0.01
2) model 1 sieci neuronowej opartej tylko na temperaturze -była to sieć wielowarstwowa gdzie zastosowano funkcję aktywacji ReLU, optymalizator Adam, oraz learning_rate = 0.01
3) model 2 sieci neuronowej opartej tylko na temperaturze – także sieć wielowarstwowa z funkcją aktywacji LeakyReLU, optymalizatorem SGD, learnining_rate = 0.0005 oraz z dodaną regularyzacją L2
4) model 3 sieci neuronowej opartej tylko na temperaturze – także sieć wielowarstwowa z funkcją aktywacji LeakyReLU, optymalizatorem Adam, learning_rate = 0.005 oraz z dodana regularyzacją L2
5)model sieci neuronowej opartej zarówno na temperaturze jak i opadach – także sieć wielowarstwowa z funkcją aktywacji ReLU, optymalizatorem Adam oraz learning_rate = 0.005

## Krzywa uczenia na zbiorze treningowym i walidacyjnym dla każdego modelu:
<img width="410" height="315" alt="image" src="https://github.com/user-attachments/assets/d962e81f-c9dd-4ab5-9f3d-92c4e08b536d" />
<img width="424" height="323" alt="image" src="https://github.com/user-attachments/assets/56cefb25-ad25-489c-8597-8b5502c67d37" />
<img width="399" height="306" alt="image" src="https://github.com/user-attachments/assets/e31742a9-eb05-4d81-a943-baa30bc4493f" />
<img width="388" height="300" alt="image" src="https://github.com/user-attachments/assets/f702369e-7002-40b1-bc9f-a7776f3657bf" />
<img width="399" height="316" alt="image" src="https://github.com/user-attachments/assets/959f9f66-7dab-4535-8234-2e60895b5dfb" />

## Wartość funkcji kosztu na zbiorze treningowym, walidacyjnym i testowym po ostatniej epoce:										
<img width="705" height="411" alt="image" src="https://github.com/user-attachments/assets/58ee01ab-25d6-4a4d-9f98-cb33af5599c9" />

## Wartości rzeczywiste i przewidywania na zbiorze testowym:
<img width="707" height="416" alt="image" src="https://github.com/user-attachments/assets/7af9c8a6-5f06-4033-b2d0-385880da77d4" />

## Prognoza kilku chwil w przyszłość porównana z wartościami rzeczywistymi:
Prognozę 10 dni w przyszłości wykonano za pomocą drugiego modelu sieci neuronowych (uzyskał najlepsze wyniki spośród wszystkich modeli sieci neuronowych dla zbioru testowego).
<img width="641" height="394" alt="image" src="https://github.com/user-attachments/assets/ea68c8d6-368e-49ed-b8b2-4e9654da7971" />

## Komentarz otrzymanych wyników:
Prognoza przyszłości jest wiarygodna maksymalnie na około 2-3 dni do przodu, chociaż jej ogólny trend spadku pokrywa się w pewien sposób z prawdziwą temperaturą.
Analizując pozostałe wyniki, zauważono, że najlepszym modelem okazała się model regresji liniowej oraz model 2 oparty na sieciach neuronowych. Okazało się także, że wykorzystanie opadów do stworzenia modelu sieci neuronowej znacznie pogorszyło jej wyniki. Prawdopodobnie dlatego, że opady można uznać za coś mocno losowego i jeszcze cięższego do przewidzenia niż temperatura.

