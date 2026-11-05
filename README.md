# Hotel Mini-Markt – Lager- und Verkaufsmanagement

> **Projektstatus:** Planung / Konzeptphase 🚧

Eine interne Webanwendung für den Mini-Markt in einer Hotellobby. Dort werden Getränke, Snacks, Süßigkeiten, Hygieneartikel und weitere Reise-Essentials verkauft. Die Anwendung soll Mitarbeiterinnen und Mitarbeitern helfen, Lagerbestände, Mindesthaltbarkeitsdaten, METRO-Einkäufe, Nachbestellungen sowie Einnahmen und Ausgaben übersichtlich zu verwalten.

## 🎯 Ziel

Weniger manuelle Bestandskontrollen, weniger abgelaufene Produkte und ein besserer Überblick über die Wirtschaftlichkeit des Mini-Markts.

Die Anwendung ist **kein öffentlicher Onlineshop**, sondern zunächst ein internes Tool für autorisierte Hotelmitarbeitende.

## ✨ Geplante Funktionen

### 1. Dashboard
- Aktueller Lagerbestand und wichtige Kennzahlen
- Warnungen bei niedrigen Beständen und bald ablaufenden Produkten
- Übersicht über Einkäufe, Verkäufe, Umsatz und Kosten
- Liste der Produkte, die nachgekauft werden sollten

### 2. Produkt- und Lagerverwaltung
- Produkte mit Name, Kategorie, Barcode/EAN, Einheit, Einkaufspreis und Verkaufspreis erfassen
- Lagerbestand und optional Verkaufsflächenbestand getrennt verwalten
- Mindestbestand und gewünschten Zielbestand pro Produkt definieren
- Wareneingänge, Verkäufe, Korrekturen und Verluste nachvollziehbar dokumentieren
- Chargen/Lieferungen mit unterschiedlichen Mindesthaltbarkeitsdaten verwalten
- Hinweise auf bald ablaufende Produkte (konfigurierbarer Zeitraum)

### 3. Einkauf und METRO-Rechnungen
- Einkäufe bei METRO erfassen und Belege archivieren
- Rechnungen als Foto oder PDF hochladen
- Artikel, Mengen und Einkaufspreise nach Möglichkeit automatisch erkennen
- Erkannte Positionen vor dem Speichern manuell prüfen und Produkten zuordnen
- Nach Bestätigung den Wareneingang verbuchen und die Einkaufskosten erfassen
- **Offen:** Prüfen, welche Daten der Code auf einer METRO-Rechnung tatsächlich enthält und ob eine geeignete Schnittstelle verfügbar ist. Das Scannen eines QR-/Barcodes garantiert nicht, dass sämtliche Rechnungspositionen ausgelesen werden können.

### 4. Kassensystem und Verkäufe
Die Produkte werden an einer Kasse in der Lobby gescannt und meist per Karte bezahlt.

- Prüfen, welches Kassensystem verwendet wird
- Falls möglich, Verkäufe per API oder Datei-Export importieren
- Produkte anhand ihrer Artikelnummern/Barcodes zuordnen
- Bestände nach erfassten Verkäufen reduzieren
- Als Alternative zunächst CSV-Import oder manuelle Verkaufserfassung ermöglichen
- Doppelimporte vermeiden und Korrekturen nachvollziehbar speichern

**Wichtig:** Kartenzahlungen allein liefern nicht unbedingt Informationen über die verkauften Einzelprodukte. Eine automatische Bestandsaktualisierung setzt geeignete Kassendaten voraus.

### 5. Finanzen und Auswertungen
- Einkaufsausgaben und Verkaufserlöse nach Zeitraum
- Umsatz nach Produkt und Kategorie
- Geschätzter Rohertrag: Verkaufserlöse minus zugehörige Wareneinsatzkosten
- Berücksichtigung von Retouren, Schwund und Korrekturen, soweit erfasst
- Unterschied zwischen Umsatz, Rohertrag und tatsächlichem Gewinn klar darstellen
- Steuer-/Bruttobeträge und Nettobeträge bei Bedarf getrennt ausweisen

### 6. Benutzerverwaltung
- Geschützter Login für Hotelmitarbeitende
- Rollen, z. B. Mitarbeitende und Administratoren
- Berechtigungen für Einkäufe, Bestandskorrekturen und Auswertungen
- Änderungsverlauf für wichtige Lagerbewegungen

## 🧰 Vorgeschlagener Tech-Stack

| Bereich | Technologie | Zweck |
| --- | --- | --- |
| Web-App | Next.js + TypeScript | Oberfläche und serverseitige Logik |
| Design | Tailwind CSS | Responsives UI |
| Datenbank | PostgreSQL (z. B. Supabase) | Produkte, Bestände, Einkäufe, Verkäufe |
| Authentifizierung | z. B. Supabase Auth | Sichere Mitarbeiterkonten |
| Versionskontrolle | Git + GitHub | Zusammenarbeit und Entwicklung |
| Deployment | Noch festzulegen | Sichere Bereitstellung |

