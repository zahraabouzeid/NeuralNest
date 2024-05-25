## Zweckbeschreibende Namen wählen
- Gute Namen zu wählen braucht zwar Zeit, spart aber letztendlich mehr Zeit ein.
- Der Name der Variablen, Klassen und Funktionen sollte es genau beschreiben, warum es existiert, was er tut und wie er benutzt wird.
- Ein guter Name braucht keinen Kommentar dazu.
- Namen die ihren Zweck ausdrücken macht den Code leichter zu verstehen und zu ändern.
- Ein Code muss implizit sein.
- Implizität heißt, wie weit der Kontext aus dem Code hervorgeht.
- Gute Name ändern die Einfachheit des Codes. Allerdings ist der Code viel expliziter und drückt seinen Zweck.
- Gute Namen machen den Code verständlicher.

## Fehlinformationen vermeiden
- Einige Wörter bedeuteten für einen Programmierer etwas ganz Spezielles . 
- Wenn eine Variable nicht tatsächlich eine List ist, könnte `List` in der irreführend sein.
- Man muss auf Name achten, die sich geringfügig unterscheiden.
- Der Unterschied zwischen zwei Wörter muss ganz schnell entdeckt werden.
- **l** oder **O** als Variablennamen sind irreführende Namen

## Unterschiede deutlich machen
- Wenn die Namen unterschiedlich sein müssen, dann sollten sie auch etwas Verschiedenes bezeichnen
- Namen mit Zahlenserien `a1, a2, aN` sind keiner zweckvollen Benennung und sind informationsleer.
- Wörter mit unterschiedliche Namen sollen andere Bedeutung haben.
- Das Wort variable sollte niemals in einem Variablennamen erscheinen

## Aussprechbare Namen verwenden
Namen die Sie nicht aussprechen können, können Sie nicht darüber diskutieren.

## Suchbare Namen verwenden
- Namen sollen leicht suchbar sein.
- numerischen Konstanten sind in einem Textabschnitt zu schwer zu finden.

## Codierungen vermeiden
- Codierte Namen lassen sich selten aus sprechen und können leicht falsch getippt werden.
- Ungarische Notation: Variablen mit Präfixe benennen, die ihren Typ bezeichnen.
- Es was früher nötig, denn damals führten Compiler keine Typ-Prüfungen durch. Deshalb brauchten Programmierer was ihnen half, die Typen zu erkennen und auseinanderzuhalten.

>[!tip]
>Der Unterschied zwischen einem schlauen Programmierer und einem professionellen Programmierer besteht darin, dass der professionelle P rogrammierer weiß, dass die Klarheit absoluten Vorrang hat.

## Klassen und Methodennamen
- Klassen und Objekte sollen Namen haben, die aus einem Substantiv bestehen.
- Methoden sollten Namen haben, die aus einem Verb bestehen.
- Wenn Konstruktor überladen werden, sollte die Factory Methoden mit einem Namen verwenden.

```java
ComplexfulcrumPoint = Complex.FromRealNumber(23.0)
// ist besser als
ComplexfulcrumPoint = new Complex(23.0)
```


## Keine Wortspiele
>[!tip]
>Sagen Sie, was Sie meinen. Meinen Sie, was Sie sagen.
- Humorige Namen vermeiden.
- Nicht dasselbe Wort für zwei Zwecke verwenden.
- Der Leser soll den Code schnell überfliegen können und nicht intensiv studieren müssen.

## Namen der Lösung und Problemdomäne verwenden
- Lösung und Problemdomäne auseinander trennen.
- Technische Namen für die Aufgaben zu wählen, ist normalerweise die angemessenste Vorgehensweise damit Entwicklern nicht diese mit dem Fachbegriffe der Informatik die sie kennen verwechseln.
- Der Code, der mehr mit Konzepten der Problemdomäne zu tun hat, sollte mehr Namen aus der Problemdomäne enthalten.

## Keinen überflüssigen Kontexthinzufügen
Kürzere Namen sind im allgemeinen besser als längere, solange sie klar sind. Also Namen sollen so Kurz wie möglich sein aber auch klar und die erforderliche Informationen liefern.