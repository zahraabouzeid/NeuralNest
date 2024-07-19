## Klein
- Je kleiner eine Funktion ist, wird sie besser lesbar und verstehbar
- "Eine Funktion sollte nicht länger als eine Bildschirmseite sein". Diese Regel stimmt nicht mehr, denn heutzutage können wir mehr als 100 Zeilen auf einem Bildschirm unterbringen.
- Jede Funktion soll einen erkennbaren Zweck haben.
- Blöcke in if, else, while Anweisungen sollten eine Zeile lang sein und einen Funktionsaufruf der aussagekräftig ist enthalten.
- Einrückungstiefe einer Funktion sollte maximal ein bis zwei Ebenen betragen um die Lesbarkeit einer Funktion zu erleichtern, bzw. nicht sehr viel verschachtelte Strukturen aufnimmt.
## Eine Aufgabe erfüllen
- Funktionen sollten eine Aufgabe erledigen.
- Sie sollten sie gut erledigen.
- Sie sollten keine andere Aufgaben erledigen.
- die Schritte der Funktion sollen eine Abstraktionsebene unter dem Zweck liegen, der durch den Namen der Funktion ausgedrückt wird.
- Wenn eine Funktion nur die Schritte, die in der Name ausgedrückt sind, erledigt heißt es, dass sie nur eine Aufgabe erledigt.
- eine Funktion erfüllt mehr als eine Aufgabe, wenn Sie aus ihr eine andere Funktion mit einem Namen extrahieren können, der nicht nur eine Neuformulierung ihrer Implementierung ist.
- Funktionen, die eine Aufgabe erledigen, können nicht vernünftigerweise in Abschnitte zerlegt werden.

## Eine Abstraktionsebene pro Funktion
- die Anweisungen innerhalb einer Funktion müssen alle auf derselben Abstraktionsebene befinden.
- Abstraktionsebenen innerhalb einer Funktion zu vermischen, ist immer verwirrend.
- Dass eine Funktion viele Details hat, führt dazu, dass im Laufe der Zeit immer mehr details anzieht.

## Die Stepdown-Regel
- Code sollte wie eine Erzählung von oben nach unten gelesen werden können.
- Hinter jede Funktion müssen andere Funktionen auf der nächsttieferen Abstraktionsebene stehen
- Wir sollen immer eine Abstraktionsebene tiefer gehen, wenn wir die Liste der Funktionen von oben nach unten lesen.

## Single Responsibility Prinzip
Eine Klasse oder ein Modul sollte nur einen Grund für eine Änderung haben

## Open Closed Prinzip
Eine Erweiterung im Sinne des Open-Closed-Prinzips ist beispielsweise die Vererbung. Diese verändert das vorhandene Verhalten der Einheit nicht, erweitert aber die Einheit um zusätzliche Funktionen oder Daten.

## Switch-Anweisungen
Da switch-Anweisungen auf N Aufgaben ausgelegt sind, müssen wir dafür sorgen, dass jede switch-Anweisung tied in einer niedrig angesiedelten Klassen vergraben ist und dafür verwenden wir den Polymorphismus.

#### Lösung
die switch-Anweisung in den Keller einer Abstract Factory zu verbannen und niemals von jemandem sehen zu lassen. Die Factory erstellt anhand der switch-Anweisung die entsprechenden Instanzen der abgeleiteten Klassen

```java
public abstract class Employee {
    public abstract boolean isPayday();
    public abstract Money calculatePay();
    public abstract void deliverPay(Money pay);
}

public interface EmployeeFactory {
    Employee makeEmployee(EmployeeRecord r) throws InvalidEmployeeType;
}

public class EmployeeFactoryImpl implements EmployeeFactory {
    public Employee makeEmployee(EmployeeRecord r) throws InvalidEmployeeType {
        switch (r.type) {
            case COMMISSIONED:
                return new CommissionedEmployee(r);
            case HOURLY:
                return new HourlyEmployee(r);
            case SALARIED:
                return new SalariedEmployee(r);
            default:
                throw new InvalidEmployeeType(r.type);
        }
    }
}
```

## Beschreibende Namen verwenden
- gute Namen für Funktionen finden
- je kleiner eine Funktion ist desto leichter findet man einen beschreibenden Namen dafür.
- Lange Namen sind auch in Ordnung, denn ein langer beschreibender Name ist besser als ein kurzer geheimnisvoller Name.
- Ein Langer Name ist besser als ein Kommentar.

## Funktionsargumente
- Die Anzahl die Argumente einer Funktion soll am besten weniger als 3 sein.
- Je mehr Argumente es gibt, desto wird das Testen schwieriger.
- Output-Argumente sind schwerer zu verstehen als Input-Argumente.
- Bei einer monadischen Funktion, kann man eine Frage über das Argument stellen.
- Eine monadische Funktion ist auch nutzbar bei Ereignisse.
- Flag Argumente (Boolean) bei einer monadischen Funktion sind schlecht, es ist besser wenn die Funktion in zwei verschiedene Funktionen zerlegt wird.
- Manchmal ist eine dyadische Funktion nötig, zum Beispiel bei einer Funktion die Kartesische Koordinaten erfordert.
- Wenn eine Funktion mehrere Argumente erfordert, wäre besser diese Argumente in einer Klasse auszulagern.
- Mehrere Argumente sind in einer Array auszulagern.
>[!info]
> - niladish: null Argumente
> - monadisch: 1 Argument
> - dyadisch: 2 Argumente
> - triadisch: 3 Argumente
> - polyadisch: mehr als 3 Argumente

## Nebeneffekte vermeiden
Eine Funktion sollte nur eine Aufgabe erfüllen und keine andere verborgene Aufgaben.

## Anweisung und Abfrage trennen
Eine Funktion sollte etwas zurückgeben oder etwas ändern aber nicht beides gleichzeitig.

## Try Catch - Blöcke extrahieren
Die Körper des try und catch Blocks ist in eine separate Funktion zu extrahieren.

## Don't Repeat Yourself
_DRY: Wiederhole dich nicht!_
Wenn ein Algorithmus sich mehr Mals wiederholt, sollte es in einer Funktion ausgelagert werden.

## Strukturierte Programmierung
Eine Funktion sollte nur eine return Anweisung, keine break oder
continue Anweisungen in einer Schleife und niemals, wirklich niemals, goto Anweisungen enthalten. Dieser Prinzip ist beim größere Funktionen zu verfolgen.