Der Stack ist ein **Vorschlag** und wird vor der Implementierung festgelegt.

## 🗂️ Geplantes Datenmodell

- **products:** Produktstammdaten, Barcodes, Kategorien und Preise
- **stock_batches:** Lieferungen/Chargen, Mengen und Ablaufdaten
- **stock_movements:** Wareneingänge, Verkäufe, Korrekturen und Schwund
- **purchases / purchase_items:** METRO-Einkäufe und Rechnungspositionen
- **sales / sale_items:** Verkäufe und Artikelpositionen aus der Kasse
- **suppliers:** Lieferanten (zunächst METRO)
- **users / roles:** Benutzer und Zugriffsrechte

Bestände sollen aus nachvollziehbaren Bewegungen berechnet bzw. konsistent aktualisiert werden. Einkaufspreise können sich zwischen Lieferungen unterscheiden.

## 🛣️ Entwicklungsplan

- [ ] **Phase 1 – Anforderungen & Design**
  - [ ] Kassensystem identifizieren und Importmöglichkeiten prüfen
  - [ ] Produktkategorien, Lagerorte und Arbeitsabläufe klären
  - [ ] Wireframes für Dashboard, Produktliste und Produktdetails erstellen
  - [ ] Datenmodell und technische Architektur festlegen
- [ ] **Phase 2 – MVP: Lagerverwaltung**
  - [ ] Next.js-Projekt und Datenbank einrichten
  - [ ] Anmeldung und grundlegende Zugriffsrechte
  - [ ] Produkte anlegen, bearbeiten und suchen
  - [ ] Wareneingänge, Bestandskorrekturen und Chargen erfassen
  - [ ] Mindestbestands- und Ablaufwarnungen anzeigen
- [ ] **Phase 3 – Einkäufe & Verkäufe**
  - [ ] METRO-Einkäufe zunächst manuell erfassen
  - [ ] Verkäufe zunächst manuell oder per CSV importieren
  - [ ] Lagerbestände und einfache Umsatz-/Kostenberichte verknüpfen
- [ ] **Phase 4 – Automatisierung**
  - [ ] Rechnungs-PDFs/Fotos auslesen und Positionen prüfen
  - [ ] Kassenschnittstelle integrieren, falls technisch möglich
  - [ ] Nachbestellvorschläge und erweiterte Auswertungen ergänzen
- [ ] **Phase 5 – Test & Einführung**
  - [ ] Mit anonymisierten Beispieldaten testen
  - [ ] Mobile Ansicht und Bedienbarkeit prüfen
  - [ ] Datenschutz, Backups und Zugriffsrechte prüfen
  - [ ] Mit Zustimmung des Hotels bereitstellen und Mitarbeitende einweisen

### Erstes umsetzbares Ziel (MVP)

Eine nutzbare interne Website, auf der Mitarbeitende **Produkte erfassen, Lieferungen mit Ablaufdatum einbuchen, Bestände sehen und Nachbestellwarnungen erhalten**. Kassen- und Rechnungsautomatisierung folgen, sobald die technischen Möglichkeiten geklärt sind.

## ❓ Offene Fragen

1. Hersteller und Modell der Lobby-Kasse? Unterstützt sie API, CSV-/Excel-Export oder Verkaufsberichte pro Artikel?
2. Werden Waren nur im Lager oder zusätzlich in der Lobby-Auslage gezählt?
3. Wie viele Mitarbeitende benötigen Zugang und welche Rollen?
4. Wie viele unterschiedliche Produkte gibt es ungefähr?
5. Wie sehen METRO-Rechnungen aus (QR-/Barcode, PDF, Papier)?
6. Wie werden Schwund, abgelaufene Produkte, Retouren und Preisänderungen derzeit behandelt?
7. Welche Datenschutz-, IT- und Hosting-Vorgaben macht das Hotel?

## 🔒 Datenschutz & Sicherheit

- Keine echten Gäste-, Karten- oder Zahlungsdaten im Repository speichern.
- Zugangsdaten und API-Schlüssel nur über sichere Umgebungsvariablen verwalten.
- Produkt- und Finanzdaten nur berechtigten Mitarbeitenden zugänglich machen.
- Vor dem Einsatz im Hotel Freigabe, Datenschutz und IT-Vorgaben klären.
- Dieses Repository ist aktuell öffentlich: keine vertraulichen Hotelinformationen oder echten Belege hochladen.

## 📌 Status

Dieses README beschreibt die **geplanten Funktionen**. Die Anwendung ist noch nicht implementiert. Umfang und technische Details können sich während der Entwicklung ändern.
