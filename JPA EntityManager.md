# JPA EntityManager
## Zustände von Entitäten
- Transient:
	- Mit `new` erzeugt, oder mit `remove()` aus DB entfernt
	- (Noch) keine Repräsentation in der DB
- Persitent:
	- Durch `persist()`, `merge()`, `find()`
	- PK schon gesetzt, aber erst mit commit/flush wird Objekt mit DB abgeglichen
- Detached:
	- `detatch()`
	- Vom Persistenzkontext gelöst, hat aber DB-Eintrag und ID

![[Pasted image 20210525190010.png]]

## Wichtige Methoden
**Persist**
```java
public void persist(Object entity)
```

- Nimmt transientes Objekt in Persistenzkontext auf (fall bereits aufgenommen: Methodenaufruf ignoriert)
- Autogenerierter PK wird zugewiesen

**Remove**
```java
public void remove(Object entity)
```

- Markiert Objekt zum Löschen aus DB
- Wird detached-Entity übergeben -> IllegalArgumentException

**Merge**
```java
public <T> T merge(T entity)
```

- Kopiert Zustand des Objekts in persistente Objekt mit gleicher ID 
	- Wenn keines exisitiert: Versuch aus DB zu laden
	- Wenn nicht in DB gefunden: Neu angelegt und retourniert
- Das übergebene Objekt `entity` wird nicht persistiert

**Find**
```java
public <T> T find(Class<T> entityClass, Object id)
```

- Läd das Objekt der angegebenen Klasse `entityClass` und ID `id` aus der DB
- Wenn ein Objekt mit gesuchter ID im Persistenzkontext existiert: retourniert dieses Objekt
- Wenn nicht exisiert: retourniert `null`