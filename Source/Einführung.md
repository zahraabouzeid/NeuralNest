## Ziele einer guten Datenverwaltung
- **Effizienz**
  - schnelle Erfassung
  - schneller Zugriff
  - gute Wartbarkeit 
- **Konsistenz**
  - Fehlerfreie
  - Widerspruchsfreie
  - aktuelle Daten
- **Sicherheit**
  - Datensicherheit (Schutz vor Verlust und Manipulation)
  - Datenschutz (Schutz personenbezogener Daten)

## Arten von Datenbanken
- **hierarchische Datenbanken**
übergeordnete Themen werden untergeordnete Themen mit ihren Daten zugeordnet. Top-Down. (XML oder JSON).
- **relationale Datenbanken**
bestehen aus Tabellen, die über Schlüssel miteinander verbunden werden.
- **NoSQL Datenbanken**
"not only" SQL Datenbanken ergänzen relationale Datenbanken um weitere Konzepte. MongoDB ist z.B. eine dokumentenbasierte Datenbank.

## Grundlegende Fachbegriffe
- **Relation:** Tabelle (eine Zeile, mehr als ein Ergebnis)
- **Datensatz (engl. recordset)**
	  - alle Informationen, die inhaltlich zusammen gehören, z.B. zu einer Person.
	  - entspricht einer Zeile einer Tabelle.
	  - Alle Daten, die logisch zusammengehören sind Datensätze.
	  - Ein Datensatz ist eine Zeile in der datenansicht der Tabelle
- **Datenfeld**
	  - Daten gleicher Art, z.B. Nachname. Entspricht je nach Kontext einer Spalte oder einer Zelle in einer Tabelle.
	  - Ein Datenfeld ist eine Spalte in der datenansicht der Tabelle.
	  - Ein Datenfeld ist ein Speicherplatz für daten der gleichen Art
- **Redundanzfreiheit**
	  - Keine überflüssigen, doppelten Informationen. 
	  - Die 3. Normalform sichert die Redundanzfreiheit der Datensätze.
- **Primärschlüssel**
	  - Ein Feld oder eine Kombination aus Datenfeldern, die eindeutig einen Datensatz identifizieren.
	  - Die Primärschlüssel sichert die Eindeutigkeit der Datensätze.
- **Fremdschlüssel**
	  - Ein Feld oder eine Kombination von Feldern, die auf einen Primärschlüssel einer anderen Tabelle verweist und so die Beziehung zwischen den Datensätzen der beiden Tabellen herstellt.
	  - Ein Fremdschlüssel stellt sicher, dass Datensätze einem zugehörigen Datensatz, der in einer anderen Tabelle steht, zugeordnet werden kann.
	  - Ein Fremdschlüssel ist ein Verbindungsfeld zu einer anderen Tabelle.
- **Sekundärschlüssel:** Ein zweiter Schlüssel, der neben dem Primärschlüssel eindeutig einen Datensatz identifiziert, aber nicht als Primärschlüssel genutzt wird.
- **Datentyp:** Ein Datentyp besagt, was für Daten ein Feld aufnehmen kann.
- **Datenbank Management System (DMS)**
- **Back End (Daten)**
- **Front End (Formulare und Berichte)**


