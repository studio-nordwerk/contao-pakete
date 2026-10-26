# Mini-Shop: Was ist neu?

Jeder Eintrag nennt unter „Templates geändert“ die Templates, die sich mit der Version geändert haben. Hast du eines davon im Template Studio überschrieben, hat deine Fassung Vorrang. Vergleiche sie dann mit dem neuen Original.

## 0.7.0 vom 26. Oktober 2026

**Neu**
- Shop-Einstellungen: Unter Inhalte → Shop-Einstellungen bearbeitest du alle Einstellungen im gewohnten Contao-Formular, mit Versionen, Feldrechten und denselben Prüfungen wie im Assistenten. Der Assistent „Shop einrichten“ bleibt und schreibt dieselben Einstellungen.
- Shop-Seiten am Startpunkt: Im Startpunkt der Website wählst du unter „Mini-Shop“ die Shop-Seiten (Shop, Warenkorb, Kasse und so weiter) für genau diese Website. Mehrere Websites in einer Installation brauchen so keine Umwege mehr.
- Bestellungen als Contao-Liste: Inhalte → Bestellungen hat Filter (Status, Monat), Suche (Bestellnummer, Name, E-Mail), Sortierung und eine Detailansicht. Name, E-Mail und Summe stehen in der Liste. „Bestellung verwalten“ öffnet wie bisher die Aktionen; Links aus bereits verschickten Mails funktionieren weiter.
- Produkte: Ein Augen-Symbol veröffentlicht oder verbirgt ein Produkt direkt in der Liste, ebenso bei Kategorien. „Anzeigen ab/bis“ beachten Shop, Sitemap, Weiterleitung und Bestandsreservierung.
- Suchmaschinen: Produkte haben den Abschnitt „Suchmaschinen“ mit Seitentitel, Beschreibung und Robots-Angabe, samt Vorschau. Produktseiten stehen je Startpunkt in der `sitemap.xml`, geschützte Seiten sowie Seiten und Produkte mit „noindex“ nicht.
- Das Produktlisten-Element hat das Standardfeld „Bildgröße“. Ohne Auswahl bleibt es bei der bisherigen Kartengröße.
- Die Oberfläche des Assistenten, der Bestellansicht, des Mail-Editors und der Produkt- und Kategorieverwaltung gibt es auf Deutsch und Englisch.

**Verbessert**
- Der Seitencache aktualisiert Produktlisten und Produktseiten gezielt, wenn du Produkte, Kategorien oder Einstellungen speicherst, umschaltest oder löschst. Auch Bestandsänderungen durch Bestellungen und Stornos wirken sofort. Erreicht „Anzeigen ab/bis“ eines Produkts seinen Zeitpunkt, zeigt der Seitencache den alten Stand bis zum Ablauf der Cache-Zeit.
- Stylesheets und Skripte des Shops werden nur noch einmal pro Seite im Seitenkopf bzw. am Seitenende eingebunden. Das Warenkorb-Fragment enthält keine eigenen Link-Tags mehr; das Mini-Warenkorb-Modul bindet die Styles ein.
- Der Seitenmodus berücksichtigt „Unsichtbar“ und „Anzeigen ab/bis“ des Elements sowie die Veröffentlichung des Artikels. Der Startklar-Check warnt, wenn auf einer Seite verschiedene Shop-Elemente gemischt sind.
- Der Assistent bietet nur Seiten an, die in deiner Seitenverwaltung freigegeben sind (Seitenfreigaben deines Kontos), und legt Seiten, Artikel und Elemente nur an, wenn deine Rechte in der Seitenstruktur es erlauben.
- Die Überschriftenebenen h5 und h6 der Produktliste werden übernommen.
- Bezahlung bei Abholung stellen im Assistenten Administratoren und Benutzer mit dem Recht „Zahlung einrichten“ ein.

**Behoben**
- Im Mail-Editor ließen sich Absender und Akzentfarbe nicht speichern: Das Zeichen `#` (Hex-Farben) und `&` wurden umkodiert. Das funktioniert jetzt.

**Templates geändert:** `_buy_box`, `_cart`, `_cart_fragment`, `_checkout_form`, `_gallery`, `_product_card`, `_product_list`, `mini_shop_product_list`, `mini_shop_cart`, `_mini_shop_cart_sheet`. Hast du eines davon im Template Studio überschrieben, vergleiche deine Fassung mit dem neuen Original. Überschreibungen mit eigenen `<link>`- oder `<script>`-Tags im Body stellst du am besten auf `{% add 'mini_shop_…' to head|body %}` um. Überschreibt deine `_product_card` die Bildgröße fest mit `_mini_shop_card`, funktioniert sie weiter, ignoriert aber die im Element gewählte Größe.

