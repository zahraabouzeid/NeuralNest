Eine IP-Adresse (Internet Protocol) ist eine eindeutige Adresse, die ein Gerät im Internet oder in einem lokalen Netzwerk identifiziert.
# IPv4 Adresse
**Dotted Decimal Format (Dezimal Punktnotation):** eine Adresse besteht aus vier verschiedenen Oktetten.

| 192      | 168      | 10       | 10       |
| -------- | -------- | -------- | -------- |
| 11000000 | 10101000 | 00001010 | 00001010 |
## IP-Subnetzmaske
Von dem möglichen Anzahl an Hostbits wird 1 bit für die Netzwerk und 1 bit für Broadcast abgezogen.

$Hosts = 2^{(Anzahl\ an\ Hostbits)}-2$

```bash
Address:   192.168.10.10        11000000.10101000.00001010. 00001010
Netmask:   255.255.255.0 = 24   11111111.11111111.11111111. 00000000
Wildcard:  0.0.0.255            00000000.00000000.00000000. 11111111
=>
Network:   192.168.10.0/24      11000000.10101000.00001010. 00000000
HostMin:   192.168.10.1         11000000.10101000.00001010. 00000001
HostMax:   192.168.10.254       11000000.10101000.00001010. 11111110
Broadcast: 192.168.10.255       11000000.10101000.00001010. 11111111
Hosts/Net: 254                   Class C, Private Internet
```

```bash
Address:   10.1.1.0             00001010.00000001.00000001. 00000000
Netmask:   255.255.255.0 = 24   11111111.11111111.11111111. 00000000
Wildcard:  0.0.0.255            00000000.00000000.00000000. 11111111
=>
Network:   10.1.1.0/24          00001010.00000001.00000001. 00000000
HostMin:   10.1.1.1             00001010.00000001.00000001. 00000001
HostMax:   10.1.1.254           00001010.00000001.00000001. 11111110
Broadcast: 10.1.1.255           00001010.00000001.00000001. 11111111
Hosts/Net: 254                   Class A, Private Internet
```

```bash
Address:   10.1.1.0             00001010.00000001.00000001.0 0000000
Netmask:   255.255.255.128 = 25 11111111.11111111.11111111.1 0000000
Wildcard:  0.0.0.127            00000000.00000000.00000000.0 1111111
=>
Network:   10.1.1.0/25          00001010.00000001.00000001.0 0000000
HostMin:   10.1.1.1             00001010.00000001.00000001.0 0000001
HostMax:   10.1.1.126           00001010.00000001.00000001.0 1111110
Broadcast: 10.1.1.127           00001010.00000001.00000001.0 1111111
Hosts/Net: 126                   Class A, Private Internet
```

```bash
Address:   10.1.1.0             00001010.00000001.00000001.00 000000
Netmask:   255.255.255.192 = 26 11111111.11111111.11111111.11 000000
Wildcard:  0.0.0.63             00000000.00000000.00000000.00 111111
=>
Network:   10.1.1.0/26          00001010.00000001.00000001.00 000000
HostMin:   10.1.1.1             00001010.00000001.00000001.00 000001
HostMax:   10.1.1.62            00001010.00000001.00000001.00 111110
Broadcast: 10.1.1.63            00001010.00000001.00000001.00 111111
Hosts/Net: 62                    Class A, Private Internet
```

```bash
Address:   10.1.1.0             00001010.00000001.00000001.000 00000
Netmask:   255.255.255.224 = 27 11111111.11111111.11111111.111 00000
Wildcard:  0.0.0.31             00000000.00000000.00000000.000 11111
=>
Network:   10.1.1.0/27          00001010.00000001.00000001.000 00000
HostMin:   10.1.1.1             00001010.00000001.00000001.000 00001
HostMax:   10.1.1.30            00001010.00000001.00000001.000 11110
Broadcast: 10.1.1.31            00001010.00000001.00000001.000 11111
Hosts/Net: 30                    Class A, Private Internet
```

