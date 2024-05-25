![Zweierkomplement.png](Attachments/Zweierkomplement.png)
Das erste Bit codiert das Vorzeichen (Sign Bit), was weniger Bits für die eigentliche Zahl übrig lässt.

## Darstellung negativer Zahlen

- Um eine negative Zahl darzustellen, wird jede 0 durch eine 1 und jede 1 durch eine 0 ersetzt (Bitweise Negation).
- Dann wird 1 addiert.
- Diese Darstellung enthält ein "Vorzeichenbit".

## Subtraktion in Komplementdarstellung

- Der Vorteil besteht darin, dass die Subtraktion als Addition einer negativen Zahl behandelt werden kann.
- Es wird nur ein Algorithmus oder Schaltwerk benötigt.
- Das Problem besteht jedoch in einem möglichen Overflow oder einer Bereichsüberschreitung.