**Nach dem Update:** Mini-Shop 0.7.0 nur zusammen mit dem Payment-Bundle 1.2.0 hochladen: Payment 1.2.0 verweigert ältere Mini-Shops. Den Widerrufsbutton 1.2.0 am besten gleich mit aktualisieren. Danach im Contao Manager die Datenbank aktualisieren und den Prod-Cache leeren. Zwischen dem Hochladen und der Datenbankaktualisierung ist das Frontend nicht nutzbar, weil neue Spalten fehlen; spiele beides also direkt nacheinander ein. Deine bisherige Einrichtung wird vollständig übernommen, einschließlich der Shop-Seiten (sie stehen danach am Startpunkt), des Rechnungspräfixes und der Bestellungen. Du musst nichts neu einrichten. Prüfe nach dem Update kurz die Startklar-Anzeige.

**Neue Rechte:** Das Formular „Shop-Einstellungen“ nutzt Contaos Tabellen- und Feldrechte. Die Migration gibt Benutzergruppen und Benutzern mit eigenen Rechten, die „Shop einrichten“ haben, einmalig „Shop-Einstellungen“ und „Shop-Mails“ samt Feld- und Tabellenrechten. Halter von „Produkte“ bekommen einmalig die neuen Felder für Suchmaschinen und „Anzeigen ab/bis“. Entziehst du später ein Recht, bleibt es entzogen. Neu angelegte Gruppen bekommen die Rechte wie in Contao üblich von dir. Die Bezahlung bei Abholung im Assistenten ist nicht mit diesen Rechten gekoppelt, sondern mit „Zahlung einrichten“; gib dieses Modul den Gruppen frei, die sie schalten sollen (siehe Payment 1.2.0). Solange auf den Shop-Einstellungen kein Feldrecht vergeben ist, zeigt der Assistent alle Felder.

## 0.6.0 vom 23. Oktober 2026

**Neu**
- Bezahlung bei Abholung: In Schritt 6 des Assistenten „Bezahlung bei Abholung anbieten (bar oder PayPal)“ einschalten. Die Zahlart erscheint an der Kasse nur zusammen mit Abholung; bei Versand ist sie ausgegraut. Die Bestellung zeigt „Wird bei Abholung bezahlt“ und bekommt keine Zahlungserinnerung. Beim Abholen setzt du sie in der Bestellverwaltung auf „Zahlung eingegangen“ und dann auf „Abgeholt“.
- PayPal per QR-Code: Mit einem PayPal.me-Link (zum Beispiel `paypal.me/hofladen`) zeigen Danke-Seite und Bestellmail einen QR-Code und einen Link, in denen der Betrag schon steht.
- Eigener Abholungstext: In Schritt 5 trägst du ein, wann und wo abgeholt wird, etwa „Fr + Sa 9–18 Uhr im Hofladen“. Der Text steht an der Kasse, in der Bestellprüfung und in der Mail. Ohne Text steht wie bisher „nach Absprache“.
- Mengen ab 1000 g, 1000 ml und 100 cm stehen in kg, l und m: 5000 g erscheint als „5 kg“.

**Behoben**
- Der Contao Manager meldete bei einer frischen Installation „funktioniert nicht mit Contao 5.7.*“ und sperrte den Upload, obwohl die Pakete ab Contao 5.7.12 laufen. Die Pakete verlangen jetzt Contao 5.7 und schließen ältere Versionen als 5.7.12 auf anderem Weg aus; die Meldung erscheint nicht mehr. Bei älteren Paketversionen hilft: beim Contao-Paket über das Zahnrad die Versionsbedingung auf `~5.7.12` stellen.
- Bietet der Shop Abholung an, zeigt der Warenkorb „Versand oder Abholung: Wahl an der Kasse“ statt Versandkosten und Gesamtpreis mit Versand.
- Bei Abholung stehen in Bestellübersicht und Mail keine Lieferzeit mehr und kein „Wir versenden, sobald die Zahlung eingegangen ist“, sondern „Wir legen Ihre Bestellung zur Abholung bereit“.

**Templates geändert:** `_cart`, `_checkout_form`, `_order_review`, `_mandatory_information`, `_confirmation`, `_info_accordion`. Hast du eines davon im Template Studio überschrieben, vergleiche deine Fassung mit dem neuen Original.

**Nach dem Update:** Mini-Shop 0.6.0 zusammen mit dem Payment-Bundle 1.1.0 hochladen (und dem Widerrufsbutton 1.1.1, wenn du ihn ebenfalls aktualisierst). Danach im Contao Manager den Prod-Cache leeren. Eine Datenbankänderung gibt es nicht.

