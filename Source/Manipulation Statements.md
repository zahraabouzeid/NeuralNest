## Insert

**Datensätze in eine neue Tabelle einfügen**

```sql
CREATE TABLE mytable
SELECT column1, column2
FROM anothertable
```

**Datensätze in existierende Tabelle einfügen**
```sql
INSERT INTO mytable(col1, col2)
SELECT column1, column2
FROM anothertable
WHERE condition
```

## Delete
```sql
DELETE FROM mytable
WHERE column IN (
	SELECT mycol
	FROM anothertable 
	WHERE condition
)
```

## Update
**Einfache Aktualisierung**

```sql
UPDATE mytable 
SET col = data
WHERE condition
```

**Aktualisierung von mehr als eine Tabelle mit eine Subquery**
```sql
UPDATE artikel
INNER JOIN (
	SELECT ArtikelNr, (verkaufspreis* 3) AS wucherPreis
	FROM artikel
	WHERE verkaufspreis < 5
) AS sub ON sub.ArtikelNr = artikel.ArtikelNr
SET verkaufspreis = wucherPreis
WHERE wucherPreis > 2;
```

**Subquery in where**
```sql
UPDATE artikel
SET verkaufspreis = 5
WHERE verkaufspreis < (
SELECT avg(verkaufspreis)
FROM artikel art);
```

> [!warning]
> Gruppierung im `UPDATE` selber ist verboten, da eine Gruppierung nicht geändert werden kann

```sql
UPDATE Einkauf
INNER JOIN (
	SELECT EinkaufsNr, SUM(Verkaufspreis * Menge) AS betrag
	FROM Einkaufsposition
	GROUP BY EinkaufsNr
) AS sub
ON sub.EinkaufsNr = Einkauf.EinkaufsNr
SET Einkauf.Gesamtbetrag = sub.betrag
```

```sql
UPDATE Artikel
LEFT JOIN (
	SELECT artikel, COUNT(artikel) AS Verkaufsfrequenz
	FROM KdAuftragsPosition 
	GROUP BY artikel
) AS sub
ON sub.artikel = Artikel.ArtikelNr
SET Artikel.Verkaufspreis = Artikel.Verkaufspreis * 0.5
WHERE ifnull(Verkaufsfrequenz, 0) <= 6
```

>[!info]
> - `DELETE` und `UPDATE` haben nur eine Tabelle nach Schlüsselwort `FROM`, andere Tabellen verbindet man in Subqueries
> - Nach `DELETE` kommt die Subquery nur in WHERE und Zieltabelle wird mit Alias benutzt, und nur ein Datenfeld im SELECT
> - Bei `UPDATE` wird auch die Zieltabelle mit Alias benutzt
