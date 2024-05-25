## Einführung

Ziel der Normalisierung ist es, Datenredundanzen in der Datenbank zu vermeiden. **Redundanzfreiheit** bedeutet, dass kein Teil eines Datenbestandes weggelassen werden kann, ohne dass dies zu Informationsverlusten führt. Dadurch soll einerseits Speicherplatzgespart werden. Andererseits sollen keine Probleme beim Ändern, Speichern und Löschen von Daten sogenannte **Anomalien** auftreten.

## Nicht normalisierte Relation

|Schüler-Nr|Schüler-nachname|Klasse|Klassen-lehrer|Fach|Note|Fach-bereich|
|---|---|---|---|---|---|---|
|1|Schmidt|110|Herbst|Englisch, BWL|3,2|Sprachen, Wirtschaft|
|2|Müller|110|-|Englisch, Deutsch|4,1|Sprachen|
|3|Schneider|524|-|Feldbusch|2|Englisch|

## Erste Normalform
#### Merkmale
- alle Attribute atomar sind, d.h. in jedem Datenfeld steht nur ein Wert: also nicht Name, sondern Vor-und Nachname.
- jedes Nichtschlüsselattribut von einem Primärschlüssel abhängig ist, d.h. durch den Primärschlüssel eindeutig identifiziert wird.

#### Auswahl der richtigen Attribute:
- Jeder Datensatz (auch genannt Tupel) ist gleich lang.
- Es gibt keine langfristig leeren Felder.
- Kein Attribut (Datenfeld) kommt mehrfach vor, also nicht Telefon1, Telefon2, Telefon3, ...
- Keine Redundanzen in den Attributen, also nicht Geburtsdatum und Alter.

#### Wie komme ich zur 1. Normal Form?
###### 1. **Schritt:**
- In einem Datenfeld darf nur ein Wert stehen.
- Am Kreuzungspunkt von Zeile und Spalte darf nur ein Wert stehen.

| **Schüler-Nr** | **Schüler-nachname** | **Klasse** | **Klassen-lehrer** | **Fach** | **Note** | **Fach-bereich** |
| -------------- | -------------------- | ---------- | ------------------ | -------- | -------- | ---------------- |
| 1              | Schmidt              | 110        | Herbst             | Englisch | 3        | Sprachen         |
|                |                      |            |                    | BWL      | 2        | Wirtschaft       |
| 2              | Müller               | 110        |                    | Englisch | 4        |                  |
|                |                      |            |                    | Deutsch  | 1        | Sprachen         |
| 3              | Schneider            | 524        | Feldbusch          | Englisch | 2        |                  |

###### 2. Schritt:
Jeder Datensatz muss gleich lang sein.

| **Schüler-Nr** | **Schüler-nachname** | **Klasse** | **Klassen-lehrer** | **Fach** | **Note** | **Fach-bereich** |
| -------------- | -------------------- | ---------- | ------------------ | -------- | -------- | ---------------- |
| 1              | Schmidt              | 110        | Herbst             | Englisch | 3        | Sprachen         |
| 1              | Schmidt              | 110        | Herbst             | BWL      | 2        | Wirtschaft       |
| 2              | Müller               | 110        | Herbst             | Englisch | 4        | Sprachen         |
| 2              | Müller               | 110        | Herbst             | Deutsch  | 1        | Sprachen         |
| 3              | Schneider            | 524        | Feldbusch          | Englisch | 2        | Sprachen         |
###### 3. Schritt: 
Alle Nichtschlüsselattribute müssen durch einen Primärschlüssel eindeutig identifiziert werden. Das heißt für ein und denselben Primärschlüsselwert darf es nicht möglich sein in ein Nichtschlüsselfeld zwei verschiedene Attributswerte einzutragen.

| ==**Schüler-Nr**== | **Schüler-nachname** | **Klasse** | **Klassen-lehrer** | ==**Fach**== | **Note** | **Fach-bereich** |
| ------------------ | -------------------- | ---------- | ------------------ | ------------ | -------- | ---------------- |
| 1                  | Schmidt              | 110        | Herbst             | Englisch     | 3        | Sprachen         |
| 1                  | Schmidt              | 110        | Herbst             | BWL          | 2        | Wirtschaft       |
| 2                  | Müller               | 110        | Herbst             | Englisch     | 4        | Sprachen         |
| 2                  | Müller               | 110        | Herbst             | Deutsch      | 1        | Sprachen         |
| 3                  | Schneider            | 524        | Feldbusch          | Englisch     | 2        | Sprachen         |

#### Anomalien in der 1. Normalform
- **INSERT ANOMALY**: In der Relation 1NF_SCHULE kann kein Schüler eingefügt werden, ohne, dass mindestens ein Fach bereits feststeht, da sonst der Primärschlüssel unvollständig ist.
- **DELETE ANOMALY:** Wird das Fach Englisch für den Schüler Schneider gelöscht, so gehen auch alle Schülerdaten verloren.
- **UPDATE ANOMALY:** Soll die Klassenzugehörigkeit des Schülers Schmidt geändert werden, muss dies hier in zwei Zeilen geschehen.

