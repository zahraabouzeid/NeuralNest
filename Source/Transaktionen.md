Eine Transaktion ist eine Sequenz verwandter Anweisungen, die als eine unzertrennliche Einheit behandelt werden muss.

## ACID
- **Atomicity** (Atomarität): Unteilbarkeit bzw. alle oder keine Änderungen.
- **Consistency** (Konsistenz): referentielle Integrität und keine falschen Zustände, wie z.B. halbe Überweisungen
- **Isolation** (Isoliertheit): Transaktionen dürfen sich vor commit nicht gegenseitig beeinflussen
- **Durability** (Dauerhaftigkeit): Erst nach commit sind Auswirkungen dauerhaft. Davor muss auch bei Absturz, die Wiederherstellung des alten Zustands möglich sein.

## Prinzip der Atomarität
- Threads dürfen nicht in die Transaktionen anderer Threads eingreifen.
- Bei einem Absturz sollte der Zustand vor Beginn der Transaktion wieder hergestellt werden und nicht der Zustand halb dazwischen.

## Transaction erstellen
```sql
START TRANSACTION;
COMMIT | ROLLBACK;
```

## Lesen und Schreiben

- `WRITE` verhindert lesen und schreiben
- `READ` verhindert schreiben
```sql
LOCK TABLES Tabellenname WRITE;
UNLOCK TABLES;
```
