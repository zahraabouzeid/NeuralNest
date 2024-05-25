## Grundschutz
- eine "Vorgabe" bzw. Begriff des BSI
- Strukturierung aller Bestandteile der IT-Sicherheit

## Schutzziele
- Kategorien für Schutzintensionen
- Freie "Normen"
	- Keine Verbindlichkeit
	- Keine Ableitung
	- Jedes Unternehmen muss eigene definieren oder die vorhandenen gewichten.
- Es gibt noch keine einheitliche Systematik
- Grundwerte: Integrität, Vertraulichkeit, Verfügbarkeit

## Gefährdungen
- Sammlung (Liste aller Gefahren)
- Gefahr heißt nur es besteht die Möglichkeit eines Schadens
- Analyse von Risiken

## Schadenszenarien
- Gewichtung (Bewertung aus Eintrittswahrscheinlichkeit) und Kategorisierung der Risiken
- Abschätzung der Folgen
- Auch als Risikomanagement bezeichnet

## Information Security Management System

Die Schicht ISMS (Information Security Management System): alle Aktivitäten im Sicherheitsprozess Prozess-Bausteine
#### Prozess-Bausteine
- Der Baustein ORP: Organisatorischen und personellen Sicherheitsaspekte 
- Der Baustein CON: Konzepten und Vorgehensweisen.
  - Typische Bausteine der Schicht CON:
    - Auswahl und Einsatz von Standardsoftware 
    - Kryptokonzept
    - Datenschutz.
- Der Baustein OPS (Operative Security): Sicherheitsaspekte betrieblicher Art (laufender Betrieb), des operativen IT-Betriebs, sowohl bei einem Betrieb als im Haus

#### System-Bausteine
- APP (Application and Services) beschäftigt sich mit der Absicherung von Anwendungen und Diensten, unter anderem in den Bereichen:
	- Kommunikation
	- Verzeichnisdienste
	- netzbasierte Dienste
	- Business- und Client-Anwendungen.
  z.B. Allgemeiner E-Mail-Client und -Server, Office-Produkte, Webserver und Relationale Datenbanksysteme.
	
- SYS (IT-Systems) betrifft die einzelnen IT-Systeme des Informationsverbunds, die ggf. in Gruppen zusammengefasst wurden. Sicherheitsaspekte von Servern, Desktop-Systemen, Mobile Devices und sonstigen IT-Systemen wie Druckern und TK-Anlagen behandelt.
  Beispielsweise Bausteine zu konkreten Betriebssystemen, Allgemeine Smartphones und Tablets sowie Drucker, Kopierer und Multifunktionsgeräte.
  
- IND (Industrial) befasst sich mit Sicherheitsaspekten industrieller IT. 
  In diese Schicht fallen beispielsweise die Bausteine Prozessleit- und Automatisierungstechnik, Allgemeine ICS-Komponente und Speicherprogrammierbare Steuerung (SPS).
  
- NET (Networks) betrachtet die Vernetzungsaspekte, die sich nicht primär auf bestimmte IT-Systeme, sondern auf die Netzverbindungen und die Kommunikation beziehen. 
  z.B. Netz Management, Firewall und WLAN-Betrieb.
  
- INF (Infrastructure) befasst sich mit den baulich-technischen Gegebenheiten, hier werden Aspekte der infrastrukturellen Sicherheit zusammengeführt.

Die Schicht DER (detection and reaction) Detektion und Reaktion (Kontrolle Evaluation Behandlung von Sicherheitsvorfällen, Vorsorge, aber auch Kontrolle der Reaktionen)

#### Vorgehensweise  
R1 R2 R3 sind Gewichtungen der Instrumente und Methoden: z.B. hat R1 SoftwareTest und Freigaben Vorrang vor R2 Protokollierung und R3 Fernwartung

## Informationssicherheit
- Schutz aller Informationen 
- Teilweise als Oberbegriff für Datensicherheit und Datenschutz
- Grundziele:
	- Integrität
	- Verfügbarkeit
	- Vertraulichkeit

#### Säulen der Schutzziele
- Datensicherheit
	- Schutz aller Daten im Unternehmen
	- Egal welche Daten und egal wie diese erfasst und verwaltet werden
	- Grundschutzzielschwerpunkt: Integrität
