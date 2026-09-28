Sterowanie czterema sygnalizatorami świetlnymi
Opis projektu

Program przeznaczony dla Arduino steruje czterema sygnalizatorami świetlnymi oznaczonymi jako A, B, C oraz D.

Każdy sygnalizator posiada trzy diody LED:

🔴 czerwone światło,

🟡 żółte światło,

🟢 zielone światło.

Program realizuje ustaloną sekwencję zmiany świateł, wykorzystując funkcje digitalWrite() oraz delay().

Podłączenie
Sygnalizator	Czerwone	Żółte	Zielone
A	13	12	11
B	10	9	8
C	7	6	5
D	4	3	2

Każda dioda LED powinna być podłączona do odpowiedniego pinu Arduino, najlepiej przez rezystor ograniczający prąd.

Inicjalizacja

W funkcji setup() wszystkie piny używane przez diody są ustawiane jako wyjścia (OUTPUT).

pinMode(redA, OUTPUT);
pinMode(yellowA, OUTPUT);
pinMode(greenA, OUTPUT);


Analogicznie ustawiane są piny pozostałych trzech sygnalizatorów.

Działanie programu

Program działa w nieskończonej pętli loop().

1. Sygnalizator A — zielone

A: 🟢 zielone

B: 🔴 czerwone

C: 🔴 czerwone

D: 🔴 czerwone

Czas: 9 sekund

2. Zmiana A/B

Włączane są światła żółte:

A: 🟡

B: 🟡

Czas: 1 sekunda

3. Sygnalizator B — zielone

A: 🔴 czerwone

B: 🟢 zielone

C: 🔴 czerwone

Czas: 5 sekund

4. Zmiana B/C

Włączane są światła żółte:

B: 🟡

C: 🟡

Czas: 1 sekunda

5. Sygnalizator C — zielone

B: 🔴 czerwone

C: 🟢 zielone

D: 🔴 czerwone

Czas: 5 sekund

6. Zmiana C/D

Włączane są światła żółte:

C: 🟡

D: 🟡

Czas: 1 sekunda

7. Sygnalizator D — zielone

Następnie program przechodzi do kolejnego etapu sterowania sygnalizatorem D.

8. Powrót do początku

Po wykonaniu całej sekwencji program wraca do początku funkcji loop() i cykl rozpoczyna się ponownie.

Wykorzystane funkcje
pinMode()

Ustawia sposób działania pinu Arduino.

pinMode(greenA, OUTPUT);

digitalWrite()

Włącza lub wyłącza diodę:

digitalWrite(greenA, HIGH); // włączenie
digitalWrite(greenA, LOW);  // wyłączenie

delay()

Zatrzymuje wykonywanie programu na określony czas w milisekundach:

delay(5000);


5000 ms = 5 sekund.

Ważna uwaga

Program korzysta z delay(), dlatego podczas oczekiwania Arduino nie wykonuje innych zadań. Przy bardziej rozbudowanym projekcie można zastąpić delay() funkcją opartą na millis(), co pozwoli na jednoczesną obsługę innych elementów układu.

Wymagane elementy

Arduino, np. Arduino Uno,

4 × czerwona dioda LED,

4 × żółta dioda LED,

4 × zielona dioda LED,

12 × rezystor ograniczający prąd,

płytka stykowa,

przewody połączeniowe.

Cel projektu

Celem projektu jest demonstracja sterowania kilkoma sygnalizatorami świetlnymi za pomocą mikrokontrolera Arduino oraz poznanie podstawowych funkcji:

konfiguracji pinów,

sterowania wyjściami cyfrowymi,

tworzenia sekwencji zdarzeń,

wykorzystania opóźnień czasowych.