## 0.5.0 vom 23. Oktober 2026

**Neu**
- Produktarten: Am Produkt wählst du die Art, etwa Kosmetik, Lebensmittel, Kerzen, Textilien, Keramik/Deko, Schmuck oder Stoffe. Die Art bestimmt, welche Angaben das Produkt abfragt und zeigt, zum Beispiel Inhaltsstoffe, Zutaten und Nährwerte, Material, Maße, Pflege oder Sicherheitshinweise.
- Mengen in g, kg, ml, l, cm, m, m² oder Stück, mit Grundpreis je kg, l, m oder m², wo die Preisangabenverordnung ihn verlangt. „Pro Stück“ aus 0.4.6 ist jetzt die Einheit „Stück“.
- Hersteller und Produktsicherheit: Name, Anschrift und E-Mail des Herstellers sowie Warn- und Sicherheitshinweise stehen auf der Produktseite. Ohne eigene Angabe nennt der Shop dich als Verkäufer.

**Templates geändert:** `_buy_box`, `_info_accordion`, `_order_summary`.

**Nach dem Update:** Im Contao Manager die Datenbank aktualisieren und den Prod-Cache leeren. Bestehende Produkte bekommen eine Produktart (nach Füllmenge „Kosmetik und Pflege“, pro Stück „Keramik, Kunst und Deko“); bitte die Produktart in jedem Produkt prüfen.

## 0.4.6 vom 16. Oktober 2026

**Neu**
- Verkauf pro Stück: Am Produkt wählst du unter „Verkauf“ zwischen „Nach Füllmenge (mit Grundpreis)“ und „Pro Stück (ohne Grundpreis)“. Pro Stück verschwinden Nettofüllmenge, Einheit und Grundpreis, etwa für Keramik, Bilder, Deko oder Schmuck. Das Feld „Inhaltsstoffe“ heißt dann „Material“ und ist optional. Auf der Produktseite, in der Bestellübersicht und in den Mails steht „Material: …“.
- Anfertigung auf Bestellung: Unter „Verfügbarkeit“ wählst du „Auf Lager“ (mit Bestand wie bisher) oder „Auf Bestellung angefertigt“ mit einer eigenen Lieferzeit, zum Beispiel „ca. 3 Wochen“. Das Produkt ist immer bestellbar und zieht keinen Bestand ab. Karte, Produktseite, Warenkorb, Kasse, Bestellübersicht vor dem Bestellknopf, Bestellbestätigung und die Bestellansicht im Backend zeigen „Wird nach Bestellung angefertigt, Lieferzeit ca. 3 Wochen“. Stehen auch Produkte vom Lager im Warenkorb, gilt für sie weiter die Lieferzeit des Shops.
- Templates: `detail.soldByPiece`, `detail.madeToOrder` und `detail.deliveryTime` (auf der Karte `product.madeToOrder` und `product.deliveryTime`).

**Templates geändert:** `_buy_box`, `_product_card`, `_info_accordion`, `_cart`, `_checkout_form`, `_order_summary`, `_mandatory_information`. Hast du eines davon im Template Studio überschrieben, vergleiche deine Fassung mit dem neuen Original.

**Nach dem Update:** Im Contao Manager die Datenbank aktualisieren (neue Felder „Verkauf“, „Verfügbarkeit“ und „Lieferzeit“) und den Prod-Cache leeren. Bestehende Produkte bleiben „Nach Füllmenge“ und „Auf Lager“. Voraussetzung ist der Widerrufsbutton ab 1.1, siehe 0.4.1.

## 0.4.5 vom 14. Oktober 2026

**Neu**
- Unterkategorien: Eine Kategorie bekommt eine „Übergeordnete Kategorie“, etwa Seifen › Olivenseifen. Eine Produktliste mit „Seifen“ zeigt die Produkte aller Unterkategorien automatisch mit. In allen Auswahllisten steht der ganze Pfad.
- Produktliste: „Kurzbeschreibung anzeigen“ blendet die Kurzbeschreibung unter dem Produktnamen ein, ohne Template-Änderung.
- Produktliste: „Text bei leerer Liste“, zum Beispiel „Hier kommen bald neue Produkte“. Ohne eigenen Text steht dort „Hier sind noch keine Produkte.“
- Produktverwaltung: Im Filter-Feld lässt sich nach Kategorie und Veröffentlichung filtern, und die Kategorien stehen in der Liste neben Preis und Bestand.
- Templates: `detail.categories` (Produktseite) und `product.categories` (Karte) enthalten alle Kategorien des Produkts mit `id`, `name` und `alias`, zum Beispiel `{% if 'seifen' in detail.categories|column('alias') %}`.
- Startklar-Check und `mini-shop:doctor` melden Produktbilder unter 1400 Pixel. Empfohlen: quadratisch, mindestens 1400 × 1400 Pixel, Motiv mittig.
- Anleitung „In ein bestehendes Theme einbauen“ mit den CSS-Variablen für Akzentfarbe, Ecken, Linien, Kartenschatten, Bildformat und Abstände (neu: `--mini-shop-card-ratio`, `--mini-shop-card-shadow`, `--mini-shop-grid-gap`).

