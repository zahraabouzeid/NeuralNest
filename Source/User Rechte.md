**Alle Benutzer anzeigen**
```sql
SELECT *
FROM mysql.user;
```
**Benutzer erstellen**
```sql
CREATE USER IF NOT EXISTS 'benutzer'@'localhost'
IDENTIFIED BY 'passwort';
```

**Passwort für sich selbst setzen**
```sql
SET PASSWORD = PASSWORD('passwort')
```

**Passwort für sich selbst setzen**
```sql
SET PASSWORD 
FOR 'benutzer'@'localhost'v= PASSWORD('passwort');
```

**Rechte vergeben**
```sql
GRANT ALL PRIVILEGES ON meineDB.* TO 'benutzer'@'localhost';
GRANT INSERT, DELETE ON meineDB.Mitarbeiter TO 'benutzer'@'localhost';
FLUSH PRIVILEGES;
```

**Rechte entziehen**
```sql
REVOKE ALL PRIVILEGES ON meineDB . * FROM 'benutzer'@'localhost';
REVOKE ALL PRIVILEGES ON meineDB . * FROM 'benutzer'@'localhost';
REVOKE INSERT ON meineDB.Mitarbeiter FROM 'benutzer'@'localhost';
```

- `ALL PRIVILEGES:` Ein Wildcard für alle Rechte auf das gewählte Datenbankobjekt, mit einem `*.*` auf alle Datenbanken.
- `CREATE`: Erlaubt einem Benutzer, neue Datenbanken und Tabellen zu erstellen
- `DROP`: Erlaubt einem Benutzer, Datenbanken und Tabellen zu löschen
- `DELETE`: Erlaubt einem Benutzer, einzelne Zeilen in einer Tabelle zu löschen
- `INSERT`: Erlaubt einem Benutzer, neue Zeilen in eine Tabelle zu schreiben
- `SELECT`: Leseberechtigungen auf eine Datenbank oder Tabelle
- `UPDATE`: Erlaubnis, eine Zeile zu aktualisieren
- `GRANT OPTION`: Erlaubt einem Benutzer, die Rechte anderer Benutzer zu setzen oder zu widerrufen

**Roles**
```sql
CREATE ROLE 'app_developer', 'app_read', 'app_write';
GRANT ALL ON app_db.* TO 'app_developer';
GRANT SELECT ON app_db.* TO 'app_read';
GRANT INSERT, UPDATE, DELETE ON app_db.* TO 'app_write'; 
GRANT 'app_developer' TO 'dev1'@'localhost';
GRANT 'app_read' TO 'read_user1'@'localhost', 'read_user2'@'localhost';
GRANT 'app_read', 'app_write' TO 'rw_user1'@'localhost';
DROP ROLE 'app_read'
```