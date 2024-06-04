## Stored Functions
Eine **Stored Function** ist eine Menge von SQL Anweisungen, die auf dem Server gespeichert werden, zum Zweck der Wiederholbarkeit der gleichen Anweisungsfolgen und des wenigen Datenaustauschs zwischen dem Client und dem Server. Jedoch können **Stored Functions** den Datenbankserver belasten.

#### Delimiter setzen
```sql
DELIMITER //
```

#### Funktion erstellen
```sql
DELIMITER //
CREATE FUNCTION Funktion(Parameter Datentyp) RETURNS Datentyp
BEGIN
	RETURN Ausdruck
END;
//
DELIMITER ;
```

#### Funktion aufrufen
```sql
SELECT Funktion(Parameterwert)
```

## Trigger
Ein Trigger ist ein Datenbankobjekt, welches mit einer Tabelle verbunden ist und aktiviert wird, wenn für diese Tabelle ein bestimmtes Ereignis eintritt. Sie werden nicht im `SELECT` aufgerufen.

Die auslösende Ereignisse sind:
- `UPDATE`
- `INSERT`
- `DELETE`

#### Trigger erstellen
```sql
DELIMITER //
CREATE TRIGGER Triggername [BEFORE | AFTER] [INSERT | UPDATE | DELETE]
ON Tabellenname
FOR EACH ROW
BEGIN
	IF Bedingung THEN
	BEGIN
		Statement;
	END IF;
END;
//
DELIMITER
```

#### Insert Trigger
```sql
CREATE TRIGGER Inserttrigger BEFORE INSERT
ON Tabellenname
FOR EACH ROW
	SET @Datenfeld = @Datenfeld + NEW.Datenfeld;
```

#### Update Trigger
```sql
CREATE TRIGGER Updatetrigger AFTER UPDATE
ON Tabellenname
FOR EACH ROW
	INSERT INTO Sicherungstabelle
	SET Sicherungstabelle.Datenfeld = OLD.Datenfeld,
		Sicherungstabelle.Datenfeld = OLD.Datenfeld;
			
```