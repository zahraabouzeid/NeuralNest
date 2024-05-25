## Datenbank Management System

Ein Datenbank Management System (DBMS) umfasst verschiedene Funktionen zur Verwaltung von Datenbanken, darunter:

- Datenspeicherung und Implementation des Modells
- Datenverwaltung und Manipulation
- Datenzugriff
- Gewährleistung der Datensicherheit

## Bestandteile

Ein DBMS besteht aus mehreren Bestandteilen, darunter:

- **Data Manipulation Language (DML)**: Zum Löschen und Anfügen von Datensätzen.
- **Data Query Language (DQL)**: Für die Suche gespeicherter Informationen.
- **Data Definition Language (DDL)**: Beschreibt die logische Struktur und Konzeption (Datenbankaufbau).
- **Data Control Language (DCL)**: Zur Verwaltung von Zugriffsrechten auf Tabellen.
- **Transaction Control Language (TCL)**: Für Sicherungsmaßnahmen bei der Datenübertragung.

## Struktur

**Datenbank erstellen**

```sql
CREATE DATABASE datenbank;
```

**Datenbanken anzeigen**

```sql
SHOW DATABASES;
```

**Datenbank löschen**

```sql
DROP DATABASE datenbank;
```

**Datenbank verwenden**

```sql
USE datenbank;
```

**Tabellen anzeigen**

```sql
SHOW TABLES;
```

**Spalten einer Tabelle anzeigen**

```sql
SHOW COLUMNS FROM tabelle;
```

**Tabelle erstellen**

```sql
CREATE TABLE tabelle (
    ID INT AUTO_INCREMENT,
    Wert CHAR(50) NOT NULL,
    FK INT NOT NULL,
    PRIMARY KEY (ID),
    FOREIGN KEY (FK)
        REFERENCES andere_tabelle(PK)
        ON DELETE CASCADE
        ON UPDATE CASCADE,
    UNIQUE INDEX (FK),
    INDEX(Wert)
);
```

**Tabelle löschen**

```sql
DROP TABLE tabelle;
```

**Spalte zur Tabelle hinzufügen**

```sql
ALTER TABLE tabelle
ADD spalte DATATYPE;
```

**Spalte aus Tabelle entfernen**

```sql
ALTER TABLE tabelle
DROP Wert;
```

**Spaltendatentyp ändern**

```sql
ALTER TABLE tabelle
MODIFY Wert DATATYPE;
```

**Primärschlüssel entfernen**

```sql
ALTER TABLE tabelle
DROP PRIMARY KEY;
```

**Primärschlüssel hinzufügen**

```sql
ALTER TABLE tabelle
ADD PRIMARY KEY (PK);
```

**Index erstellen**

```sql
CREATE [UNIQUE] INDEX i
ON tabelle(spalte);
```

**Index löschen**

```sql
DROP INDEX i
ON tabelle;
```

**Daten einfügen**

```sql
INSERT INTO tabelle (ID, Wert) 
VALUES (12, 'John'),
       (13, 'Alex');
```