## Zweite Normalform
#### Merkmale
- Eine Relation befindet sich in der 2. Normalform wenn die erste Normalform erfüllt ist
- alle Nichtschlüsselattribute voll funktional vom gesamten Primärschlüssel und nicht schon von einem Teilschlüssel abhängig, sind.
- Notwendige Voraussetzung: Die 1. Normalform hat einen zusammengesetzten Primärschlüssel. Ansonsten entspricht die 1. Normalform bereits der 2. Normalform.
- Aus Attributen, die bereits von einem Teilschlüssel abhängen, wird eine neue Relation gebildet.
- Alle Nichtschlüsselattribute sollen voll funktional vom gesamten Primärschlüsselabhängig sein.

#### Wichtig
- Der zusammengesetzte Schlüssel der ersten Normalform muss in einer Relation der 2. Normalform auftauchen.
- Das gilt auch, wenn diese Relation nur aus diesen Schlüsselfeldern besteht.
- Ohne diese Relation könnten die Beziehungen zwischen den übrigen Relationen nicht hergestellt werden!


| ==**Schüler-Nr**== | **Schüler-nachname** | **Klasse** | **Klassen-lehrer** |
| ------------------ | -------------------- | ---------- | ------------------ |
| 1                  | Schmidt              | 110        | Herbst             |
| 2                  | Müller               | 110        | Herbst             |
| 3                  | Schneider            | 524        | Feldbusch          |

| ==**Schüler-Nr**== | **==Fach==** | **Note** |
| ------------------ | ------------ | -------- |
| 1                  | Englisch     | 3        |
| 1                  | BWL          | 2        |
| 2                  | Englisch     | 3        |
| 2                  | BWL          | 1        |
| 3                  | Englisch     | 2        |

| **==Fach==** | **Fachbereich** |
| ------------ | --------------- |
| Englisch     | Sprachen        |
| BWL          | Wirtschaft      |
| Deutsch      | Sprachen        |

## Dritte Normalform

- Eine Relation befindet sich in der 3. Normalform wenn sie die 2. Normalform erfüllt und keine transitiven Abhängigkeiten bestehen.
- Alle Datenfelder, die von einem anderen Nichtschlüsselattribut abhängen, werden als neue Relation angelegt.
- Der Klassenlehrer ist abhängig von der Klasse, die widerrum von der Schülernummer abhängig ist. Der Klassenlehrer ist somit durch ein anderes Nichtschlüsselattribut eindeutig bestimmt. So eine Abhängigkeit nennt man transitive Abhängigkeit.
- Relationen in der 3. Normalform in Kurzschreibweise:
	- 3NF_SCHÜLER (Schüler-Nr, Schülernachname, Klasse)
	- 3NF_KLASSE (Klasse, Klassenlehrer)
	- 3NF_NOTEN (Schüler-Nr, Fach, Note)
	- 3NF_FÄCHER (Fach, Fachbereich)

| ==**Schüler-Nr**== | **Schüler-nachname** | **Klasse** | **Klassen-lehrer** |
| ------------------ | -------------------- | ---------- | ------------------ |
| 1                  | Schmidt              | 110        | Herbst             |
| 2                  | Müller               | 110        | Herbst             |
| 3                  | Schneider            | 524        | Feldbusch          |

| ==**Schüler-Nr**== | **Schüler-nachname** | **Klasse** |
| ------------------ | -------------------- | ---------- |
| 1                  | Schmidt              | 110        |
| 2                  | Müller               | 110        |
| 3                  | Schneider            | 524        |

| **==Klasse==** | **Klassen-lehrer** |
| -------------- | ------------------ |
| 110            | Herbst             |
| 524            | Feldbusch          |

## Fazit

In der 1. Normalform die Attribute sind atomar.
In der 3. Normalform werden transitive Abhängigkeiten gelöst.

#### Die erste Normalform beinhaltet:
- dass alle Attribute Atomar sind
- dass es keine Dopplung in den Attributen gibt, wie z.B. Alter und Geburtsdatum
- dass alle Datensätze gleich lang sind
- dass nur ein Wert am Kreuzungspunkt von Zeile und Spalte steht
- dass es einen Primärschlüssel gibt, welcher alle anderen Attribute eindeutig identifiziert

#### Die zweite Normalform beinhaltet:
- jedes Nicht-Schlüssel Attribut voll funktional vom gesamten Primärschlüssel abhängig ist
- die erste Normalform erfüllt ist
- kein Nicht-Schlüssel Attribut nur von einem Teil des Primärschlüssels eindeutig identifiziert werden kann
- Alle Attribute atomar sind

#### Die dritte Normalform beinhaltet:
- die erste Normalform erfüllt ist
- die zweite Normalform erfüllt ist
- es keine transitiven Abhängigkeiten mehr gibt
- es keine Redundanzen mehr gibt
- keine Anomalien mehr auftreten können

#### Der Ziel der Normalisierung ist:
- Redundanzen zu eliminieren
- Speicherplatzverschwendung zu vermeiden

#### Anomalien:
- Änderungsanomalie (update anomaly): Nach einem Umzug müssen die neuen Adressdaten mehrfach eingepflegt werden
- Einfügeanomalie (insert anomaly): Beim Anlegen eines neuen Kunden muss bereits ein Vertrag eingegeben werden
- Löschanomalie (delete anomaly): Bei einer Löschung gehen ungewollt Daten verloren, da der ganze Datensatz gelöscht werden muss
- Eine Anomalie kann in der ersten Normalform vorkommen
- Anomalien können nur auftreten, wenn es Redundanzen in den Daten gibt
- Eine Anomalie kann in einer unnormalisierten Datenbank vorkommen
- Eine Anomalie kann in der zweiten Normalform vorkommen
