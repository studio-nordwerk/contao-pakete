# Mini-Shop: Was ist neu?

## 0.4.2 vom 2. Oktober 2026

**Verbessert**
- Produktliste, Produktseite, Warenkorb, Kasse und das Warenkorb-Modul haben jetzt CSS-ID/Klasse und Template-Auswahl sowie Sichtbarkeitseinstellungen wie normale Contao-Elemente. So lassen sich Varianten aus dem Theme ohne Template-Änderung zuweisen.

## 0.4.1 vom 2. Oktober 2026

**Verbessert**
- Die Bestellmail ist neu aufgebaut, wie in modernen Shops: oben Dank, ein Button „Bestellung ansehen“ und bei Vorkasse ein Kasten mit Betrag, IBAN, Verwendungszweck, Fälligkeit und GiroCode. Darunter die Produkte als kompakte Zeilen mit Bild, Größe und Preis, die Summen und die Bestelldetails. Die Pflichttexte (wesentliche Merkmale, Widerrufsbelehrung, Muster-Formular, AGB, Gewährleistung) stehen klein am Ende, deine Anbieterangaben als Fußzeile.
- Zahlungserinnerung, Zahlungseingang, Versand und Storno nutzen denselben Aufbau.
- Die Mail an dich selbst begrüßt nicht mehr die Kundin, sondern nennt sie: „Neue Bestellung von …“, mit Link direkt zur Bestellung im Backend.
- Kategorien haben einen eigenen Menüpunkt „Kategorien“ unter Inhalte, gleich neben „Produkte“.
- Die Einrichtung warnt, wenn im Muster-Widerrufsformular noch ein Platzhalter wie „[Firmenname … einfügen]“ steht.

**Behoben**
- Klammern aus den Rechtstexten erscheinen in Mails nicht mehr als „&#40;“.
- Die Rechtsform steht nicht mehr als interner Wert („sole“) in der Mail, leere Angaben erzeugen keine Leerzeilen mehr.

**Nach dem Update:** Im Contao Manager den Prod-Cache leeren und neu erzeugen. Das Widerruf-Bundle wird dabei auf 1.1 aktualisiert.

## 0.4.0 vom 2. Oktober 2026

**Neu**
- Produktlisten als Karussell: Im Produktlisten-Element wählst du unter „Darstellung“ zwischen Raster und Karussell. Das Karussell zeigt die Produkte nebeneinander zum Wischen, ideal für „Neu im Shop“ auf der Startseite und auf dem Handy. Es nutzt unser kostenloses Karussell-Bundle; ist es nicht installiert, erscheint wie bisher das Raster.

**Verbessert**
- Der Warenkorb arbeitet ruhiger und verlässlicher: Jede Änderung (Plus, Minus, Menge, Entfernen) wird sofort gespeichert. Während der Shop kurz speichert, halten alle Bedienelemente still, danach zeigt der Warenkorb den gespeicherten Stand. Doppelte oder verschluckte Klicks gibt es nicht mehr, und die Warenkorbseite lädt dabei nicht mehr komplett neu.
- Vier Produkte im Raster stehen auf mittelgroßen Bildschirmen zwei mal zwei statt drei plus eins.
- Produktnamen in Listen unter einer Zwischenüberschrift wie „Neu im Shop“ haben die passende Überschriftenebene, das hilft Screenreadern und Suchmaschinen.

**Nach dem Update:** Im Contao Manager unter Systemwartung die Datenbank aktualisieren (neues Feld „Darstellung“) und den Prod-Cache leeren und neu erzeugen. Für das Karussell zusätzlich `nordwerk/contao-carousel-bundle` installieren.

## 0.3.0 vom 2. Oktober 2026

**Neu**
- Eine neue, ruhigere Shop-Oberfläche: Produktkarten mit großem Bild, Produktseite mit Kaufbereich, Mengenwähler und aufklappbaren Abschnitten, Warenkorb mit Fortschritt bis zum kostenlosen Versand, Kasse in drei Schritten (Warenkorb, Angaben, Prüfen) und eine übersichtliche Bestätigung.
- Eigene Seiten für Warenkorb und Kasse mit verständlichen Adressen wie `/warenkorb`, `/kasse`, `/kasse/pruefen` und `/kasse/danke`. Jedes Produkt hat eine feste Adresse unter deiner Shop-Seite, zum Beispiel `/shop/lavendelseife`. Im Assistenten legst du die Seiten mit „Seiten anlegen“ an.
- Kategorien: Produkte in Kategorien wie „Seifen“ oder „Pflege“ einteilen und auf normalen Contao-Seiten zeigen. Reihenfolge („Neueste zuerst“, Preis, manuell) und Anzahl stellst du im Produktlisten-Element ein, zum Beispiel für „Neu im Shop“ auf der Startseite.
- Drei Kartenstile im Produktlisten-Element: Katalog (Standard), mit Button oder mit Plus-Symbol auf dem Bild.
- Brotkrümel auf Produkt- und Kategorieseiten, wenn du das Contao-Modul einbindest.

**Verbessert**
- In der Bestellprüfung stehen Waren, wesentliche Merkmale und Gesamtpreis direkt über „Zahlungspflichtig bestellen“.
- Der Grundpreis steht jetzt auch im Warenkorb, in der Kassenübersicht und in der Bestellprüfung.
- Wählst du an der Kasse Abholung, rechnet die Übersicht sofort ohne Versandkosten.
- Das Warenkorb-Symbol springt beim Seitenwechsel nicht mehr, die Anzahl bleibt stehen.
- Mengenänderungen im Warenkorb speichern sich selbst, und „Zur Kasse“ übernimmt geänderte Mengen auch ohne JavaScript.
- Eingabefelder und leise Texte haben mehr Kontrast und sind besser lesbar.
- Wenn die Einrichtung noch unvollständig ist, nimmt der Shop freundlich keine Bestellungen an und zeigt dir im Backend, was fehlt, statt einer Fehlerseite.

**Behoben**
- Die Eingabetaste im Mengenfeld entfernt keinen Artikel mehr aus dem Warenkorb.
- „Entfernen“ funktioniert auch, wenn ein anderes Mengenfeld leer ist.
- Ohne eingetragene Lieferzeit erscheint kein leeres „Lieferzeit: .“ mehr.

**Nach dem Update:** Dein Shop funktioniert ohne neue Einrichtung weiter, alte Warenkorb- und Kassenlinks leiten automatisch um. Im Contao Manager unter Systemwartung den Prod-Cache leeren und neu erzeugen. Hast du eigene Vorlagen im Template Studio überschrieben, sieh sie dir einmal an: Die neue Oberfläche bringt neue Vorlagen mit.

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
