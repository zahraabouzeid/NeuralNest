## Datenbank Management System

Ein Datenbank Management System (DBMS) ist eine Systemsoftware zur Erstellung und Verwaltung von Datenbanken. Es umfasst verschiedene Funktionen zur Verwaltung von Datenbanken, darunter Datenspeicherung und Implementation des Modells, Datenverwaltung und Manipulation, Datenzugriff und Gewährleistung der Datensicherheit

## Bestandteile
Ein DBMS besteht aus mehreren Bestandteilen, darunter:

 **Data Definition Language (DDL)**
 Definition der Datenbankstruktur oder des Datenbankschemas, beschreibt die logische Struktur und Konzeption (Datenbankaufbau).

**Data Query Language (DQL)**
Daten aus dem Datenbank abrufen

**Data Manipulation Language (DML)**
Datenbankinstanz durch Einfügen, Ändern und Löschen Daten ändern

**Data Control Language (DCL)**
Verwaltung von Zugriffsrechten und Berechtigungen auf Tabellen

**Transaction Control Language (TCL)**
Sicherungsmaßnahmen bei der Datenübertragung

## Datentypen

| Typ           | Beschreibung                                                                 |
| ------------- | ---------------------------------------------------------------------------- |
| INT           | Ganze Zahlen (32 Bit)                                                        |
| DECIMAL(p, s) | Festkommatyp (p Dezimalstellen insgesamt, s Dezimalstellen hinter dem Komma) |
| FLOAT         | Gleitkommatyp (32 Bit)                                                       |
| DOUBLE        | GLeitkommatyp (64 Bit)                                                       |
| BOOLEAN       | False, True (0 oder 1)                                                       |
| DATE          | Datum JJJJ-MM-DD                                                             |
| DATETIME      | Datum und Uhrzeit                                                            |
| TIMESTAMP     | Datum und Uhrzeit in Milli-Sekunden                                          |
| CHAR(s)       | Zeichenfolge mit Länge s                                                     |
| VARCHAR(s)    | Zeichenfolge mit Maximal-Länge s, ggf. auch kürzer                           |
| Text          | Sehr große Texte                                                             |

## Datenbank verwalten

#### Datenbank erstellen

```sql
CREATE DATABASE [IF NOT EXISTS] Datenbankname;
```
#### Datenbanken auflisten

```sql
SHOW DATABASES;
```
#### Datenbank löschen

```sql
DROP DATABASE Datenbankname;
```
#### Datenbank auswählen

```sql
USE Datenbankname;
```

## Tabellen verwalten

#### Tabellen auflisten
```sql
SHOW TABLES;
```
#### Tabellenaufbau anzeigen
```sql
DESC Tabellenname;
```

#### Tabelle anlegen
```sql
CREATE TABLE Tabellenname (
	Attributname Datentyp [AUTO_INCREMENT] [NOT NULL] [DEFAULT WERT],
	Attributname Datentyp,
	Attributname Datentyp,
	PRIMARY KEY (Attributname),
	FOREIGN KEY (Attributname) REFERENCES ReferenzierteTabelle(Attributname) [ON UPDATE CASCADE] [ON DELETE CASCADE],
	UNIQUE INDEX (Attributname),
    INDEX(Attributname)
);
```

#### Tabelle löschen
```sql
DROP TABLE Tabellenname;
```


## Bestehende Tabellen ändern
#### Spalten auflisten

```sql
SHOW COLUMNS FROM Tabellenname;
```
#### Spalte hinzufügen

```sql
ALTER TABLE Tabellenname ADD Attributname Datentyp;
```
#### Spalte löschen

```sql
ALTER TABLE Tabellenname DROP Attributname;
```
#### Spalte ändern

```sql
ALTER TABLE Tabellenname MODIFY Attributname Datentyp;
```
#### Primärschlüssel entfernen

```sql
ALTER TABLE Tabellenname DROP PRIMARY KEY;
```

#### Primärschlüssel hinzufügen

```sql
ALTER TABLE Tabellenname ADD PRIMARY KEY (Attributename);
```

## Index
Indexe werden in Relationalen Datenbanken dazu benutzt, Daten schneller abfragen zu können.
Mit dem Keyword `UNIQUE` können doppelte Werte ausgeschlossen werden.
#### Index erstellen
```sql
CREATE [UNIQUE] INDEX Indexname ON Tabellenname(Attributname);
```

#### Index löschen
```sql
DROP INDEX Indexname ON Tabellenname;
```

## Daten bearbeiten

#### Daten einfügen
```sql
INSERT INRO Tabellenname (Attributname, Attributname, Attributname)
VALUES (Wert, Wert, Wert)
```
#### Daten löschen
```sql
DELETE FROM Tabellenname;
```

#### Daten aktualisieren

```sql
UPDATE Tabellenname
SET Datenfeld = NeuerWert,
	Datenfeld = NeuerWert;
```
