## Protokolle
#### Nachrichtenkodierung
Quelle der Nachricht => Kodierer => Sender => Übertragungsmedium (Der Kanal) => Empfänger => Dekodierer => Ziel der Nachricht.
#### Nachrichtenformatierung und Kapselung
![400](Nachrichtenkapselung.png)
#### Nachrichtengröße 
Ein Nachrichten wird in kleiner Teile aufgeteilt, weil die Größenbeschränkung notwendig ist.
#### Zeitliche Steuerung von Nachrichten
1. Zugriffsmethode 
	- wann darf gesendet werden?
	- wer darf senden?
2. Flussteuerung
	- wie schnell?
	- wie viel? 
1. Antwort-Zeitüberschreitung / Timeout 
	- was passiert, wenn nichts passiert?
#### Nachrichtenübermittlungsoptionen
- Unicast
- Broadcast
- Multicast

## Protokollfamilien und Regeln
Protokollfamilien sind Regelsätze, die zusammenwirken, um ein Problem zu lösen.
#### Inhaltsschicht
Wo ist das Café?
#### Regelschicht
- Verwenden Sie eine gemeinsame Sprache 
- Warten Sie, bis Sie dran sind
- Geben Sie ein Zeichen, wenn Sie fertig sind
#### Physische Schicht

## Protokolle beschreiben:
#### Wie die Nachricht formatiert oder strukturiert ist:
Ich benutze den IPv4-Header => Ich leite die Nachricht weiter, da ich den IPv4 Header verstehe => Ich nehme diese Nachricht an, da ich IPv4 verstehe)

#### Den Prozess, mit dem Netzwerkgeräte Informationen über Pfade zu anderen Netzwerken übertragen:
Wir informieren verbundene Geräte, falls einer unserer Verbindungspfade ausfällt.

#### Wie und wann Fehler und Systemmeldungen zwischen den Geräten weitergeleitet werden:
Jede Fehlermeldung erhält eine eindeutige ID-Nummer:
- Fehler 1002: Pfad ist langsam.
- Fehler 1001: Pfad ist ausgefallen

#### Den Verbindungsauf und Abbau einer Datenübertragung:
Ich möchte eine virtuelle Verbindung mit dir aufbauen => Ich bin damit einverstanden

## Zusammenspiel der Protokolle
**Netzwerkzugriff:** Ethernet => **Internet:** Internet Protocol (IP) => **Transport:** Transmission Control Protocol => **Anwendung:** HTTP (Hypertext Transfer Protocol)

## TCP/IP Protokollfamilie
#### Anwendungsschicht
Präsentiert die Daten dem Endbenutzer und übernimmt zusätzlich die Kodierung und die Dialogsteuerung
- **Name des Systems:** DNS (Domain Name Service)
- **Host Konfiguration:** BOOTP (Bootstrap Protocol), DHCP (Dynamic Host Configuration Protocol)
- **Email:** SMTP (Simple Mail Transfer Protocol), POP (Post Office Protocol), IMAP (Internet Message Access Protocol)
- **Dateiübertragung:** FTP (File Transfer Protocol), TFTP (Trivial File Transfer Protocol)
- **Web:** HTTP (Hypertext Transfer Protocol)

#### Transportschicht
Unterstützt die Kommunikation zwischen unterschiedlichen Geräten über unterschiedliche Netzwerke hinweg
- UDP (User Datagram Protocol)
- TCP (Transmission Control Protocol)

#### Internetschicht
Bestimmt den besten Pfad durch das Netzwerk.
- IP (Internet Protocol), NAT (Network Address Translation)
- **IP Unterstützung:** ICMP (Internet Control Message Protocol)
- **Routing-Protokolle:** OSPF (Open Shortest Path First), EIGRP (Enhanced Interior Gateway Routing Protocol)

#### Netzwerkzugriffsschicht
Steuert die Geräte und Medien, die zusammen das Netzwerk bilden.
- ARP (Address Resolution Protocol)
- PPP (Point-to-Point Protocol)
- Ethernet
- Schnittstellentreiber (Internet Interfaces)

