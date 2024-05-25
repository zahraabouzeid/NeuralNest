## Fächerbeziehungen
Fächerbeziehungen sind Kombinationen von Beziehungen, die zu einem kartesischen Produkt führen. Bei der Nutzung von Aggregatfunktionen wie  `SUM` und `COUNT` ist oft ein Zwischenergebnis mit einem Subquery erforderlich.

**Kartesischem Produkt**
```sql
SELECT Gruppe, COUNT(Frau.FNr), COUNT(Mann.MNr)
FROM Frau 
INNER JOIN Gruppe ON Frau.Gruppe = GruppenID
INNER JOIN Mann ON Mann.Gruppe = GruppenID
GROUP BY GruppenID;
```


**Aggregatfunktion in Subquery**

```sql
SELECT Gruppe, COUNT(Frau.FNr) AS FrauenAnzahl, MännerAnzahl
FROM Frau 
INNER JOIN 
(        
	SELECT Gruppe AS MannGruppe, COUNT(Mann.MNr) AS MännerAnzahl
	FROM Mann
	GROUP BY Gruppe
) AS qryMann ON Frau.Gruppe = qryMann.MGruppe -- die qry wird zu einem Tabelle
GROUP BY Gruppe;
```

> [!INFO]
> `AVG` führt zu keinem kartesischen Produkt.

## Kombination von Aggregation und Nicht Aggregation
Eine Subquery wird auch benötigt, wenn wir eine Wert mit seinem aggregierten Wert vergleichen.

**Ohne Gruppierung**

```sql
SELECT SchülerNr, Note, Durschnittsnote
FROM Arbeitsnoten, 
(
	SELECT AVG(Note) AS Durschnittsnote
	FROM Arbeitsnoten
) AS qryArbeitsnoten -- wie Tabellenname
WHERE Note < Durschnittsnote;
```

**Mit Gruppierung**
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

## WHERE Clause

**Vergleichen**
```sql
SELECT Datenfeld1, Datenfeld2
FROM tabelle
WHERE Datenfeld1 < (SELECT AVG(Datenfeld1) FROM tabelle);
```

**IN**
```sql
SELECT Datenfeld1, Datenfeld2
FROM tabelle
WHERE Datenfeld1 IN (SELECT datenfeld FROM andere_tabelle);
```

**NOT IN**

```sql
SELECT KdNr, KdName
FROM Kunde
WHERE KdNr NOT IN 
(
	SELECT KdNr
	FROM Kunde, KdAuftrage
	WHERE KdNr = Kunde AND YEAR(Auftragsdatum) = 2005
)
```

> [!warning]
> Primärschlüssel als einziges Feld im Subquery!

## UNION
Zeilen mit gleichem Inhalt werden standardmäßig zu einer Zeile komprimiert.
```sql
SELECT Gruppe, Vorname AS Name, Geburtsdatum AS Geburtsdatum -- Diese Spalten ergeben die Spaltenüberschriften
FROM frau
UNION
SELECT Gruppe, Vorname, Geburtsdatum
FROM mann;
```


## Correlated Subqueries

```sql
SELECT tabelle.feld, (SELECT andere_tabelle.feld FROM andere_tabelle JOIN tabelle ON tabelle.key = andere_tabelle.key)
FROM tabelle;
```

> [!danger]
> Correlated Subqueries verknüpfen mit dem äußeren Select. Sie werden für **jede Zeile** neu ausgeführt. Dadurch sind sie sehr ineffizient.

## Kontrolle

- Man benötigt **nicht** jedes Mal einen Subquery, wenn man einen berechneten Wert vergleichen möchte.
- **Nicht** jedes im Subquery verwendete Feld benötigt einen Alias, wenn es außerhalb verwendet werden soll.
- Man benötigt einen Subquery wenn man folgende Beziehungskonstellation hat: T **m-1** T **1-m** T.
- Der Alias **des Subquerys** wird nicht wie der Name eines Attributs verwendet.
- Um einen Subquery, der sich in der WHERE-Klausel befindet, zu verwenden, benötigt dieser **keinen** Alias-Namen.
- Für Queries mit aggregierten Werten benötigt man **nicht** immer einen Subquery.
- Man benötigt bei Vergleichen mit Berechnungen einen Subquery, **wenn** man den **aggregierten Wert** eines Datenfeldes mit seinen nicht-aggregierten Werten vergleichen möchte.
- Im Subquery  - egal wo verwendet - sollte man lieber großzügig auch mal **nicht** zu viele Felder selektieren.
- Um einen Subquery, der sich in der FROM-Klausel befindet, zu verwenden, benötigt dieser einen Alias-Namen.
- Man erhält **kein** kartesisches Produkt bei folgender Beziehungskonstellation:  T **1-mc** T **mc-1** T.
- Ein im Subquery berechnetes Feld benötigt einen Alias, um im äußeren Select verwendet werden zu können – es sei denn der Query steht in der WHERE-Klausel.
- In der Regel benötigt man ein Schlüsselfeld im Subquery, um diesen mit dem äußeren Select zu verbinden.
- Der Alias **eines aggregierten Wertes im Subquery** wird wie der Name eines Attributs verwendet.