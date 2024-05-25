![](Outer%20Join.png)
- `INNER JOIN` beinhaltetet nur Ergebnisse, die Datensätze in beiden Tabellen haben.
- `LEFT JOIN` beinhaltet die Schnittmenge und Datensätze der linken Tabelle.
- `RIGHT JOIN` beinhaltet die Schnittmenge und Datensätze der rechten Tabelle.
- `FULL JOIN` enthält die Vereinigungsmenge und ist bei referentieller Integrität irrelevant.
- `IFNULL()` ersetzt `NULL` mit dem ausgewählten Wert, ist aber irrelevant bei `COUNT`
- `COALESCE()` wird der Wert erste genommen, der nicht `NULL` ist. Gibt `COUNT(\*)` `NULL` zurück, ist 0 der erste Wert, der nicht `NULL` ist. Wenn alle Werte `NULL` sind, ist das Ergebnis `NULL`
## Kontrolle

- `FULL OUTER JOIN` sind irrelevant, wenn die Datenbank referentielle Integrität unterstützt.
- Wenn wir bei einer `LEFT JOIN` Abfrage mit zwei Tabellen die beiden Tabellen vertauschen und stattdessen einen RIGHT JOIN verwenden, erhalten wir dieselben Zeilen in der Ergebnismenge.
- Bei `COUNT` und `IFNULL` bzw. `COALESCE` benötigt man bei der Verwendung von mehr als einer Tabelle sehr oft einen `OUTER JOIN`, um ein vollständiges richtiges Ergebnis zu erhalten.
- Einen `OUTER JOIN` benötigt man, wenn es in der parent-Tabelle Datensätze gibt, die keine child-Datensätze in der verbundenen Tabelle hat und auch die  parent-Datensätze ohne child-Datensätze für die Vollständigkeit des Queries benötigt werden.