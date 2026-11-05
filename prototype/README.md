# LobbyStock – Interaktiver Prototyp

Dieser Ordner enthält einen ersten klickbaren **Frontend-Prototyp** für die geplante Hotel-Mini-Markt-Anwendung.

## Starten

1. Die Datei [index.html](./index.html) herunterladen oder das Repository klonen.
2. `prototype/index.html` per Doppelklick im Browser öffnen.
3. Dashboard, Produkte, METRO-Einkäufe, Verkäufe und Auswertungen ausprobieren.

Es sind **keine Installation und kein Server** nötig.

## Was funktioniert bereits?

- Responsives Dashboard mit Kennzahlen
- Produktliste mit Suche und Filtern
- Warnungen bei niedrigen Beständen und nahenden Ablaufdaten
- Neue Produkte hinzufügen
- Wareneingänge manuell erfassen
- Verkäufe simulieren (Bestand wird reduziert)
- Einfache Umsatz-/Kostenübersicht und Diagramm
- Speicherung der Demo-Änderungen im Browser per `localStorage`

## Was ist noch nicht implementiert?

- Echte Datenbank und Login
- Anbindung an das Kassensystem
- Automatisches Auslesen von METRO-Rechnungen
- Zuverlässige Chargen-/Ablaufdatumsverwaltung je Lieferung
- Buchhalterisch korrekte Gewinnberechnung
- Gemeinsame Datenhaltung für mehrere Mitarbeiter

**Achtung:** Alle Produkt- und Finanzwerte sind frei erfundene Beispieldaten. Die Änderungen sind nur im jeweiligen Browser gespeichert und können beim Löschen der Browserdaten verloren gehen. Nicht für den produktiven Hotelbetrieb verwenden.

## Nächster Schritt

Den Prototyp gemeinsam durchgehen, Design und Abläufe abstimmen und dann eine echte Next.js-/TypeScript-Anwendung mit PostgreSQL/Supabase entwickeln.
