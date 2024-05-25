## BCD Code
- Der BCD-Code (Binary Coded Decimal) wandelt jede Ziffer in binäre Form um.
- Häufig genutzt als Zahlenformat in COBOL.
- Es ermöglicht die präzise Darstellung von Brüchen.
- Rundungsfehler werden vermieden, was besonders wichtig ist in Bereichen wie Versicherungen und Bankwesen.
	
	| 7    | 9    | 3    |
	|------|------|------|
	| 0111 | 1001 | 0011 |

## Wissenschaftliche Notation
- Jede reelle Zahl lässt sich ausdrücken durch $± Mantisse \times Basis^{Exponent}$
- Die Basis im wissenschaftlichen System ist 10.
- Im Rechnersystem ist die Basis 2, bzw.  $2^{n}$, wobei n die Anzahl der Bits in der Darstellung ist.

	`3.1415926 = 3.1415926 x 10 = 1.5707963 x 2`

## ASCII Code

- Der ASCII-Code (American Standard Code for Information Interchange) ist ein Zeichensatz zur Darstellung von Text in Computern.
- Er besteht aus 127 Zeichen, die jeweils mit 7 Bits codiert werden.
- Dieser Zeichensatz umfasst das Alphabet, Zahlen, Sonderzeichen und Steuerzeichen.
- Eine Erweiterung des ASCII-Codes ermöglicht die Darstellung von 256 Zeichen durch die Verwendung von 8 Bits.

#### ASCII Tabelle

![ASCII%20Table.png](Attachments/ASCII%20Table.png)


- Die ASCII-Tabelle (American Standard Code for Information Interchange) ist ein Zeichensatz zur Darstellung von Text in Computern.
- Sie besteht aus 128 Zeichen, von denen die ersten 32 Steuerzeichen sind.
- Die Steuerzeichen sind anhand ihrer Bitkombinationen erkennbar:
    - Die Bitkombinationen b7-b5 sind entweder 000 oder 001 und zusätzlich 0100000 (SP) und 1111111 (DEL).
    - Die Bitkombinationen b4-b1 kodieren dual die Dezimalzahlen 0-9 (BCD-Code).
    - Die Bitkombinationen b7-b5 haben den Wert 011.
    - b4-b1 sind gleich b7-b5, um 100 bei Großbuchstaben und 110 bei Kleinbuchstaben.

#### Bei Vereinbarung einer geraden Parität:
Ein Prüfbit wird hinzugefügt, so dass die Gesamtzahl der Eins-Bits (1) einschließlich des Prüfbits gerade ist.

#### Bei Vereinbarung einer ungeraden Parität:
Ein Prüfbit wird hinzugefügt, so dass die Gesamtzahl der Eins-Bits (1) einschließlich des Prüfbits ungerade ist.



## Bild-Codierung 
- Jedes Pixel enthält eine Farbinformation, die kodiert und gespeichert wird. 
- Für Schwarz-Weiß-Bilder gilt: 1 Pixel = 1 Bit. 
- Bei Graustufen-Bildern gilt: 1 Pixel = 8 Bit. 
- High Color verwendet: 1 Pixel = 16 Bit. 
- True Color verwendet: 1 Pixel = 24 Bit. 
- Die DPI (dots per inch) geben an, wie viele Pixel pro Zoll vorhanden sind. 
- 1 Zoll entspricht 2,54 cm. 

#### Beispiel 
- Bildgröße: 6 x 4 Zoll. 
- Auflösung: 300 DPI. 
- Farbtiefe: True Color (24 Bit pro Pixel). 

```
Speicherbedarf
300 x 6 x 300 x 4 x 3 = 6 480 000 : 106 Byte = 6.48 MB
```