```bash
Address:   10.1.1.0             00001010.00000001.00000001.0000 0000
Netmask:   255.255.255.240 = 28 11111111.11111111.11111111.1111 0000
Wildcard:  0.0.0.15             00000000.00000000.00000000.0000 1111
=>
Network:   10.1.1.0/28          00001010.00000001.00000001.0000 0000
HostMin:   10.1.1.1             00001010.00000001.00000001.0000 0001
HostMax:   10.1.1.14            00001010.00000001.00000001.0000 1110
Broadcast: 10.1.1.15            00001010.00000001.00000001.0000 1111
Hosts/Net: 14                    Class A, Private Internet
```

## Bestimmung des Netzwerkes
Gegeben sind 2 IP Adressen. Wir bestimmen mithilfe der gleichen Subnetmaske,  die Netzwerk Adresse. Kommt ein gleiches Ergebnis, befinden beide Geräte im selben Netzwerk.

## UND Verknüpfung
Wie die oben gegebenen Beispiele werden immer die bits der Adresse mit dem Subnetmask verglichen. 
- `1 UND 1 => 1`
- `1 UND 0 => 0`
- `0 UND 0 => 0`

## IP-Konfiguration
> [!info]
> Die Default gateway eines Gerätes ist die IP Adresse der Router

```bash
ipconfig # On Windows
ifconfig # On Unix
```

Es gibt zwei Methoden um IPs zu konfigurieren:
- Statische IP-Konfiguration
- Dynamische IP-Konfiguration

## Broadcast
Ein Broadcast ist eine spezielle Form der Mehrpunktverbindung, die es erlaubt, gleichzeitig eine Nachricht an alle Teilnehmer eines Netzwerks zu verschicken, ohne dass diese wissen, an wen die Nachricht noch versendet wurde. Der Absender muss im Gegensatz zum Unicast, wo nur ein einzelner, bekannter Empfänger adressiert wird, nicht explizit Empfänger angeben, sondern dafür kommt eine Broadcast Adresse bzw. Broadcast-IP zum Einsatz. Ein Netzteilnehmer schickt ein Datenpaket bzw. eine Nachricht von einem Punkt aus gleichzeitig an alle Teilnehmer dieses Netzes.
#### Limited Broadcast:

Beim Limited Broadcast wird als Ziel die **IP-Adresse 255.255.255.255** angegeben. Von der technischen Seite aus zielt dieser Broadcast zwar auf alle IP-Adressen, in der Praxis liegt das Ziel jedoch immer im eigenen lokalen Netz und wird so direkt in einen Ethernet-Broadcast umgesetzt. Eine Weiterleitung der Datenpakete vom Router findet beim Limited Broadcast nicht statt.
#### Directed Broadcast
Beim Directed Broadcast (Gerichtete Broadcast Adresse) werden immer alle Empfänger innerhalb eines bestimmten Netzes adressiert. Die Broadcast-Adresse ist in diesem Fall eine Kombination aus der IP-Adresse des Zielnetzwerks und dem Setzen aller Hostbits auf 1. Sofern sich das Ziel nicht im eigenen Netz befindet, wird das Datenpaket vom Router weitergeleitet.

`Netzwerk Adresse mit 1s in Host Teil`
## Multicast
IP-Multicasting, ermöglicht die Übertragung von einem Punkt zu mehreren Empfängern. Aus diesem Grund bezeichnet man Multicast-Verbindungen auch als Punkt-zu-Mehrpunkt-Verbindung.
(siehe Class D Netze)

## Private Adressen
> [!info]
> Das Internetprotokoll Version 4 (IPv4) hat eine Obergrenze von 3.706.452.992 öffentlichen Adressen.

Private IPs können das Internet nicht erreichen, da viele Geräte dieselbe private IP haben.

