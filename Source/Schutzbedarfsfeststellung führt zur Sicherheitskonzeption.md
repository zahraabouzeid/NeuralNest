
## Vorgehensweise bei der Schutzbedarfsfeststellung
- Dokumentation des IT- Verfahrens: Ein Unternehmen muss vorher festlegen wie es vorgehen will und wird. (Also von der Gefährdung bis zum Konzept)
- Sicherheitsleitlinie: Klären was will man tun, wie soll gearbeitet werden, was soll erfasst werden was soll dokumentiert werden, wer ist zuständig, wer ist betroffen
- Sicherheitskonzept: eher IST Aufnahme des IT-Systems also welche Bereiche gibt es (BSI sind keine Wissenschaftler sondern eher "TÜV Behörde") Welche Geschäftsprozesse gibt es? Wo könnten Sicherheitsbelange eine Rollen spielen? Welche IT-Systeme gibt es? Wer nutzt diese?
- Strukturanalyse: Genauere Erfassung, der  IT-Räume, IT-Systeme (Hard- und Software), Prozesse und Kommunikationsverbindungen, strukturelle Erfassung und Darstellung der Bisherigen Informationen (Beim BSI ,mit Kreuztabellen, Objekt Beschreibung Nutzer Risiko/Schadensklassen Prozesszugehörigkeit)
- Schutzbedarfsfeststellung:
	- Schadensszenarien
	- Zielobjekte festlegen
	- Ziele und Unterziele ableiten
	- Systematisch betrachtet wäre
		1. Gefahrensammlung
		2. Gefährdete Objekte-Personen-Prozesse
		3. Analyse
		4. Zieldefinition (Sicherheitsrelevanz, Schadenskosten vs Risikoverringerungskosten usw.)
		5. Sicherheitskonzept

## Erstellung einer Schutzbedarfsfeststellung
- Gefährdung aufstellen
- Priorisierung der Gefährdung anhand Wahrscheinlichkeiten = Risikoanalyse
- Abhängigkeiten analysieren und darstellen
- Gewichtung nach Schutzzielen (Vertraulichkeit, Integrität und Verfügbarkeit) (Begründung für die Maßnahmen)
- Gewichtung der Maßnahmen:
	- Basismaßnahmen: Regelungen beim Öffnen externer Dokumente
	- Standardmaßnahmen: Sichere und ergonomische Installation, Beseitigung von Metadaten bei Weitergabe
	- Erhöhte Schutzbedarfsmaßnahmen: Verschlüsselung von Dokumenten, Schutz von Formeln

## Allgemeine Schutzmaßnahmen für Software
- Sicherstellen der Software-Integrität:
	- Verwenden von Originaldatenträgern oder geprüften Kopien für die Softwareinstallation.
	- Verhindern von Veränderungen durch Malware, Bit-Fehler oder manipulierte Konfigurationsdateien.
- Erstellung eines Anforderungskatalogs für Standardsoftware:
	- Berücksichtigung von Funktionalität und sicherheitsrelevanten Anforderungen bei der Auswahl von Standardsoftware.
	- Kriterien für die Softwareauswahl sollten in diesem Katalog festgehalten werden.
- Überprüfung der Lieferung von Standardsoftware:
	- Prüfung der Lieferung anhand vorhandener Unterlagen, um sicherzustellen, dass sie bestellt wurde und für den vorgesehenen Zweck ist.
	- Identifizierung von Transportschäden und Sicherstellen der Vollständigkeit der Lieferung.
- Vollständige und sichere Deinstallation von Software:
	- Entfernung aller Dateien, die für den Betrieb der Software auf dem IT-System erstellt wurden.
	- Löschen von Einträgen in Systemdateien.
	- Dokumentation der Installation, um alle während des Installationsprozesses vorgenommenen Änderungen rückgängig machen zu können.

## Beispielhafte Schutzmaßnahmen für Betriebssysteme
- Sicherstellen eines minimalen Systems: Installieren nur unbedingt notwendiger Programme, um das Gefahrenpotenzial zu minimieren.
- Korrekte Konfiguration:
	- Vermeiden einer Standardinstallation für sicherheitskritische Systeme.
	- Individuelle Installation, um nicht benötigte Systemprogramme und Funktionalität zu verhindern.
- Ports sperren: Deaktivieren und sperren aller nicht benötigten Ports, um potenzielle Angriffsvektoren zu minimieren.
- Benutzerkonten:
	- Anlegen nur notwendiger Benutzerkonten.
	- Vergeben von Berechtigungen nach dem Prinzip des geringsten Privilegs, sodass Benutzer nur die benötigten Rechte erhalten.
