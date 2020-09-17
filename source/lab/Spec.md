# TDD Workshop Übungen

## Übung I
## Übung II
* Gegeben sei ein 128 KiB EEPROM Baustein, der via SPI angeschlossen ist.
* Geschrieben wird der Baustein, indem nach dem Anziehen der CS Leitung zunächst eine 32 Bit Adresse gesandt wird und dann die zu schreibenden Daten. Das obere Bit der Adresse ist immer 0 (signalisiert "schreiben").
* Gelesen wird, indem nach dem Anziehen der CS Leitung zunächst eine 32 Bit Adresse gesandt wird und 0 Bytes (der Baustein schickt parallel die Daten die gelesen werden und inkrementiert die Leseadresse selbstständig). Das obere Bit der Adresse ist immer 1 (signalisiert "lesen").
* Nach dem "Loslassen" der CS Leitung geht der Baustein wieder in den Idle Zustand über, d.h. wenn erneut gelesen oder geschrieben werden soll muss zunächst wieder die entsprechende Adresse gesandt werden.
* Der Baustein interpretiert alle Adressen Modulo 131072 (d.h. wird ausserhalb der 128 KiB geschrieben oder gelesen wrapped die Adresse!).
* Euer gedachtes "BSP" für den SPI Zugang befindet sich unter sources/spi/spi.h

Aufgaben & Fragen:
* Was ist eine geeignete Ebene um Code zu testen, der mit diesem Baustein interagiert?
* Sollten diese Tests on- oder off-target durchgeführt werden (oder eine Mischung aus beidem?)?
* Schreibt einen minimalen Treiber inklusive Tests für den Baustein, der folgende Funktionen hat:
    * Schreiben von Daten
    * Lesen von Daten
* Beachtet dabei folgende Punkte:
    * Welche Fehler muss der Treiber auf API Seite abfangen?
    * Welche Möglichkeiten habt Ihr die API so zu gestalten, dass sie möglichst nicht falsch bedienbar ist?
