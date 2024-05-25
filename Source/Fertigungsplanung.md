Die Ablauforganisation stellt die Ordnung des Arbeitsablaufs dar. Im Gegensatz zur Aufbauorganisation ist die Ablauforganisation dadurch gekennzeichnet, dass sie den Faktor **Zeit** mit in die Planung einbeziehen.

**Was versteht man unter Projekt?**
Unter Projekt wird eine komplexe Aufgabe verstanden, deren Einzelaufgaben derart abgestimmt werden müssen, dass es in einer bestimmten Zeit zu Ende geführt werden kann.
## Ablaufplanung
Die Aufgabe der Ablaufplanung ist es, die Fertigung zu steuern und zu überwachen. Hierzu bedient sie sich im Wesentlichen zweier Hilfsmittel: dem Arbeitsplan und dem Zeitplan.
#### Arbeitsplan
Er wird aus der Konstruktionszeichnung und den Stücklisten entwickelt. Im Arbeitsplan wird genau festgehalten, welche Arbeiten in welcher Reihenfolge von welcher Arbeitsstelle in welcher Zeit und mit welchen Hilfsmitteln ausgeführt werden müssen.
#### Zeitplan
Die Zeit und Terminplanung basiert auf den im Arbeitsplan angegebenen Daten. Sie ermittelt, wie lange die eigentliche Produktion eines Erzeugnisses dauert. Diese Zeit zwischen Start der Produktion und deren Ende heißt **Durchlaufzeit**. 

Die **Durchlaufzeit** setzt sich wiederum aus verschiedenen Teilzeiten zusammen:
- Rüstzeit (Einstellen und Umbau einer Maschine) 
- Bearbeitungszeit (Zeit, in der an dem Teil gearbeitet wird) 
- Transportzeit (Transport eines Teiles von einer Werkstatt zur anderen) 
- Liegezeit (z. B. verursacht durch belegte Maschinen) 
- Kontrollzeit (durch Qualitätskontrollen) 

Wenn die Durchlaufzeit ermittelt wurde, kann auch ein **Termin** genannt werden, zu dem die einzelnen Aufträge fertig gestellt werden können. Damit jedermann im Betrieb diese Terminplanung nachvollziehen kann, bedient man sich zweier anschaulicher Darstellungsmethoden, des **Balkendiagramms** und der **Netzplantechnik**.

## Netzplan
ist eine wichtige Methode der zeitorientierten Ablauforganisation.

#### Schritte
1. Strukturanalyse (systematische Erfassung und grafische Darstellung des Projektverlaufs)
2. Zeitanalyse (Ermittlung des zeitlichen Ablaufs des Projekts)

Ergebnis der Strukturanalyse ist ebenso wie beim Balkendiagramm eine Vorgangsliste, allerdings erfolgt hier noch keine Angabe der Dauer der einzelnen Vorgänge. Die Vorgangsliste wird grafisch dargestellt. Vorgänge werden durch sogenannte **Knoten** visualisiert. 

#### Regeln:
- Schleifen sind nicht erlaubt.
- Die Abhängigkeit zwischen zwei unmittelbar aufeinanderfolgenden Vorgängen wird durch einen Pfeil dargestellt.
- Ein Vorgang kann mehrere Vorgänger und Nachfolger haben.
- Es muss vom Startknoten bis zum Zielknoten ein ununterbrochener Ablauf geben.

#### Knoten im Netzplan zum Zweck der Zeitanalyse:
![|400](Knoten.png)
- Dauer der Vorgänge (D)
- Frühester Anfangszeitpunkt (FAZ)
- Frühester Endzeitpunkt (FEZ)
- Spätester Anfangszeitpunkt (SAZ)
- Spätester Endzeitpunkt (SEZ)
- Gesamtpuffer (GP)
- Freier Puffer (FP)

**Informationen die ich damit darstellen kann**
-  Logische u. zeitliche Abhängigkeiten der Vorgänge
- Frühster und spätester Endzeitpunkt eines Vorgangs
- Zeitreserven
-  Zeitlicher Engpass (kritischer Pfad)
#### Kalkulationen
**1. Vorwärtsrechnung**
- Startknoten haben immer ein `FAZ = 0`
- `FEZ = FAZ + Dauer`

**2. Rückwärtsrechnung**
- FEZ des Zielknotens ist der SEZ des Projekts
- `SAZ = SEZ - Dauer`
- Der SAZ eines Vorgangs ist zugleich der SEZ aller unmittelbar vorausgehenden Vorgänge.
- Haben mehrere Vorgänge einen gemeinsamen Vorgang, so richtet sich dessen SEZ nach dem frühsten SAZ aller Nachfolger.

	![|500](Netzplan.png)

**3. Gesamtpuffer**
Es gibt Auskunft darüber, wie lange sich ein Vorgang maximal verzögern darf, ohne dass die Gesamtdauer des Projekts sich verlängert.
`GP = SAZ - FAZ`

**4. freien Pufferzeiten**
- ist die Zeitspanne, um die ein Vorgang ausgedehnt werden kann, ohne den nachfolgenden Vorgang aus seiner frühesten Lage zu verdrängen.
- Wird der freie Puffer überschritten, beginnt der nachfolgende Vorgang später.
	`FP A = FAZ B - FAZ A`

**5. Kritischer Pfad**
- Die termingerechte Bearbeitung der Vorgänge, die über keine Zeitreserven verfügen ist entscheidend für die Einhaltung der Projektdauer. 
- Diese Vorgänge nennt man kritische Vorgänge. 
- Die Verbindung aller kritischen Vorgänge vom Startknoten bis zum Endknoten nennt man kritischen Weg.
- **Kritischer Vorgang:** `FP = 0 und GP = 0`

> [!tip]
> - Bei der Vorwärtskalkulation nehmen wir den größten FEZ
> - Bei der Ruckwärtskalkulation nehmen wir den kleinsten SAZ
## Balkendiagramm
**Synonyme:** Gantt-Diagramme
- Es dient der Planung und Darstellung von **zeitorientierten Abläufen**.
- Die Arbeitsvorgänge werden durch Balken dargestellt.
- Die Länge der Balken hängt von der Dauer der Vorgänge.
- Wird im Projektmanagement, Maschinenbelegungsplanung und Urlaubsplanung angewendet.

**Informationen die ich damit darstellen kann**
- Alle Vorgänge eines Projekts
- Start und Endzeitpunkt je Vorgang
- Dauer eines Vorgangs
- Überschneidung von Vorgängen und Dauer der Überschneidungen
- Start- und Enddatum eines Projekts
#### Nachteile
Das Balkendiagramm zeigt die einzelnen Vorgänge nur in ihrem zeitlichen Zusammenhang. Sollen zusätzlich sachlogische Abhängigkeiten veranschaulicht werden, muss auf eine andere Art der Darstellung ausgewichen werden, den **Netzplan**.