- Betriebssystem aktuell halten: Umgehende Installation von Sicherheitsupdates nach ihrer Veröffentlichung, um Schwachstellen zu beheben.
- Regelmäßige Sicherheitschecks mithilfe von Log-Dateien: Überprüfung der Betriebssystem-Log-Dateien, um Angriffe und Angriffsversuche zu erkennen und entsprechend zu reagieren.
- Verwendung sicherer Passwörter: Verwenden von starken, schwer zu erratenden Passwörtern, um die Sicherheit der Benutzerkonten zu erhöhen.
- Regelmäßige Datensicherung: Durchführung regelmäßiger Backups, um Datenverlust durch Bedienungsfehler oder Vireninfektionen zu verhindern.

## Schutzmaßnahmen für Office-Produkte
- Einschränken von aktiven Inhalten: Deaktivierung des automatischen Ausführens von aktiven Inhalten wie Makros und ActiveX-Steuerelementen in Office-Dokumenten, um die Verbreitung von Schadprogrammen zu verhindern.
- Regelungen zum Öffnen von Dokumenten aus externen Quellen:
	- Vermeiden des Öffnens von Dokumenten aus unbekannten externen Quellen.
	- Betrachten solcher Dateien bis zur Sicherheitsüberprüfung als "ausführbare Programme".
- Versionskontrolle:
	- Dokumentation der installierten Office-Produktversionen und Konfigurationen auf den Computern.
	- Anstreben der Verwendung derselben Version mit einheitlicher Konfiguration auf allen Rechnern, um Inkompatibilitäten zu vermeiden.
- Beseitigung von Restinformationen vor der Weitergabe von Dokumenten:
	- Überprüfung und Entfernung überflüssiger Meta-Informationen in Office-Dokumenten, die schützenswert sein könnten.
	- Genau festlegen, welche Meta-Daten in einem Dokument enthalten sein dürfen und welche nicht.
- Regelung der Verwendung von Viewer-Funktionen:
	- Verwendung von Dokumenten-Viewern, um das Risiko von Angriffen durch schädlichen Code in Office-Dokumenten zu verringern.
	- Viewer dienen nur zum Anzeigen der Dokumente und sollten keine aktiven Inhalte ausführen.
- Schutz gegen nachträgliche Veränderungen von Informationen:
	- Verwendung von Funktionen in Office-Produkten, um nachträgliche Bearbeitungen von Dokumenten einzuschränken und die Integrität der Informationen zu wahren.

#### Gefährdungslage und Schutzmaßnahmen beim Einsatz von Software-Containern

Software-Container sind eine Virtualisierungstechnik, bei der Anwendungen in separierten Umgebungen auf einem Wirtssystem ausgeführt werden. Im Gegensatz zu virtuellen Maschinen teilen Container das Betriebssystem des Wirts und bieten dadurch eine leichtgewichtige Möglichkeit zur Bereitstellung von Anwendungen. Der Einsatz von Containern hat sich in den letzten Jahren enorm verbreitet, da er die Bereitstellung, Skalierung und Verwaltung von Anwendungen erleichtert. Allerdings erfordert der massenweise Einsatz von Containern besondere Aufmerksamkeit in Bezug auf Sicherheit und Datenschutz.

## Einige grundlegend eSchutzmaßnahmen für Clients näher betrachtet

- Absicherung des Boot-Vorgangs:
	- Schutz vor Angriffen beim Booten von Wechselmedien.
	- Verhindern von Schadprogrammen, die den Boot-Vorgang beeinflussen könnten.
- Zugriff auf Ausführungsumgebungen mit unbeobachteter Codeausführung: Deaktivierung solcher Umgebungen in der Client-Firmware, z.B. Intel Software Guard Extensions (SGX).
- Rollentrennung:
	- Unterscheidung zwischen Benutzer- und Administratorrollen.
	- Administratoren erhalten umfassende Systemverwaltungsrechte.
- Protokollierung:
	- Aktivierung der Protokollierung für sicherheitsrelevante Ereignisse.
	- Regelmäßige Überprüfung der Protokolle, einschließlich unberechtigter Zugriffsversuche.
- Nutzung von TLS:
	- Verwendung von SSL/TLS als Sicherheitsprotokoll bei der Web-Nutzung.
	- Absicherung von Verbindungen durch Verschlüsselung, Datenintegritätsprüfung und Serveridentitätsüberprüfung.
- Deaktivierung und Deinstallation nicht benötigter Komponenten und Kennungen: Überprüfung und Entfernung von unnötigen Benutzerkonten, Programmen, Diensten und Komponenten.
- Benutzerauthentisierung:
	- Eindeutige Identifikation und Authentifizierung von Benutzern.
	- Verwendung von Authentisierungstechniken wie PIN, Passwörter, Zugangskarten oder Biometrie.