## Kapselung und Entkapselung
![400](Kapselung.png)

## Standardsorganisation
Standards vereinfachen die Kommunikation:
- EIA Standards (Ekectronic Industries Alliance)
- IETF (Internet Engineering Task Force)
- IEEE (Institute of Electrical and Electronics Engineers)
- iana (Internet Assigned Numbers Authority)
- ICANN (Internet Corporation for Assigned Names and Numbers)
- ITU (International Telecommunication Union)
- TIA (Telecommunication Industry Association)

## Referenzmodelle
Ein Netzwerkmodell ist lediglich eine Darstellungsweise für den Betrieb eines Netzwerks. Das Modell ist nicht das tatsächliche Netzwerk.

![500](OSI.png)

#### Bitübertragung (Physical)
Die Normen und Protokolle der Bitübertragungsschicht beschreiben die mechanischen, elektrischen, funktionalen und verfahrenstechnischen Mittel, um eine physikalische Verbindung für die Bitübertragung zwischen Netzwerkgeräten zu aktivieren, aufrecht zu erhalten und wieder zu deaktivieren.

#### Sicherung (Data Link)
Die Protokolle der Sicherungsschicht (Data Link Layer) legen Methoden für den Austausch von Datenrahmen (Frames) über eine gemeinsames Medium fest. Tauscht Frames zwischen Geräten aus.

#### Vermittlung (Network)
Die Vermittlungsschicht stellt Dienste bereit für den Austausch der einzelnen Datenblöcke über das Netzwerk zwischen eindeutig festgelegten Endgeräten. Die Schicht beinhaltet unter anderem Definitionen zu elektrischen Signalen, Kabeln und
auch Steckern.

#### Transport
Die Transportebene definiert Dienste für die Segmentierung, die Übertragung und die Wiederzusammensetzung der Daten für die einzelnen Kommunikationsverbindungen der Endgeräte. Segmentiert die Daten, überträgt sie und setzt sie in der richtigen Reihenfolge wieder
zusammen

#### Sitzung (Session)
Die Sitzungsschicht, stellt der Darstellungsschicht Dienste zur Verfügung, um deren Dialog zu steuern und den Datenaustausch zu verwalten.

#### Darstellung (Presentation)
Die Darstellungsschicht sorgt für eine gemeinsame Darstellung der Daten, die zwischen den Diensten der Anwendungsschicht ausgetauscht werden.

#### Anwendung (Application)
Die Anwendungsschicht stellt die Mittel für eine Ende-zu-Ende Verbindung zwischen Personen bereit, die ein Datennetz für ihre zwischenmenschliche Vernetzung verwenden. Diese Schicht stellt Funktionen, z. B. für Mail-Client Programme, zur Verfügung.

## Segmentierung von Nachrichten
Die Aufteilung der Kommunikation in Teilestücke.
## Kennzeichnung von Nachrichten
Die einzelnen Teile einer Nachricht werden mit einer Kennzeichnung versehen. Dies erleichtert die weiterleitung und die zusammensetzung beim Empfänger. Sie sorgt für die korrekte Anordnung und den Zusammenbau der Teile, wenn sie ankommen.

## Protocol Data Units (PDUs)
![500](PDUs.png)

## Adressierung
Adressen der Vermittlungsschicht und Adressen der Sicherungsschicht

![500](Adressierung.png)
## Layer 3: IP Adressen
![500](IP-Adressen.png)

## Layer 2: Adressen der Sicherungsschicht
![500](Layer%202.1.png)
![500](Layer%202.2.png)
![500](Layer%202.3.png)

## Kommunikation mit einem Gerät im selben Netzwerk
![500](Kommunikation%20mit%20einem%20Gerät%20im%20selben%20Netzwerk.png)

## Kommunikation mit einem Gerät in einem Remote-Netzwerk
![500](Kommunikation%20mit%20einem%20Gerät%20in%20einem%20Remote-Netzwerk.png)