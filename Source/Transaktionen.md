Eine Transaktion ist eine Sequenz verwandter Anweisungen, die als eine unzertrennliche Einheit behandelt werden muss.

## Prinzip der Atomarität
- Threads dürfen nicht in die Transaktionen anderer Threads eingreifen.
- Bei einem Absturz sollte der Zustand vor Beginn der Transaktion wieder hergestellt werden und nicht der Zustand halb dazwischen.

**Beispiel**
```sql
START TRANSACTION;
	UPDATE account
		SET balance = balance - 1000
		WHERE number = 2;
	UPDATE account
		SET balance = balance + 1000
		WHERE number = 1;
COMMIT;

START TRANSACTION;
	UPDATE account
		SET balance = balance - 1000
		WHERE number = 2;
	UPDATE account
		SET balance = balance + 1000
		WHERE number = 1;
	SELECT balance
	FROM account
	WHERE number = 2;
COMMIT;
```

## READ and WRITE

- `WRITE` verhindert lesen und schreiben
- `READ` verhindert schreiben
```sql
LOCK TABLES account WRITE;
UNLOCK TABLES;
```
## ACID
- **A**tomicity **A**tomarität: Unteilbarkeit bzw. alle oder keine Änderungen.
- **C**onsistency **K**onsistenz: referentielle Integrität und keine falschen Zustände, wie z.B. halbe Überweisungen
- **I**solation **I**soliertheit: Transaktionen dürfen sich vor commit nicht gegenseitig beeinflussen
- **D**urability **D**auerhaftigkeit: Erst nach commit sind Auswirkungen dauerhaft. Davor muss auch bei Absturz, die Wiederherstellung des alten Zustands möglich sein.