- Nutzung von Client-Server-Diensten: Client-Server-Dienste ermöglichen den Austausch von Ressourcen zwischen IT-Systemen, z.B. gemeinsame Nutzung von Druckern.

## Beschreibung ausgewählter Maßnahmen für den sicheren Datenaustausch mittels mobiler Datenträger

- Festlegung zuverlässiger Kommunikationspartner:
	- Sicherstellen, dass Empfänger die notwendigen Berechtigungen für den Datenerhalt und die Verarbeitung besitzen.
	- Überprüfung der Identität des Kommunikationspartners vor der Datenübertragung.
- Verlustmeldung:
	- Unverzügliche Meldung des Verlusts eines mobilen Datenträgers, auch bei dienstlicher Nutzung von privaten Datenträgern.
	- Schnelles Handeln, um potenziellen Missbrauch der verlorenen Informationen zu verhindern.
	- Untersuchung auf mögliche Manipulationen, wenn verlorene Datenträger wieder auftauchen.
- Regelung der Mitnahme von mobilen Datenträgern:
	- Klare Vorschriften zur Mitnahme von mobilen Datenträgern außerhalb des Unternehmens.
	- Festlegung von Berechtigten, Bedingungen und Sicherheitsmaßnahmen für die Mitnahme.
- Regelungen zum Versand von Datenträgern:
	- Schutz der Datenträger während des Versands, um Beschädigungen zu verhindern.
	- Anpassung der Verpackung an die Schutzanforderungen der Datenträger.
	- Festlegung von Versand- und Transportmethoden sowie Nachweisverfahren für den Versand und Empfang.
- Sicheres Löschen der Datenträger vor und nach der Verwendung:
	- Geeignetes Löschen von wiederbeschreibbaren Datenträgern, um Restinformationen zu verhindern.
	- Verwendung von physikalischer Löschung durch Überschreiben mit einem bestimmten Muster.
	- Vermeidung von reinen Löschbefehlen, die oft Restinformationen hinterlassen.
- Verwendung von zertifizierten mobilen Datenträgern:
	- Einsatz ausschließlich zertifizierter Datenträger.
	- Zertifizierung mit Schwerpunkt auf sicherer Datenspeicherung und Verschlüsselung.

---

## Kompetenzcheck

#### Schutzbedarf Arbeitsplatzsoftware Test
| Aussage                                                                                  | Bewertung |
|------------------------------------------------------------------------------------------|-----------|
| In der Regel reicht einfach das Löschen des kompletten Verzeichnisses, in dem die Software installiert ist, um diese sicher vom PC zu entfernen | Falsch    |
| Zur Installation von Software sollten Originaldatenträger verwendet werden               | Wahr      |
| Betaversionen von Software sollten so schnell wie möglich installiert und genutzt werden, weil diese die neuesten Sicherheitsstandards besitzen | Falsch    |
| Wenn möglich sollte immer die gleiche Version eines Office-Produktes mit derselben Konfiguration auf allen Rechnern im Unternehmen installiert sein | Wahr      |
| Container beinhalten kein eigenes Betriebssystem                                         | Wahr      |
| Während des produktiven Einsatzes sollte die Software des Containers nicht verändert werden | Wahr      |
| In der Regel kann man bedenkenlos jede Datei mit einem entsprechenden Programm öffnen     | Falsch    |
| Die Programmierung und Nutzung von Makros in Office-Produkten sollten einheitlichen Regeln unterworfen sein | Wahr      |

#### Schutzbedarf von Clients
| Aussage                                                                                  | Bewertung |
|------------------------------------------------------------------------------------------|-----------|
| In der Regel reicht eine Standardinstallation vom Betriebssystem auf dem Client aus      | Falsch    |
| Über vernetzte Clients können sich Schadprogramme schnell auf andere Systeme übertragen  | Wahr      |
| Das Booten sollte immer auch von einem mobilen Datenträger wie einer externen Festplatte möglich sein, um im Notfall schneller reagieren zu können | Falsch    |
| Für die Nutzung von USB-Sticks sind keine Regelungen erforderlich                          | Falsch    |
| In Clients verbaute Mikrofone sind unbedenklich                                           | Falsch    |
| Viren-Schutzprogramme sollten zur Grundausstattung eines Clients gehören                    | Wahr      |
| In der Regel findet bei der Schutzbedarfsfeststellung für Clients das Minimumprinzip Anwendung | Falsch |
| In den Clients verbaute Kameras könnten zur Spionage genutzt werden                       | Wahr      |
| Der Schutzbedarf ist für alle Clients im Arbeitsbereich gleich                             | Falsch    |
| Es sollte Regelungen geben, ob und inwieweit mobile Datenträger mit einzelnen Clients verbunden werden dürfen | Wahr |

