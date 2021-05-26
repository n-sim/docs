# JPA JPQL
Eine Abfragesprache, mit der man ausschließlich Entitäten (gemappte Java-Klassen) abfragen kann

## Eigenschaften
- Case-sensitive
- Auf Java-Namen bezogen
- Abfragen können nur über aktiven EntityManger ausgeführt werden
- Vor der Ausführung: Persistenzkontext geflusht

## Abfragen
**Erzeugung:**
```java
em.createQuery("select a from Address a");
```

**Erzeugung typisierte Queries:**
```java
em.createQuery("select a from Address a", Adresse.class);
```

**Erzeugung Named Queries:**
```java
@NamedQuery(name = "Book.findByISBN", query = "select b from Book b where b.isbn = :isbn")
public class Dozent implements Serializable{...}

Query qu = em.createNamedQuery("Book.findByISBN");
```

**Ergebnisabfrage:**
```java
query.getResultList(); //Resultat: Mehrere Werte
query.getSingleResult(); //Resultat: Nur 1 Wert
```

**Parameter:**
```java
Query query = em.createQuery("select a from Address a where a.zip = :zip"); 
query.setParameter("zip", zip);
```



