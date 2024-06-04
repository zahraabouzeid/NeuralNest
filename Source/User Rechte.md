## Benutzereinstellungen
#### Benutzer auflisten
```sql
SELECT * FROM mysql.user;
```
#### Benutzer erstellen
```sql
CREATE USER IF NOT EXISTS 'Benutzer'@'localhost'
IDENTIFIED BY 'Passwort';
```

#### Benutzerpasswort setzen
```sql
SET PASSWORD = PASSWORD('Passwort')
```

#### Passwort für einen bestimmten Benutzer setzen
```sql
SET PASSWORD 
FOR 'Benutzer'@'localhost' = PASSWORD('Passwort');
```

## Benutzerrechte

| Befehl         | Beschreibung                                                                                           |
| -------------- | ------------------------------------------------------------------------------------------------------ |
| ALL PRIVILEGES | Ein Wildcard für alle Rechte auf das gewählte Datenbankobjekt und mit einem `*.*` auf alle Datenbanken |
| CREATE         | Erlaubt einem Benutzer, neue Datenbanken und Tabellen zu erstellen                                     |
| DROP           | Erlaubt einem Benutzer, Datenbanken und Tabellen zu löschen                                            |
| DELETE         | Erlaubt einem Benutzer, einzelne Zeilen in einer Tabelle zu löschen                                    |
| INSERT         | Erlaubt einem Benutzer, neue Zeilen in eine Tabelle zu schreiben                                       |
| SELECT         | Leseberechtigungen auf eine Datenbank oder Tabelle                                                     |
| UPDATE         | Erlaubnis, eine Zeile zu aktualisieren                                                                 |
| GRANT OPTION   | Erlaubt einem Benutzer, die Rechte anderer Benutzer zu setzen oder zu widerrufen                       |


#### Rechte vergeben
```sql
GRANT ALL PRIVILEGES ON Datenbankname.* TO 'Benutzer'@'localhost';
GRANT INSERT, DELETE ON Datenbankname.Tabellenname TO 'Benutzer'@'localhost';
FLUSH PRIVILEGES;
```

#### Rechte entziehen
```sql
REVOKE ALL PRIVILEGES ON Datenbankname.* FROM 'Benutzer'@'localhost';
REVOKE INSERT ON Datenbankname.Tabellenname FROM 'Benutzer'@'localhost';
FLUSG PRIVILIGES;
```


## Benutzerrollen

#### Rolle erstellen
```sql
CREATE ROLE 'Role', 'Role', 'Role';
GRANT INSERT ON Datenbankname.* TO 'Role';
```
#### Role löschen
```sql
DROP ROLE 'Role'
```
#### Rolle vergeben
```sql
GRANT 'Role' TO 'Benutzer'@'localhost';
```
