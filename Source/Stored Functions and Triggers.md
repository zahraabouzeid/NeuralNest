## Stored Functions
Eine **Stored Function** ist eine Menge von SQL Anweisungen, die auf dem Server gespeichert werden, zum Zweck der Wiederholbarkeit der gleichen Anweisungsfolgen und des wenigen Datenaustauschs zwischen dem Client und dem Server. Jedoch können **Stored Functions** den Datenbankserver belasten.

**Wie ändert man der Delimiter?**
```sql
DELIMITER //
```

**Wie schreibe ich eine Funktion?**
```sql
DELIMITER //
CREATE FUNCTION myfunc(param1 type) RETURNS type
BEGIN
	RETURN ausdruck
END;
//
DELIMITER ; -- delimiter wieder auf Semcolon zurücksetzen
```

**Eine Funktion aufrufen**
```sql
SELECT myfunc(param1)
```

## Trigger
Ein Trigger ist ein Datenbankobjekt, welches mit einer Tabelle verbunden ist und aktiviert wird, wenn für diese Tabelle ein bestimmtes Ereignis eintritt. Sie werden nicht im `SELECT` aufgerufen.

Die auslösende Ereignisse sind:
- `UPDATE`
- `INSERT`
- `DELETE`

**Syntax**
```sql
DELIMITER //
CREATE TRIGGER name zeitpunkt event
ON tbl_name
FOR EACH ROW
BEGIN
	IF bedingung THEN
	BEGIN
		trigger_statement;
	END IF;
END;
//
DELIMITER
```

**Beispiele**
```sql
CREATE TRIGGER insert_sum BEFORE INSERT
ON account
FOR EACH ROW
	SET @sum = @sum + NEW.amount;
```

```sql
CREATE TRIGGER update_preise AFTER UPDATE
ON Artikel
FOR EACH ROW
	INSERT INTO altePreise
	SET altePreise.ArtNr = OLD.ArtNr
		altePreise.Verkaufspreis = OLD.Verkaufspreis;
			
```