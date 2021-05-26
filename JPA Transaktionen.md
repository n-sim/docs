# JPA Transaktionen
Jeder Application-managed EntityManager verwaltet genau eine Transaktion

## Wichtige Methoden
**Transaktion erhalten:**

```java
public EntityTransaction getTransaction()
```
IllegalStateException wenn JTA-EntityManager

**Transaktion beginnen:**
```java
public void begin()
```
IllegalStateException wenn Transaktion bereits aktiv

**Commitieren**:
```java
public void commit()
```
RollbackException wenn Transaktion zurück gerollt wird

**Rollback**:
```java
public void rollback()
```