| Prefix         | First Address | Last Address    | Class   |
| -------------- | ------------- | --------------- | ------- |
| 10.0.0.0/8     | 10.0.0.0      | 10.255.255.255  | Class A |
| 172.16.0.0/12  | 172.16.0.0    | 172.31.255.255  | Class B |
| 192.168.0.0/16 | 192.168.0.0   | 192.168.255.255 | Class C |
#### Besondere IPv4 Adressen
Der Router leitet **TEST-NET** (192.0.2.0/24) und **Link-Local-Adressen** (169.254.0.0/16) nicht weiter, denn diese können nur innerhalb des lokalen Netzwerks kommunizieren.
## Öffentliche Adressen
Wenn du das Internet erreichen möchtest, sendest du Informationen an deinen Router und der Router verwendet seine öffentliche IP-Adresse, um Daten zusammen mit einigen Angaben zu deinem Gerät an das Internet zu senden. Anschließend werden die Daten aus dem Internet an den Router zurückgesendet und der Router sendet Daten an dein Gerät.
> [!info]
> Internetdienstanbieter (ISPs) stellt dir den Internetzugang zur Verfügung, indem sie dir auf die eine oder andere Weise eine öffentliche IP zuweisen.

## Aufteilung der IPv4 Adressen in Netzwerkklassen

| Class | Anteil |
| ----- | ------ |
| A     | 50 %   |
| B     | 25 %   |
| C     | 12.5 % |
| D & E | 12.5 % |
#### Class A Netze
![500](Class%20A.png)
- Bit 0 => 0 ist das **höchstwertigstes** Bit
- 0 bis 127 mögliche Netzwerke
- 0.x.x.x bis 127.x.x.x mögliche IP Adressen
- $2^{24}$ mögliche Rechneradressen

**Sonder-Adressen:**
- 10.x.x.x ist ein privates Class A Netz und wird offiziell nicht vergeben.
- 0.0.0.0 ist die Standardroute und wird für das Routing verwendet.
#### Class B Netze
![500](Class%20B.png)
- Bit 0 und 1 => 10
- 128.0 bis 191.255 mögliche Netzwerke ($2^{16-2}=16384$)
- $2^{16}$ mögliche Rechneradressen

**Sonder-Adressen:**
172.16.x.x bis 172.31.x.x sind private Class B Netze und werden offiziell nicht vergeben.
#### Class C Netze
![500](Class%20C.png)
- Bit 0, 1 und 2 => 110
- 192.0.0 bis 223.255.255 mögliche Netzwerke ($2^{21}=2097152$)
- 256 mögliche Netzwerkadressen
#### Class D Netze
![](Class%20D.png)
- Bit 0, 1, 2 und 3 => 1110
- Alle verfügbaren hosts Bit werden für Multicast benutzt.
- Multicasting erfolgt über das spezielles Protokoll IGMP  (Inter Group Management Protokoll)
- IGMP -> RFC 1112

**IGMP Header**
![500](IGMP.png)
#### Class E Netze
![](Class%20E.png)
- Adressbereich 240.0.0.0 bis 255.255.255.255
- Reserviert für experimentelle Zwecke

## Die drei Stufen von ISP
![400](Tier%201.png)
![400](Tier%202.png)
![400](Tier%203.png)

# IPv6 Adresse
## IPv4 und IPv6 im Vergleich
- IPv4 verfügt über 4,2 Milliarden ($2^{32}$) Adressen und hat eine uneffektive Adressvergabe.
- IPv6 verfügt über $2^{128}=3,4\times10^{38}$ Adressen
- Jedem Erdbewohner stehen $6,5\times10^{28}$ Adressen zur Verfügung. (veraltet, wir sind nicht mehr 5 200 000 000 Bewohner)
- 667 Billiarden IP-Adressen pro mm2
- Eine Adresse pro Erdmolekül

## Koexistenz IPv4 & IPv6
- **Dual Stack:** Auf Dual-Stack-Geräten laufen die IPv4-und IPv6-Protokolle gleichzeitig.
- **Tunneling:** ein Verfahren, um ein IPv6-Paket über ein IPv4-Netzwerk zu transportieren. Das IPv6-Paket wird ähnlich wie bei anderen Datentypen in ein IPv4-Paket gepackt.
- **Übersetzung:**  due Network Address Translation 64 (NAT64) ermöglicht IPv6-fähigen Geräten, unter Verwendung einer Übersetzungstechnik ähnlich wie NAT für IPv4 mit IPv4-fähigen Geräten zu kommunizieren. Ein IPv6-Paket wird in ein IPv4-Paket übersetzt und umgekehrt.

