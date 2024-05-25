## Beschreibung des ERDs

| **Kardinalität** | **Anzahl der Tupel der Relation**  |
| ---------------- | ---------------------------------- |
| 1                | genau ein Datensatz                |
| c                | höchstens ein (0 oder 1) Datensatz |
| m                | mindestens ein Datensatz $>=1$     |
| mc               | beliebig viele Datensätze $<=0$    |

Im Entity-Relationship-Modell wird die Realität durch folgende Bestandteile beschrieben:
- Entitäten oder Objekte (Tabellen)
- Attribute (Datenfelder)
- Beziehungstypen (Verbindungssatz)
- Kardinalitäten (Beziehungsart) 

**Einbau**
- Eine Kardinalität legt fest, wie viele Datensätze einer Relation zu jedem Datensatz einer anderen Relation gehören können.
- Fremdschlüssel sind im ERD nicht enthalten, sondern sind implizit durch die Beziehung vorhanden. Sie stehen immer in der Tabelle, wo die 1 nicht steht.
- 1:1 Beziehungen machen nie Sinn, und Beziehungen bei denen auf einer Seite eine 1 steht nennt man hierarchische Beziehungen.
- Die Kardinalität m wird durch die referentielle Integrität der Beziehung nicht erzwungen. Es wird keine 1:m, sondern eine 1:mc Beziehung erstellt.
- Die 3. Normalform kennt keine 1:c Beziehungen.
- mc:mc Beziehungen sind nicht übersichtlich und man kann nicht alles eintragen. Um nicht hierarchische Beziehungen implementierbar zu machen, transformiert man sie in 2 hierarchische Beziehungen.

## Schritte bei der Erstellung eines ERD

1. Offensichtliche Entitäten (Tabellen) identifizieren.
2. Attribute zuordnen - soweit möglich.
3. Einfache Primärschlüssel identifizieren - soweit möglich.
4. Beziehungen erstellen.
5. Transformieren wenn notwendig.
6. Restliche Attribute zuordnen.
7. Restliche Primärschlüssel identifizieren.
8. Transformieren Sie jede nicht-hierarchische Beziehung!

## Wann ist eine ID als Primärschlüssel sinnvoll?

Eine ID als Primärschlüssel ist sinnvoll, wenn es kein eindeutiges Datenfeld gibt und wenn der „natürliche“ Primärschlüssel mehr Speicherplatz als eine ID verbraucht und in einer child-Tabelle referenziert wird (FK).