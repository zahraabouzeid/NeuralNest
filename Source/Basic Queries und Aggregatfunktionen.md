## Daten abfragen
_**W**arum **g**eht **H**erbert **o**ft **l**aufen?_

```sql
SELECT [DISTINCT] * | Attributname, Attributname | Berechnetesfeld
FROM Tabellenname  
INNER | LEFT | RIGHT JOIN AndereTabelle ON Tabellenname.Attributname = AndereTabelle.Attributname
WHERE Bedingung
GROUP BY Attributname
HAVING Bedingung
ORDER BY Attributename [ASC | DESC]
LIMIT Anzahl;
```

>[!info]
> Das Unterschied zwischen HAVING und WHERE liegt daran, dass HAVING das Vergleich mit aggregierten Feldern ermöglicht. Erst nach der WHERE und GROUP BY sind die aggregierten Werte berechnet und können dann verglichen werden.
## Where Bedingungen

#### Mathematische Operationen
```sql
=, !=, <, >, <=, >=, +, =, -, *, /, DIV, %
```
#### Boolesche Operatoren
```sql
AND, OR, NOT
```
#### Bereichsoperator
```sql
BETWEEN X AND Y
```
#### Mengenvergleich
```sql
IN (Wert, Wert)
```
#### Leere Feldeinträge
```sql
IS NULL
```
#### Like (case insensitive)
Wert beginnt mit einem Kleinbuchstaben von a bis z gefolgt von beliebigen Zeichen:

```sql
WHERE Attributname LIKE '[a-z]%';
```

Wert beginnt mit dem Buchstaben a gefolgt von beliebigen Zeichen:
```sql
WHERE Attributname LIKE 'a%';
```

Wert enthält a als zweite Buchstabe gefolgt von beliebigen Zeichen:
```sql
WHERE Attributname LIKE '_a%';
```

Wert enthält den Buchstaben a an beliebiger Stelle:
```sql
WHERE Attributname LIKE '%a%';
```

Wert beginnt mit einem a oder A gefolgt von beliebigen Zeichen:
```sql
WHERE Attributname LIKE '[aA]%';
```

Wert beginnt mit einem Zeichen, das nicht a oder A ist, gefolgt von beliebigen Zeichen:
```sql
WHERE Attributname LIKE '[!aA]%';
```

Case Sensitive Vergleich
```sql
WHERE Attributname LIKE BINARY 'WERT';
```
**%** ist ein Wildcard während **_** ist ein Platzhalter
#### Reguläre Ausdrücke

```sql
WHERE Attributname REGEXP 'Pattern';
```

|Zeichen|Bedeutung|
|---|---|
|.|Ein beliebiges Zeichen außer einer neuen Zeile|
|^|Beginn einer Zeile|
|$|Ende einer Zeile|
|[...]|Ein einzelnes Zeichen aus der Menge|
|[^...]|Ein einzelnes Zeichen nicht aus der Menge|
|*|Null oder mehr Vorkommen|
|+|Ein oder mehr Vorkommen|
|?|Null oder ein Vorkommen|
|{n}|Genau n Vorkommen|
|{n,}|Mindestens n Vorkommen|
|{n,m}|Zwischen n und m Vorkommen|
|\||Alternativen (ODER)|
|(...)|Gruppierung von Zeichen|


