# Mini-Shop: Was ist neu?

## Nächste Version (in Arbeit)

- Wenn die Einrichtung noch unvollständig ist, nimmt der Shop freundlich keine Bestellungen an und zeigt dir im Backend, was fehlt, statt einer Fehlerseite.

## 0.2.0 vom 1. Oktober 2026

**Neu**
- Steuerstatus bewusst wählen: Im Assistenten entscheidest du ausdrücklich zwischen „Ich weise Umsatzsteuer aus“ und „Kleinunternehmer nach § 19 UStG“ und siehst gleich, wie ein Preis danach im Shop aussieht.
- Produktbilder lassen sich groß ansehen (Bildergalerie mit Lightbox), und der Warenkorb öffnet sich als Seitenleiste, wenn die kostenlosen Bundles Galerie und Sheet installiert sind.
- Zahlung per Überweisung mit Bankdaten und GiroCode zum Scannen, dazu eine automatische Zahlungserinnerung. Dafür wird das kostenlose Zahlungs-Bundle 1.0 mitinstalliert.
- Die Bestätigungsseite zeigt den Status der Bestellung und die Zahlart.

**Verbessert**
- Die Produktübersicht zeigt kompakte, gleich hohe Karten: Titel, kurzer Text, Preis, Grundpreis und Button. Inhaltsstoffe und lange Beschreibungen stehen auf der Produktseite.
- Texte aus dem Editor werden mit ihrer Formatierung angezeigt, und Zeilenumbrüche in einfachen Textfeldern bleiben erhalten.
- Der Button „In den Warenkorb“ bleibt auch mit eigenen Themes gut lesbar.
- Fehlt in der Einrichtung etwas (zum Beispiel IBAN oder Datenschutzseite), erklärt die Kasse das auf Deutsch, statt mit einer Fehlerseite abzubrechen.
- Der Startklar-Check erkennt, wenn kein Mailversand eingerichtet ist.
- Hat dein Hoster keine Rechte für Datenbank-Trigger freigegeben, sagt dir die Installation genau, was er freischalten muss.
- Die Bestätigungsmail enthält den vollständigen Vertragsinhalt.

**Behoben**
- Eine unveröffentlichte Datenschutzseite verhindert jetzt Bestellungen, bis sie veröffentlicht ist.
- Der Lagerbestand stimmt auch dann, wenn ein Produkt umbenannt oder ersetzt wurde.
- Ein entferntes Produkt kann nicht mehr bestellt werden, auch wenn es noch im Warenkorb lag.
- Wer zweimal auf „Bestellen“ klickt oder in zwei Tabs bestellt, bekommt keine doppelte Bestellung.
- Erstattungen und Stornos rechnen die Umsatzsteuer korrekt, auch bei mehreren Teilerstattungen.

**Tipp nach dem Update:** Im Contao Manager unter Systemwartung den Prod-Cache leeren und neu erzeugen.

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
