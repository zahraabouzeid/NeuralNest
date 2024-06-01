Einen `OUTER JOIN` benötigt man, wenn es in der Parent Tabelle Datensätze gibt, die keine Child Datensätze in der verbundenen Tabelle hat und auch die Parent Datensätze ohne Child Datensätze für die Vollständigkeit des Queries benötigt werden.

![500](Outer%20Join.png)

### Inner Join 
Ein Inner Join gibt die Schnittmenge der Tabellen zurück. Wenn zum Beispiel eine ID nur in einer Tabelle vorkommt wird sie nicht angezeigt.

### Left Join
Ein Left Join gibt alle Daten von der linken Tabelle zurück und zusätzlich die passende Schnittmenge der zweiten.

### Right Join 
Gibt alle Daten der rechten Tabelle zurück und zusätzlich die Schnittmenge der linken.

### Full Outer Join / Full Join
Gibt alle Daten aus beiden Tabellen zurück. Sie sind irrelevant, wenn die Datenbank referentielle Integrität unterstützt.


