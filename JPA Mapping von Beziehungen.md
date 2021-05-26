# JPA Mapping von Beziehungen

## Kardinalitäten
- Unidirektional (1:1): Fremdschlüssel in Tabelle
- Bidirektional (1:1): Fremdschlüssel in Tabelle der Owning-Seite
- Unidirektional (1:n): Verbindungstabelle
- Unidirektional (n:1): Fremdschlüssel in Tabelle
- Bidirektional (1:n / n:1): Fremdschlüssel in Tabelle der Owning-Seite
- Unidirektional (m:n): Verbindungstabelle
- Bidirektional (m:n): Verbindungstabelle
## Unidirektionales / Bidirektionales Mapping
**Bidirektionales Mapping**
- Im Objektmodell gibt es auf beiden Seiten eine Referenz (Attribute in beiden Klassen)
- Eine Entität kann auf die andere schließen und umgekehrt

**Unidirektionales Mapping**
- Im Objektmodell gibt es nur auf einer Seite eine Referenz (Attribut nur in einer Klasse)
- Eine Entität kann auf die andere schließen aber NICHT umgekehrt

## Owning-Seite
- Ist für persistierung Zuständig
- Besitzt kein `mappedBy`
- Kann (im Gegensatz zur nicht-owning-Seite) assoziierten Entitäten speichern