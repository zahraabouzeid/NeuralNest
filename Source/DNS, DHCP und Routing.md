## Dynamic Host Configuration Protocol
Dieses Protokoll ermöglicht es, neu eingebundene Geräte im Netzwerk automatisch zu konfigurieren. Dazu gehören die dynamische Zuweisung von IP-Adressen und weitere Konfigurationen wie die Netzmaske.

![500](DHCP.png)

## Domain Name System
Der Begriff Domain Name System (kurz: DNS) bezeichnet einen zentralen Dienst in IP-basierten Netzwerken wie Computern. Wird eine Webadresse im Browser eingegeben, leitet das System die Anfrage an die zugehörige IP-Adresse, sprich den Server des Webseiten-Betreibers, weiter, sodass der Nutzer auf die zugehörige Seite gelangt. Somit funktioniert das System ähnlich wie ein Telefonbuch, indem es ein Verzeichnis von Namen darstellt, die mit bestimmten Zahlen (den IP-Adressen) korrespondieren.


## DNS Nachrichtenformat
![500](DNS.png)

## Hierarchie des DNS
![500](Hierarchie%20des%20DNS.png)

`nslookup` 

## Statisches Routing
Routing steht grundsätzlich für Übertragungswege und Schnittstellen, über die Datenpakete in einem Netzwerk gesendet werden. Für eine einzelne Kommunikation können viele Pfade verwendet werden, um einzelne Paket zu einem Ziel zu senden. Wenn es keinen festgelegten
Pfad gibt, werden die Pakete über den zur Zeit besten, verfügbaren Pfad geleitet. Am Ziel können Pakete in der Reihenfolge ihrer Sequenznummer wieder zusammengesetzt werden.

- Die Layer 3 (Vermittlung) des OSI Modelles enthält die Internet Protokolle Version 4 und 6.
- Die Default Gateway hilft um in andere Netze weiterzuleiten. Die Default Gateway eines Gerätes ist die IP Adresse der Router Schnittstelle.
- Um die routing Tabelle anzuschauen, `netstat -r` eingeben.

## Routing Tabelle
- `0.0.0.0` ist die Standard Route. Wenn eine Routingtabelle einen Eintrag mit 0.0.0.0 besitzt, ist dies die sogenannte "Standardroute", die gewählt wird, wenn es keine spezifischeren (besser passenden) Routen für eine Zieladresse gibt.
- die Loopback Adressen sind die Adressen zwischen 127.0.0.0 und 127.255.255.255, und wird vom Gerät selbst benutz um Pakete an sich selbst zu senden. (127.0.0.0/8)
- Lokale Routen 
- Multicast Routen
- Broadcast Routen

Es gibt Routen zu:
- Direkt verbundenen Netzen
- entfernten (remote) Netzen

Da Router nur die direkt angeschlossenen Netze muss man statischer Routen zu entfernten Netzen selber einrichten.

## Metrik
 ist die Anzahl der Router, die ein Paket auf seinem Weg passieren muss, bevor es zum Empfänger gelangt. Wann immer Daten durch einen Router bewegt werden, spricht man von einem Hop. Wenn man von einem Pfad sagt, dass er vier Hops aufweise, dann müssen die Daten vom Absender kommend vier Router passieren, bevor sie beim Empfänger ankommen. Gibt es mehrere Pfade, dann wählt der Router den Pfad mit der geringsten Anzahl an Hops. Der OSPF berechnet seine Metrik aufgrund der Bandbreite.

> [!tip]
> `ping` überprüft die Erreichbarkeit eines Hosts.
`Tracert` zeigt den Weg zu einem Zielsystem auf.