- Datenschutz
	- Schutz der Personenbezogenen Daten
	- Rechte und Pflichten bei der Speicherung und Verwendung
	- Grundschutzzielschwerpunkt: Vertraulichkeit
- IT-Sicherheit
  - Absicherung der IT-Technik (Hardware und Software)
  - Grundschutzzielpunkt: Integrität und Verfügbarkeit
  
  Die Ziele müssen individuell nach Risiko gewichtet werden
  - **Verfügbarkeit**: Ständige Erreichbarkeit der IT-Systeme
  - **Vertraulichkeit**: Kein Zugriff von Unberechtigten
  - **Integrität:** Unversehrtheit aller Daten nach der Erfassung

#### Gefährdungen
- Das BSI listet fast 50 elementare Gefährdungen auf. 
- Jedes Unternehmen muss eventuell weitere identifizieren
  - Beispiele:
    - Feuer 
    - Social Engineering
    - Wasser
    - Manipulation von Informationen
    - Sabotage

## Kreuzreferenztabellen
Zu jedem Baustein wird im Anhang eine Kreuztabelle dargestellt, die Gefährdungen des Bausteins und Anforderungen in einen Zusammenhang stellt. Zu den Gefährdungen werden jeweils auch die Grundwerte angegeben.

## Kompetenzcheck

#### Übung 1: Zuordnung von Zielobjekten zu Grundschutzbausteinen

| Zielobjekt                                       | Zuordnung zu Grundschutzbausteinen       |
|--------------------------------------------------|-------------------------------------------|
| Ausspähen von Daten bei Softwaretests           | OPS (operative security)                 |
| Browser                                          | APPS (Anwendungen und Dienste)           |
| IoT-Sensor beim kooperativen Roboter            | IND (industrielle IT)                    |
| Stromschwankungen im Stromnetz                  | INF (infrastrukturelle Sicherheit)       |
| Notfallrichtlinie am Arbeitsplatz               | DER (detection and reaction)             |
| Sicherheitsbeauftragter des Arbeitsplatzbereichs| ISMS (information security management system) |
| WLAN-Zugang                                     | NET (Netzverbindungen und Kommunikation) |
| Vergabe eines Passwortes eines Arbeitsplatzes an mehrere Personen | ORP (organisatorische und personelle Sicherheitsaspekte) |
| Datenverlust bei der vorgeschriebenen Datensicherung am Arbeitsplatz | CON (Konzepte und Vorgehensweisen) |
| Arbeitsplatzrechner                             | SYS (IT-Systeme des Informationsverbunds) |
#### Übung 2: Aussagen über IT-Grundschutz und BSI

| Aussage                                                                                                | Korrekt |
| ------------------------------------------------------------------------------------------------------ | ------- |
| IT-Grundschutz ist ein Fachbegriff des BSI.                                                            | Wahr    |
| Das IT-Grundschutzkompendium ist Teil des BDSG.                                                        | Falsch  |
| Die Systematik des BSI-Grundschutzes enthält acht Basisbausteine.                                      | Falsch  |
| Die Systematik des BSI-Grundschutzes enthält sieben Systembausteine.                                   | Falsch  |
| Die Systematik des BSI-Grundschutzes enthält fünf Systembausteine (APP NET INF SYS IND).               | Wahr    |
| Die Systematik des BSI-Grundschutzes umfasst zehn Schichten.                                           | Wahr    |
| Die Schutzziele des BSI entsprechen fast den Grundwerten des BSI.                                      | Wahr    |
| Authentizität ist nach BSI ein Teilziel des Integritätsziels.                                          | Wahr    |

#### Übung 3
| Frage                          | Antwort                                             |
| ------------------------------ | --------------------------------------------------- |
| **Drei Grundziele**            | Verfügbarkeit, Vertraulichkeit, Integrität          |
| **Oberste Bundesbehörde**      | Bundesamt für Sicherheit in der Informationstechnik |
| **Systematische Untersuchung** | IT-Forensik                                         |
| **Tabelle mit Gefährdungen**   | Kreuztabelle                                        |
| **Deming Zyklus**              | PDCA-Zyklus                                         |
| **Deutsches Wort für Threats** | Bedrohung                                           |
