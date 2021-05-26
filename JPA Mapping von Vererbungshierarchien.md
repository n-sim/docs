# JPA Mapping von Vererbungshierarchien
## Strategien
**Single Table**
- Tabelle pro Vererbungshierarchie
- Alle Attribute von Basis- und Abgeleiteten-Klasse in eine gemeinsame Tabelle
- Zusätzliche Spalte (Diskriminator) legt welcher Klasse eine Zeile angehört
- Viele NULL-Werte (kein Not-Null)

**Joined**
- Tabelle pro Unterklasse
- Für *jede* Klasse wird eine eigene Tabelle angelegt
- Attribute der Basisklasse/tabelle sind in abgeleiteten Tabelle nicht vorhanden (stattdessen 1:1 Beziehung)
- Kein Diskriminator benötigt

**Table per Class**
- Tabelle pro konkreter Klasse
- Attribute der Basisklasse werden in die Tabellen der Unterklassen mit aufgenommen (keine Basisklassen-Tabelle)
- Nicht möglich mit einer Abfrage, Instanzen verschiedener Klassen abzufragen