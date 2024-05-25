## Daten abfragen
*Warum geht Herbert oft laufen?*

**JOIN**

```sql
SELECT spalte 
FROM tabelle 
INNER JOIN andere_tabelle ON tabelle.spalte = andere_tabelle.spalte 
WHERE tabelle.spalte = 'Wert' 
ORDER BY tabelle.spalte DESC LIMIT 5;
```

**LIKE**

```sql
SELECT spalte 
FROM tabelle 
WHERE spalte LIKE 'M%';
```

**LIKE und Platzhaltern**

```sql
SELECT spalte 
FROM tabelle 
WHERE spalte LIKE 'M__R';
```

**REGEXP**

```sql
SELECT spalte 
FROM tabelle 
WHERE spalte REGEXP '^A';
```

## Operatoren

- `AND`
- `OR`
- `OR NOT`
- `BETWEEN x AND y`

## Aggregatfunktionen
- `MIN()` Gibt den kleinsten Wert zurück.
- `MAX()` Gibt den größten Wert zurück.
- `COUNT(*)` Zählt alle Datensätze.
- `COUNT(myCol)` Zählt alle Datensätze in einer bestimmten Spalte, ohne NULL-Werte.
- `SUM()` Summiert numerische Werte.
- `AVG()` Berechnet den Durchschnitt numerischer Werte.
