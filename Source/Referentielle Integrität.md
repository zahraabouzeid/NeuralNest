## Erkennung von Parent und Child

- Die Tabelle mit dem Primärschlüssel, auf den in einer anderen Tabelle über einen Fremdschlüssel verwiesen wird, wird als "Parent" betrachtet.
- Die Tabelle, die den Fremdschlüssel enthält, ist das "Child".
- Beispiel: Für die Beziehung zwischen "Klasse" und "Schüler" jede Klasse mehrere Schüler haben könnte, sodass "Klasse" die übergeordnete Tabelle ist (die den Primärschlüssel enthält, möglicherweise die Klassen-ID) und "Schüler" die untergeordnete Tabelle (die einen Fremdschlüssel enthält, der sich auf die Klassen-ID bezieht).

## Löschung

- Die referentielle Integrität verhindert das Löschen eines Datensatzes in der Parent Tabelle, wenn es zugehörige Datensätze in der Child Tabelle gibt.
- Dies gewährleistet, dass keine referenziellen "Waisen" in der Datenbank verbleiben.

## Änderung

Die referentielle Integrität verhindert die Änderung des Primärschlüsselattributs in einem Datensatz der Parent Tabelle, wenn es zugehörige Datensätze in der Child Tabelle gibt.

## Einfügung

Die referentielle Integrität verhindert die Einfügen eines Datensatzes in der Child Tabelle, wenn es keinen zugehörigen Datensatz in der Parent Tabelle gibt.

## Datenkonsistenz und Referentielle Integrität

- Die referentielle Integrität gewährleistet Datenkonsistenz, insofern dass jeder Fremdschlüssel immer einen gültigen Wert enthält, d.h. ein entsprechender Datensatz in der parent-Tabelle existiert.
- Die referentielle Integrität trägt zur Datenkonsistenz bei, indem verhindert wird, dass es einen Fremdschlüsseleintrag gibt, der auf keinen gültigen Primärschlüsseleintrag verweist.

## ON DELETE CASCADE

Die Verwendung von **ON DELETE CASCADE** in SQL ermöglicht automatisches Löschen von zugehörigen Datensätzen in der Child-Tabelle, wenn der entsprechende Datensatz in der Parent-Tabelle gelöscht wird. Dies birgt jedoch die Gefahr von Datenverlust und sollte vorsichtig eingesetzt werden, um ungewollte Konsequenzen zu vermeiden.