#### Datenaustausch mobile Datenträger
| Aussage                                                                                  | Bewertung |
|------------------------------------------------------------------------------------------|-----------|
| Der Versand von vertraulichen Daten sollte in einer gesicherten Verpackung erfolgen       | Wahr      |
| Über mobile Datenträger kann keine Schadsoftware verbreitet werden                         | Falsch    |
| USB-Sticks stellen einen Großteil der mobilen Datenträger                                  | Wahr      |
| Verschlüsselung ist eine Maßnahme, um Daten auf mobilen Datenträgern zu schützen           | Wahr      |
| Der Verlust oder der Diebstahl von mobilen Datenträgern mit hochsensiblen Daten stellt eine große Gefahr für ein Unternehmen dar | Wahr      |
| In der Regel reicht einfaches Löschen der Daten vom Datenträger, um diesen für den nächsten Gebrauch vorzubereiten | Falsch |
| Der Versand von vertraulichen Daten sollte per Kurierdienst erfolgen                       | Wahr      |
| Der Gebrauch von privaten mobilen Datenträgern zu dienstlichen Zwecken sollte unbedingt gestattet werden | Falsch    |
| Mobile Datenträger sollten zum Datenaustausch ausreichend gekennzeichnet sein               | Wahr      |
| Es sollte immer eine Sicherheitskopie von den Daten, welche ausgetauscht werden sollen, existieren | Wahr      |

#### Arten der Datensicherung
| Aussage                                                                                  | Bewertung |
|------------------------------------------------------------------------------------------|-----------|
| Nur die Dateien werden gesichert, die sich gegenüber der letzten Volldatensicherung geändert haben | Differenzielle Datensicherung |
| Nur die Dateien werden gesichert, die sich gegenüber der letzten inkrementellen Sicherung (oder Volldatensicherung) geändert haben | Inkrementelle Datensicherung |
| Alle zu sichernden Dateien werden zu einem bestimmten Zeitpunkt auf einen zusätzlichen Datenträger gespeichert | Volldatensicherung |
| Eine exakte Kopie der Daten wird laufend in einem anderen Verzeichnis oder Medium erstellt, z.B. als HSM oder RAID-System | Spiegelung |
| Mehrere Datenträger sollten in verschiedenen zeitlichen Abstufungen angelegt werden. Z.B. können für die letzte Woche für jeden Tag eine Tagessicherung, für jede Woche in den vergangenen 28 Tage eine Wochensicherung und für jeden Monat für das vergangene Jahr eine Monatssicherung angelegt werden | Generationenprinzip der Datensicherung |
| Dateien werden je nach Zugriffshäufigkeit in schnellen Datenspeichern, automatischen Datenträgerwechselsystemen oder Offline-Speichern (wie z.B. Magnetbändern) gehalten und archiviert | Hierarchisches Speicher-Management (HSM) |
| Software - eine Vollsicherung, Systemdaten: mindestens einmal monatlich mit einer Generation, Anwendungsdaten: mindestens wöchentlich als Vollsicherung (drei Generationen) Protokolldaten: mindestens einmal monatlich als Vollsicherung in (drei Generationen). Verschlüsselung der personenbezogenen Daten vor der Sicherung | Minimaldatensicherung nach Empfehlung des BSI |
| Dateien werden auf mehreren Festplatten unter dem Kommando eines sogenannten Array-Controllers gespeichert. Dabei werden unterschiedliche Level unterschieden | RAID-System (redundant array of inexpensive disks) |
| Es sollten mindestens drei Kopien der Daten vorhanden sein und Kopien auf zwei unterschiedlichen Medien gespeichert werden. Eine Backup-Kopie soll an einem externen Speicherort gespeichert sein | 3-2-1 Datensicherung |

#### Einsatzgebieten
| Einsatzgebiet                                          | Beschreibung                                                                                              |
|-------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| Cloud-Security                                         | Schutz von Daten, Anwendungen und Infrastruktur, die nicht lokal gespeichert sind, sondern überall erreichbar, vor Bedrohungen                                      |
| Mobile-Security                                        | Schutz vor Bedrohungen im Zusammenhang mit drahtloser Datenverarbeitung                                      |
| VPN                                                    | Einrichtung eines privaten Netzwerks über ein öffentliches Netzwerk zur sicheren Datenübertragung          |
| E-Mail-Security                                        | Sicherung von E-Mail-Konten und deren Inhalt vor Verlust, unerlaubtem Zugriff oder Malware                |
| Endpoint Security                                      | Verwaltung des Computer- und Datenzugriffs der Nutzer über ein Unternehmensnetzwerk                        |
| Next Gen Firewall                                      | Erweiterte Technologien für Netzwerkgeräte wie Deep Packet Inspection und Intrusion Prevention            |