## Schreibweise
![400](Hextets.png)

- 8 Word-Gruppen zu je 4 Zeichen in hexadezimaler Schreibweise (1 Hextet binäre Ziffern)
- 8 x 4 x 4 Bit = 128 Bit
- eine Folge von Nullen kann mit 2 Doppelpunkten abgekürzt werden
	**Beispiel:** Localhost
		- IPv4:  127.0.0.1
		- IPv6:  0000:0000:0000:0000:0000:0000:0000:0001 => ::1
- Führende Nullen können in den Word-Gruppen weggelassen werden
	A000:0003:0042:0000:0000:0002:0000:0001 => A000:3:42::2:0:1

- IPv6 Adresse werden wie in der CIDR Slash-Notation in Präfix und Netzteil unterteilt
	- IPv6-adress/prefix-length
	- 4711:0:0:0:5:0:0:0/32   Präfix: 4711:0:, Länge=32Bit
	- Die Präfixtabelle ist in RFC2373 definiert

>[!info]
>Die Loopback-Adresse ist eine reservierte Netzwerkschnittstelle, die vom lokalen System für eine prozessinterne Konfiguration verwendet wird. Über diese Adresse kann der Host Pakete an sich selbst senden.
#### Komprimierung
![400](Komprimierung.png)

## IPv6 Unicast Adressen
#### Präfixlänge
/64 heißt 64 Bit im Präfix
![400](Präfixlänge.png)

![400](IPv6%20Unicast.png)

## Link-Local
Die Router leitet nicht die Pakete weiter.
![400](FE80.png)

## Global Unicast Adressen
Die globale Unicast-Adresse entspricht der öffentlichen IPv4-Adresse. Globale Unicast-Adressen in IPv6 sind global identifizierbar und eindeutig adressierbar.

![400](Global%20Unicast.png)
Die Schnittstellen-ID ist ein zufällig generiertes Zahl.

![400](Global%20Unicast%20Beispiel.png)

## Extended Unique Identifier (EUI-64)
![500](EUI-64.png)
## Multicast
![500](All%20Nodes.png)
![500](Solicited%20Node.png)

## Router Solicitation
Ich brauche Adressierungsinformationen vom Router.
## Router Advertisement Nachrichten
#### Option 1 (nur SLAAC)
Ich bin alles, was du brauchst (Präfix, Präfix-Länge, Default Gateway)
#### Option 2 (SLAAC und DHCPv6)
Hier ist meine Information, aber du musst weitere Informationen wie z.B. DNS-Adresse von einem DHCPv6-Server erhalten.
#### Option 3 (Nur DHCPv6) 
Ich kann ich dir nicht helfen. Frage einen DHCPv6-Server nach allen deinen Informationen.

## ICMPv6 Neighbor Discover Protokoll
#### Adressauflösung
Ich brauche die Ethernet-MAC-Adresse des Gerätes, das diese Unicast-Adresse hat.
#### Doppeladresserkennung (DAD)
Bevor ich diese Adresse verwende, benutzt sonst jemand auf
dieser Verbindun diese Globale Unicast-Adresse?

## Art der IPv6 Adresse im Fazit

| Erstes Hextett | Art der IPv6-Adresse                                                                                                                                               |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 0000 bis OOFF  | Loopback-Adresse, beliebige Adresse, nicht näher spezifizierte Adresse oder IPv4-kompatibel                                                                        |
| 2000 bis 3FFF  | Global-Unicast-Adresse (eine routingfähige Adresse in einem Bereich von Adressen, der derzeit von der Internet Assigned Numbers Authority IANA vergeben wird)      |
| FE80 bis FEBF  | Link-Local-Adresse (eine Unicast-Adresse, die den Host Computer im lokalen Netzwerk identifiziert)                                                                 |
| FC00 bis FCFF  | Unique-Local-Adresse (eine Unicast-Adresse, die einem Host zugeordnet werden kann, um ihn als Teil eines bestimmten Subnetzes im lokalen Netzwerk zu kennzeichnen) |
| FF00 bis FFFF  | Multicast-Adresse                                                                                                                                                  |