**Behoben**
- Eine Produktliste ohne eigene Überschrift gibt kein leeres `<h2></h2>` mehr aus.
- Produktbilder in der Übersicht: Die Karte schnitt die Bilder erst auf 4:3 und zeigte sie dann quadratisch, dadurch fehlte bei quadratischen Fotos oben und unten etwas. Die Karte nutzt jetzt einen quadratischen Ausschnitt.

**Templates geändert:** `_product_card`, `_product_list`. Hast du eines davon im Template Studio überschrieben, vergleiche deine Fassung mit dem neuen Original.

**Nach dem Update:** Im Contao Manager die Datenbank aktualisieren (neue Felder für Unterkategorie, Kurzbeschreibung und Leertext) und den Prod-Cache leeren. Voraussetzung ist der Widerrufsbutton ab 1.1, siehe 0.4.1.

## 0.4.4 vom 5. Oktober 2026

**Verbessert**
- Eigene Gruppe „Mini-Shop“: Produktliste, Produkt, Warenkorb und Kasse stehen in der Auswahl der Inhaltselemente nicht mehr unter „Text-Elemente“, der Mini-Warenkorb bei den Frontend-Modulen nicht mehr unter „Verschiedenes“. Bestehende Elemente bleiben unverändert.
- Alle Shop-Elemente und der Mini-Warenkorb haben jetzt den Bereich „Zugriffsschutz“, wie jedes Contao-Element.

**Nach dem Update:** Im Contao Manager den Prod-Cache leeren. Dieses ZIP lässt sich allein hochladen, wenn der Widerrufsbutton schon auf 1.1 steht. Kommst du von 0.4.0 oder älter, siehe 0.4.1.

## 0.4.3 vom 2. Oktober 2026

**Verbessert**
- Preise in Euro statt Cent: Am Produkt gibst du „12,90“ ein, die Produktliste im Backend zeigt „12,90 €“. Versandpauschale und „Kostenlos ab“ im Assistenten ebenfalls in Euro.
- Seiten wählst du im Assistenten aus einer Liste nach Website gruppiert, eingerückt wie im Seitenbaum und mit Suchfeld.
- Die Mails haben einen eigenen Menüpunkt: Inhalte → Shop-Mails, mit Vorschau und Testmail. Alte Links aus dem Assistenten führen weiter dorthin.
- Alle Texte im Shop (Produktliste, Warenkorb, Kasse, Bestätigung) kommen aus Sprachdateien. Englische Seiten zeigen den Shop auf Englisch, und einzelne Texte lassen sich im Projekt anpassen (siehe Anleitung „Texte anpassen“). Rechtlich vorgegebene Texte wie „Zahlungspflichtig bestellen“ sind dort markiert.

**Nach dem Update:** Im Contao Manager den Prod-Cache leeren. Dieses ZIP lässt sich allein hochladen.

## 0.4.2 vom 2. Oktober 2026

**Verbessert**
- Produktliste, Produktseite, Warenkorb, Kasse und das Warenkorb-Modul haben jetzt CSS-ID/Klasse und Template-Auswahl sowie Sichtbarkeitseinstellungen wie normale Contao-Elemente. So lassen sich Varianten aus dem Theme ohne Template-Änderung zuweisen.

**Nach dem Update:** Kommst du von 0.4.0 oder älter, lade den Widerrufsbutton 1.1 zusammen mit dem Mini-Shop hoch (siehe 0.4.1).

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

**Nach dem Update:** Der Mini-Shop braucht ab dieser Version den Widerrufsbutton 1.1. Lade im Contao Manager beide ZIPs zusammen hoch (Mini-Shop und Widerrufsbutton, beide auf deiner Download-Seite) und wende die Änderungen gemeinsam an. Wird nur der Mini-Shop hochgeladen, bricht der Manager mit „conflicts with your root composer.json require (1.0.1)“ ab. Danach den Prod-Cache leeren und neu erzeugen.

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
