## Fächerbeziehungen
Fächerbeziehungen sind Kombinationen von Beziehungen, die zu einem kartesischen Produkt führen. Ein kartesisches Produkt ist eine mathematische Operation, die alle möglichen Kombinationen von Elementen aus zwei oder mehr Mengen erzeugt.  `AVG` führt zu keinem kartesischen Produkt. Nur `COUNT` und `SUM` führen dazu.

| Nr  | Name   | Gruppe |
| --- | ------ | ------ |
| 1   | Sally  | A      |
| 2   | Ina    | A      |
| 3   | Cora   | A      |
| 4   | Rita   | A      |
| 5   | Nelly  | A      |
| 6   | Bertha | A      |
| 7   | Anna   | A      |

| Nr  | Name | Gruppe |
| --- | ---- | ------ |
| 1   | Joe  | A      |
| 2   | Tom  | A      |
| 3   | Sam  | B      |
| 4   | Ali  | B      |
| 5   | John | B      |
| 6   | Nick | B      |
Die folgende Subquery ergibt ein kartesiches Produkt: 
```sql
SELECT *
FROM Frauen
INNER JOIN Männer ON Frauen.Gruppe = Männer.Gruppe;
```

Das Ergebnis sieht wie folgendes aus:

| Nr  | Name  | Gruppe | Nr  | Gruppe |
| --- | ----- | ------ | --- | ------ |
| 1   | Sally | A      | 1   | Joe    |
| 1   | Sally | A      | 2   | Tom    |
| 2   | Ina   | A      | 1   | Joe    |
| 2   | Ina   | A      | 2   | Tom    |
| 3   | Cora  | A      | 1   | Joe    |
| 3   | Cora  | A      | 2   | Tom    |
| 4   | Rita  | A      | 1   | Joe    |
| 4   | Rita  | A      | 2   | Tom    |
Nach der Aggregation ist der Count(\*)  der Frauen und Männer die zur Gruppe A gehören 8 jeweils, anstatt 4 Frauen und 2 Männer. 

#### Lösung mit einer Subquery

```sql
SELECT Gruppe, COUNT(Frauen.Nr) AS FrauenAnzahl, MännerAnzahl
FROM Frauen
INNER JOIN (        
	SELECT Gruppe AS MännerGruppe, COUNT(Männer.Nr) AS MännerAnzahl
	FROM Männer
	GROUP BY Gruppe
) AS qryMänner ON Frauen.Gruppe = qryMänner.MännerGruppe
GROUP BY Gruppe;
```

Das Ergebnis des Subquery wird dann wie eine Tabelle behandelt und mit den anderen Tabellen in der FROM Klausel verknüpft.
## Aggregation und Nicht Aggregation
Eine Subquery wird auch benötigt, wenn wir einen Wert mit seinem aggregierten Wert vergleichen.
#### Ohne Gruppierung

```sql
SELECT SchülerNr, Note, Durschnittsnote
FROM Arbeitsnoten, 
(
	SELECT AVG(Note) AS Durschnittsnote
	FROM Arbeitsnoten
) AS qryArbeitsnoten -- wie Tabellenname
WHERE Note < Durschnittsnote;
```
#### Mit Gruppierung
```sql
SELECT SchülerNr, Arbeitsnoten.ArbeitsNr, Note, Durchschnitt  
FROM Arbeitsnoten 
INNER JOIN -- wegen die Gruppierung 
(
	SELECT ArbeitsNr, AVG(Note) AS Durchschnitt 
	FROM Arbeitsnoten  
	GROUP BY ArbeitsNr
) AS qryArbeitsnoten ON qryArbeitsnoten.ArbeitsNr = Arbeitsnoten.ArbeitsNr
WHERE Note < Durchschnitt;
```

## Mehrstufige Aggregationen
Es wird der aggregierte Wert eines aggregierten Wertes berechnet.

```sql
SELECT qryArbeitsnoten.Lehrer, AVG(Klassenarbeitdurschnitt) AS Lehrernotendurschnitt
FROM Arbeitsnoten 
INNER JOIN 
(
	SELECT Lehrer, ArbeitsNr, AVG(Note) AS Klassenarbeitdurschnitt      
	FROM Arbeitsnoten      
	GROUP BY Lehrer, ArbeitsNr
) AS qryArbeitsnoten ON qryArbeitsnoten.Lehrer = Arbeitsnoten.Lehrer
GROUP BY qryArbeitsnoten.Lehrer;
```

## Subquery in WHERE 

#### Vergleich mit Operatoren

```sql
SELECT Attributname, Attributname
FROM Tabellenname
WHERE Attributname < (
	SELECT AVG(Attributname)
	FROM Tabellenname
);
```

#### Vergleich mit IN
```sql
SELECT Attributname
FROM Tabellenname
WHERE Attributname [NOT] IN 
(
	SELECT Attributname
	FROM AndereTabelle
	WHERE Bedingung
)
```

## UNION
Zeilen mit gleichem Inhalt werden standardmäßig zu einer Zeile komprimiert.
```sql
SELECT Gruppe, Vorname AS Name, Geburtsdatum AS Geburtsdatum -- Diese Spalten ergeben die Spaltenüberschriften
FROM Frauen
UNION
SELECT Gruppe, Vorname, Geburtsdatum
FROM Männer
```


## Correlated Subqueries
Correlated Subqueries verknüpfen mit dem äußeren Select. Sie werden für **jede Zeile** neu ausgeführt. Dadurch sind sie sehr ineffizient.




>[!tips]
>- Nicht alle Felder, die im Subquery verwendet werden, benötigen außerhalb einen Alias. Wenn ein Feld im Subquery berechnet wird und dann außerhalb verwendet werden soll, ist ein Alias erforderlich, damit es im äußeren Select verwendet werden kann. Ebenso braucht ein Subquery, der sich in der FROM-Klausel befindet, einen Alias-Namen, um verwendet zu werden.
>- Ein Subquery wird benötigt, wenn die Beziehungskonstellation T **m-1** T **1-m** T vorliegt. Jedoch führt die Beziehungskonstellation T 1-mc T mc-1 T nicht zu einem kartesischen Produkt.