## Datumsfunktionen
| Funktion                                       | Beschreibung                                                   |
| ---------------------------------------------- | -------------------------------------------------------------- |
| CURDATE()                                      | Gibt das aktuelle Datum zurück                                 |
| DATEDIFF(Enddatum, Startdatum)                 | Berechnet die Datumsdifferenz in Tagen                         |
| YEAR(Datum)                                    | Gibt das Jahr zurück                                           |
| MONTH(Datum)                                   | Gibt das Monat zurück                                          |
| DAY(Datum)                                     | Gibt den Tag zurück                                            |
| QUARTER(Datum)                                 | Gibt das Quartal zurück                                        |
| WEEK(Datum)                                    | Gibt die Woche zurück                                          |
| DATE_ADD(Datum, Intervall [DAY, SECOND, WEEK]) | Addiert das Intervall zum Datum                                |
| DATE_SUB(DATUM, Intervall [DAY, SECOND, WEEK]) | Subtrahiert das Intervall vom Datum                            |
| CURTIME()                                      | Gibt die aktuelle Systemzeit im Format hh:mm:ss zurück         |
| DAYOFWEEK(Datum)                               | Gibt den Wochentagsindex 1 bis 7 zurück und startet ab Sonntag |
| WEEKDAY(Datum)                                 | Gibt den Wochentagsindex 0 bis 6 zurück und started ab Montag  |
| DAYNAME(Datum)                                 | Gibt den Wochentagname in Englisch zurück                      |
| MONTHNAME(Datum)                               | Gibt den Monatsname in Englisch zurück                         |
| DATE_FORMAT(Datum, Formatter)                  | Gibt das Datum in einem bestimmten Format zurück               |
| TIME_FORMAT(Zeit, Formatter)                   | Gibt das Datum in einem bestimmten Format zurück               |

## Mathematische Funktionen
| Funktion                             | Beschreibung                                                                                                    |
| ------------------------------------ | --------------------------------------------------------------------------------------------------------------- |
| ROUND(Feld, Nachkomastellen)         | Rundet auf eine bestimmte Anzahl von Dezimalstellen                                                             |
| FLOOR(Feld)                          | Rundet auf die nächstkleinere ganze Zahl ab                                                                     |
| CEIL(Feld)                           | Rundet auf die nächsthöhere ganze Zahl auf                                                                      |
| PI()                                 | Gibt die Zahl π zurück                                                                                          |
| POW(Zahl, Exponent)                  | Gibt den Potenz zurück                                                                                          |
| RAND(CURTIME())                      | Initialisiert den Zufallszahlengenerator mit der Systemzeit und erstellt die erste Zufallszahl zwischen 0 und 1 |
| RAND()                               | Gibt nach der Initialisierung eine Zufallszahl zwischen 0 und inkl. 1                                           |
| TRUNCATE(Zahl, Stellen)              | Schneidet Nachkommazahlen nach der angegebenen Stelle ab                                                        |
| IFNULL(Attributname, 0)              | Ersetzt Null Werte mit dem angegebenen Wert                                                                     |
| COALESCE(Attributname, Attributname) | Gibt den ersten Ausdruck, der nicht NULL ist zurück                                                             |

## Stringfunktionen

| Funktion                         | Beschreibung                                       |
| -------------------------------- | -------------------------------------------------- |
| UPPER(String)                    | Wandelt ein String in Großbuchstaben               |
| LOWER(String)                    | Wandelt ein String in Kleinbuchstaben              |
| CONCAT(String, String)           | Fügt mehrere Strings zusammen                      |
| SUBSTRING(String, Start, Anzahl) | Extrahiert Buchstaben ab einer bestimmten Position |

## Aggregatsfunktionen

| Funktion    | Beschreibung                                                                |
| ----------- | --------------------------------------------------------------------------- |
| COUNT(Feld) | Zählt alle nicht-null-Werte innerhalb einer Spalte                          |
| COUNT(*)    | Zählt die Datensätze                                                        |
| SUM(Feld)   | Berechnet die Summe einer ganze Spalte                                      |
| AVG(Feld)   | Berechnet den Durchschnitt einer ganze Spalte (NULL-Werte zählen nicht mit) |
| MIN(Feld)   | Sucht den kleinsten Wert einer ganzen Spalte.                               |
| MAX(Feld)   | Sucht den größten Wert einer ganzen Spalte.                                 |
> [!warning]
> Nur die unbedingt erforderlichen Felder sollten im SELECT-Teil der Abfrage angegeben werden. Andere Felder sollten entweder in Klammern der Aggregatfunktionen oder in der GROUP BY-Klausel stehen. Alle Felder, die im SELECT-Teil der Abfrage stehen und nicht in einer Aggregatfunktion enthalten sind, müssen in der GROUP BY-Klausel aufgeführt sein. Andernfalls wird ein Fehler erzeugt.