## Transactions
In MariaDB and many other database systems, the `ROLLBACK` statement only rolls back data manipulation language [DML](Structured%20Query%20Language.md#Bestandteile) statements and not data definition language [DDL](Structured%20Query%20Language.md#Bestandteile) statements like table creation or alteration.

**Solution:**
```sql 
SAVEPOINT before; 
ROLLBACK TO before; 
```

## User Rights
#### Login
```bash
mysql -u user -p
```