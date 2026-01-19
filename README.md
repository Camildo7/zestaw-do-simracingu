# Zestaw do simracingu

## O projekcie

Celem projektu było zaprojektowanie i zbudowanie kompletnego, budżetowego systemu sterowania do symulatorów jazdy. System składa się z bazy kierownicy w technologii **Direct Drive** (bezpośrednie przełożenie napędu) z mechanizmem sprzężenia zwrotnego, bezprzewodowej kierownicy oraz zestawu manipulatorów nożnych.

Projekt został zrealizowany jako zaliczenie z przedmiotu Systemy wbudowane. Głównym założeniem było stworzenie alternatywy dla komercyjnych rozwiązań, zachowując wysoki moment obrotowy (ok. 15Nm) i precyzję sterowania przy znacznie niższych kosztach.

## Funkcjonalności

### 1. Baza Direct Drive
* **Silnik:** Wykorzystano silnik bezszczotkowy odzyskany z hoverboardu, generujący ok. 15Nm momentu obrotowego.
* **Sterowanie:** Oparte na kontrolerze MKS XDRIVE mini zintegrowanym ze sterownikiem silnika.
* **Enkoder:** Magnetyczny MT6701 zamontowany w osi obrotu dla precyzyjnego odczytu położenia.
* **Chłodzenie i obudowa:** Projekt otwarty na modyfikacje (elementy drukowane 3D).

### 2. Kierownica
* **Komunikacja:** Bluetooth Low Energy (BLE) - brak plączącego się kabla podczas obrotu.
* **Interfejs:** 14 programowalnych przycisków funkcyjnych.
* **Sygnalizacja:** Diody LED informujące o stanie połączenia i parowania.
* **Zasilanie:** Akumulator Li-Ion z modułem ładowania TP4056.

### 3. Manipulatory nożne
* **Komunikacja:** Przewodowa dla zapewnienia minimalnych opóźnień.
* **Gaz:** Oparty na precyzyjnym potencjometrze.
* **Hamulec (Load Cell):** Wykorzystuje belkę tensometryczną (120kg) oraz wzmacniacz HX711. Pozwala to na sterowanie siłą nacisku, co symuluje hydrauliczny układ hamulcowy i pozwala budować pamięć mięśniową.
* **Software:** Zaimplementowana filtracja sygnału, kalibracja oraz "martwe strefy" eliminujące szumy.

## Specyfikacja Sprzętowa

### Baza Direct Drive
* **Silnik:** Silnik od hoverboardu (ok. 15Nm)
* **Kontroler:** MKS Xdrive mini
* **Enkoder:** MT6701
* **Zasilacz:** 24V 20.8A (500W)

### Kierownica
* **Mikrokontroler:** ESP32-S3-NANO
* **Zasilanie:** Stabilizator TPS63020, Ładowarka TP4056, Akumulator Li-Ion
* **Przyciski:** 14x Tactile Switch

### Manipulatory nożne
* **Mikrokontroler:** ESP32-S3-NANO
* **Czujnik Hamulca:** Belka tensometryczna 120kg + Wzmacniacz HX711
* **Czujnik Gazu:** Potencjometr liniowy

## Technologie i biblioteki
Projekt oprogramowania został napisany z wykorzystaniem:
* **USBHIDGamepad** - obsługa komunikacji USB dla manipulatorów nożnych.
* **BleGamepad** - obsługa komunikacji Bluetooth dla kierownicy.
* **HX711** - obsługa belki tensometrycznej.

## Inspiracje i źródła

Niniejszy projekt powstał w oparciu o analizę istniejących rozwiązań Open Source oraz DIY.

* **Baza Direct Drive:** Wzorowana na projekcie [FFBeast](https://ffbeast.github.io/docs/en/wheel.html).
* **Kierownica:** Projekt mechaniczny i design inspirowany [projektem z Thingiverse](https://www.thingiverse.com/thing:4891321).
* **Manipulatory nożne:** Konstrukcja mechaniczna wzorowana na [DIY Sim Racing Pedals](https://www.diysimstudio.com/product/diy-sim-racing-pedals/).

## Autorzy

* Michał Leszczyński
* Kamil Dobek
* Nikodem Walkowiak

**Politechnika Poznańska**
