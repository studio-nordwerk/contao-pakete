# Mini-Shop: Was ist neu?

## Nächste Version (in Arbeit)

**Neu**
- Produktbilder lassen sich groß ansehen (Bildergalerie mit Lightbox), und der Warenkorb öffnet sich als Seitenleiste. Das funktioniert, wenn die kostenlosen Bundles Galerie und Sheet installiert sind.
- Zahlung per Überweisung mit Bankdaten und GiroCode zum Scannen, dazu eine automatische Zahlungserinnerung.
- Die Bestätigungsseite zeigt den Status der Bestellung und die Zahlart.

**Verbessert**
- Die Bestätigungsmail enthält den vollständigen Vertragsinhalt.
- Fehlermeldungen in der Kasse sind auch mit Screenreader gut erreichbar.

**Behoben**
- Der Lagerbestand stimmt jetzt auch dann, wenn ein Produkt umbenannt oder ersetzt wurde.
- Ein entferntes Produkt kann nicht mehr bestellt werden, auch wenn es noch im Warenkorb lag.
- Wer zweimal auf „Bestellen“ klickt oder in zwei Tabs bestellt, bekommt keine doppelte Bestellung.
- Erstattungen und Stornos rechnen die Umsatzsteuer korrekt, auch bei mehreren Teilerstattungen.
- Rechnungen werden bei einem zweiten Versuch nicht doppelt oder mit anderen Daten erstellt.

## 0.1.1 vom 30. September 2026

**Behoben**
- Die Installation brach bei älteren Contao-5.7-Versionen ab. Der Shop verlangt jetzt Contao 5.7.12 oder neuer. Bitte vor der Installation im Contao Manager alle Pakete aktualisieren.

## 0.1.0 vom 29. September 2026

Erste Version.
- Einrichtungsassistent im Contao-Backend, in etwa zehn Minuten startklar, mit Startklar-Check
- Produkte mit Bildern, optionalem Lagerbestand und Grundpreis pro Kilogramm oder Liter
- Warenkorb und Kasse ohne Kundenkonto, Versand und Abholung
- Vorkasse per Überweisung
- Pflichtangaben vor dem Button „zahlungspflichtig bestellen“ und der EU-Hinweis zur Gewährleistung
- Bestellmails an Kundschaft und Shop, Bestellübersicht im Backend
- Rechnungen als PDF mit fortlaufender Nummer, auf Wunsch
- Anbindung an den Widerrufsbutton
- Demo „Seifenwerk Anna Muster“ und eine optionale Grundgestaltung
