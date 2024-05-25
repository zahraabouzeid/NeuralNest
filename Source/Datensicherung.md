## JBOD (Just a Bunch Of Disks) 
- Verbund von Festplatten 
- Eine Festplatte nach der anderen wird beschrieben
## RAID Systeme
Redundant Array of Independent Discs

#### Vorteile
- schnellerer Daten-Zugriff 
- größere Speicherkapazitäten 
- Erhöhung der Ausfallsicherheit

## RAID 0 - Striping
![200](RAID%200.png)
**Vorteile:** 
- Kapazitätsvergrößerung: Mehrere physikalische Festplatten erscheinen als eine logische Festplatte 
- schnellerer Daten-Zugriff

**Nachteile:** 
keine Redundanz (no Fault Tolerance)

**Verfügbarkeit:**
Verfügbarkeit HD: 99% 
Raid 0 mit 3 HDs 
- wenn eine Platte ausfällt ist der GAU erreicht 
- Wahrscheinlichkeit, dass keine Festplatte ausfällt: 0,99 x  0,99 x 0,99 = 97,0299% 
- Ausfallwahrscheinlichkeit von 2,9701%, ist also ca. um Faktor 3 größer geworden.

## Raid 1 - Mirroring
**Vorteile:**
 - Redundanz 

**Nachteile:** 
- Nettodatenkapazität verkleinert sich auf 50% 
- i.d.R. langsamer als RAID 0

**Verfügbarkeit:**
Verfügbarkeit HD: 99% 
Raid 1 mit 2 HDs 
- wenn beide Platten ausfallen ist der GAU erreicht 
- Wahrscheinlichkeit, dass beide Festplatten ausfallen: 0,01 x 0,01 = 0,0001 
- Ausfallwahrscheinlichkeit ist um Faktor 100 kleiner geworden

## Raid 5 - Performance und Parität
bei > 3 Festplatten
![500](RAID%205.png)

Falls die 3. Festplatte ausfällt, wird aus der 1. und 2. ein 3. rekonstruiert.

#### Raid 5 mit 5 Festplatten
![500](Raid%205%20Beispiel.png)

## RAID 6 
![](RAID%206.png)

- Ähnlich wie bei Raid 5 werden Paritätsinformationen erzeugt und auf die Festplatten des Raid verteilt 
- Es werden 2 Paritätsblöcke (Redundanz) erstellt und jeweils auf 2 Festplatten verteilt
- >= 4 Festplatten nötig

## Kombiniete RAIDs
![500](RAID%2010.png)

![500](RAID%2050.png)

![500](RAID%2060.png)

> [!info]
> Eine spare Festplatte (Hot) ist eine Festplatte in einem System laufende, aber nicht verwendete Festplatte. Fällt eine andere Platte aus, wird die HotSpare-Platte im laufenden Betrieb automatisch anstelle der defekten Platte ein.

## Hardware und Software Raid
**Hardware-RAID**:
- Hardware-RAID wird durch eine spezielle RAID-Controller-Karte implementiert, die in das Motherboard oder den PCIe-Steckplatz des Computers eingesteckt wird.
- Die RAID-Controller-Karte übernimmt die gesamte RAID-Verarbeitung und Verwaltung unabhängig von der CPU des Computers.
- Hardware-RAID bietet oft eine bessere Leistung, da die RAID-Berechnungen und Operationen von der speziellen Hardware ausgeführt werden.
- Diese Art von RAID ist in der Regel teurer als Software-RAID, da zusätzliche Hardwarekomponenten benötigt werden.

**Software-RAID**:
- Software-RAID wird durch die RAID-Funktionen implementiert, die in das Betriebssystem integriert sind.
- Die RAID-Verwaltung erfolgt durch die CPU des Computers und die Software des Betriebssystems.
- Software-RAID kann kostengünstiger sein, da keine spezielle Hardware erforderlich ist. Es kann auch auf Standard-Hardware laufen.
- Die Leistung von Software-RAID kann von der CPU-Auslastung des Systems beeinflusst werden, insbesondere bei intensiven RAID-Operationen.