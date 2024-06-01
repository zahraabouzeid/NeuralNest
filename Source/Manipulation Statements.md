Um Daten zu manipulieren benutzt man Befehle wie `INSERT`,  `UPDATE`, `DELETE`. Bei `DELETE` und `UPDATE` kommt nur eine Tabelle nach dem Schlüsselwort `FROM`, andere Tabellen verbindet man in Subqueries. Nach `DELETE` kommt die Subquery nur in der `WHERE` Klause und die Zieltabelle wird mit Alias benutzt. Bei `UPDATE` wird auch die Zieltabelle mit Alias benutzt

## Daten einfügen

#### Tabelle erstellen und Daten von einer anderen Tabelle einfügen

```sql
CREATE TABLE Zieltabelle
[AS] SELECT Spalte, Spalte 
FROM Quelltabelle;
```

#### Datensätze aus einer existierenden Tabelle einfügen

```sql
INSERT INTO Zieltabelle(Spalte, Spalte) 
SELECT (Quellspalte, Quellspalte 
FROM Quelltabelle 
WHERE Bedingung;
```

## Daten löschen
Datensätze aus einer Tabelle löschen, basierend auf einer Untertabelle 

```sql
DELETE FROM Tabellenname 
WHERE Spalte [NOT] IN (
	SELECT Spalte 
	FROM Quelltabelle 
	WHERE Bedingung 
);
```

## Daten ändern

#### Aktualisieren mehrere Tabellen mit einer Subquery

```sql
UPDATE Tabellenname 
INNER JOIN ( 
	SELECT Datenfeld, Datenfeld AS NeuerWert
	FROM AndereTabelle 
	WHERE Bedingung 
) as qryAndereTabelle ON qryAndereTabelle.Datendfeld = Tabellenname.Datenfeld 
SET Datenfeld = NeuerWert 
WHERE Bedingung
```

#### Aggregation
Gruppierung im `UPDATE` selber ist verboten, da eine Gruppierung nicht geändert werden kann.

```sql
UPDATE Einkauf
INNER JOIN (
	SELECT EinkaufsNr, SUM(Verkaufspreis * Menge) AS Betrag
	FROM Einkaufsposition
	GROUP BY EinkaufsNr
) AS qryEinkaufsposition
ON qryEinkaufsposition.EinkaufsNr = Einkauf.EinkaufsNr
SET Einkauf.Gesamtbetrag = qryEinkaufsposition.Betrag
```

**In der Fall einer Outer Join**
```sql
UPDATE Tabelle
LEFT JOIN (
	...
) qry ON qry.Datenfeld = Tabelle.Datenfeld
SET Datenfeld = NeuerWert
WHERE IFNULL(Datenfeld, 0) <= 6;
```




