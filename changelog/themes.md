# Shop-Theme und Seminar-Theme: Was ist neu?

Seit dem 5. Oktober 2026 reicht eine ZIP je Theme: Du lädst nur dein Theme im Contao Manager hoch, die Theme-Basis holt der Manager selbst.

Hast du die Theme-Basis früher als eigene ZIP hochgeladen, lade sie bei Updates weiterhin zusammen mit dem Theme hoch. Du findest sie unter deinem persönlichen Download-Link mit dem Zusatz `contao-theme-base/latest.zip`. Die Hinweise „Theme-Basis und Theme zusammen hochladen“ in den Abschnitten unten gelten nur für diesen Fall.

## 0.6.0 vom 26. Oktober 2026

**Neu**
- Layout → Theme einrichten: ein eigener Menüpunkt für Theme-Basis, Shop- und Seminar-Theme. Er zeigt auf einer leeren Website die Willkommensfrage, importiert die Demo und listet vor einem Ersetzen auf, welche Datensätze überschrieben werden. Demo-Import und Ersetzen bleiben Administratoren vorbehalten, weil sie Seiten, Produkte und Einstellungen über alle Rechte hinweg schreiben. Jeder importierte Datensatz bekommt eine Version, nach einem Ersetzen ist der frühere Stand unter „Versionen“ wiederherstellbar. Das Modul hat ein eigenes Recht unter „Erlaubte Module“ in der Benutzergruppe.
- Die Assistenten „Shop einrichten“ und „Seminar einrichten“ sind wieder die unveränderten Assistenten der Pakete und laufen mit deren eigenen Rechten, auch für Nicht-Administratoren.
- Das Logo darf eine SVG-Datei sein und hat das Feld „Bildgröße des Logos“. Shop-Kategorien, Shop-Hero und Seminargalerie haben eine wählbare Bildgröße; ohne Auswahl gelten Standardgrößen des Themes.
- Neue Vorlage `nw_theme` für Seitenlayouts vom Typ „Twig-Layout mit Slots“. Das bisherige Demo-Layout bleibt klassisch; bestehende Layouts werden nicht umgestellt.
- Alle Frontend-Texte der Themes, ihre Backend-Beschriftungen und Fehlermeldungen gibt es auf Deutsch und Englisch.
- Seminar-Theme: Das Modul „Seminar: Termin und Buchung“ hat die Felder „Vorlage der Seminarbuchung“ und „Bildgröße“. Das versteckte Buchungselement unter dem Theme gibt es nicht mehr.

**Verbessert**
- Farben, Schriften und weitere Einstellungen des Theme-Formulars gelten für jedes Seitenlayout deines Themes, nicht mehr nur dort, wo das Kopfzeilen-Modul sitzt. Die Stylesheets des Themes sind versioniert und laden damit nach Updates neu. Sie stehen im Seitenkopf vor deinen „Externen Stylesheets“, deine eigenen Dateien haben also Vorrang.
- Das Feld „Zusätzliche head-Tags“ im Seitenlayout enthält keine Theme-Links mehr. Eigene Tags und das Favicon bleiben.
- Theme-Seiten werden beim Speichern des Theme-Formulars im Seitencache aktualisiert.
- Hero: Die gewählte Überschriftenebene wird ausgegeben. Ohne Überschrift erscheint keine mehr (der Demo-Text als Ersatz entfällt).
- Navigation: Eine im Navigationsmodul gewählte eigene Vorlage hat Vorrang vor der Vorlage des Themes.
- Seminar-Theme: Die Fußzeile baut wie beim Shop auf der gemeinsamen Fußzeile der Theme-Basis auf. Preis und Datum der Terminkarten folgen der Seitensprache.
- Die Terminseite mit Buchung wird nicht mehr von der Zwischenspeicherung ausgeschlossen; die Seminarbuchung steuert den Cache selbst.
- Das Seminar-Theme verlangt Contao 5.7.12 oder neuer, wie die übrigen Pakete.

**Entfernt**
- Die ungenutzten Felder „Zweites Bild“, „Zweite Überschrift“ und „Zweiter Text“ des Shop-Hero sind weg. Contao bietet bei der Datenbankaktualisierung an, die Spalten zu löschen; das ist optional.

**Templates geändert:** `nw_shop_header`, `nw_shop_footer`, `nw_shop_hero`, `nw_shop_categories`, `nw_theme_header`, `nw_theme_footer`, `nw_seminar_header`, `nw_seminar_footer`, `seminar_booking_nw`, `_event`. Neu als Twig-Fassung: `nav_nw`, `mod_nw_navigation`, `mod_faqpage_nw` und `event_nw_seminar` (die bisherigen HTML5-Dateien entfallen), dazu `_nw_design_variables` und das Layout `nw_theme`. Hast du eines davon im Template Studio überschrieben, vergleiche deine Fassung mit dem neuen Original. Eine bisherige HTML5-Überschreibung von `event_nw_seminar` funktioniert weiter. Bei `nav_nw`, `mod_nw_navigation` und `mod_faqpage_nw` prüfe bitte nach dem Update, ob deine Überschreibung noch greift.

**Nach dem Update:** Lade die Theme-Basis 0.6.0 zusammen mit deinem Theme hoch. Das Shop-Theme 0.6.0 braucht Mini-Shop 0.7 (und damit Payment 1.2.0, siehe Mini-Shop 0.7.0), das Seminar-Theme 0.6.0 braucht Seminar 0.3. Lade die passenden ZIPs im selben Durchgang hoch. Danach im Contao Manager die Datenbank aktualisieren und den Prod-Cache leeren. Die Migration entfernt die Theme-Stylesheet-Links aus dem Kopf deiner Layouts (die Theme-Basis lädt sie jetzt selbst), überträgt beim Seminar-Theme die Vorlage des versteckten Buchungselements ins Modul und löscht dieses Element samt verwaister Reste. Eigene Head-Tags und das Favicon bleiben. Hast du beim Widerrufsbutton die Grundgestaltung abgeschaltet, entfällt mit der Migration auch dessen Stylesheet im Layout-Kopf; die Widerrufsseite nutzt dann nur noch deine eigenen Styles. Du musst nichts neu einrichten, und Terminseiten unter `/termine/<alias>` behalten ihre Adresse.

**Neues Recht „Theme einrichten“:** Der Theme-Assistent war bisher nur Administratoren zugänglich, deshalb bekommt keine Gruppe das Recht automatisch. Sollen Redakteurinnen und Redakteure die Gestaltung ändern, hake „Theme einrichten“ in ihrer Benutzergruppe unter „Erlaubte Module“ an und gib unter „Erlaubte Felder“ die Gestaltungsfelder des Themes frei. Demo importieren und ersetzen können nur Administratoren; der Hinweis auf der Backend-Startseite erscheint deshalb nur ihnen. „Shop einrichten“ und „Seminar einrichten“ brauchen weiterhin ihr eigenes Modulrecht. Ein Ersetzen bleibt durch Bestätigung und die Sperre nach Bestellungen bzw. Buchungen geschützt.

## 0.5.7 vom 23. Oktober 2026

**Behoben**
- Der Contao Manager meldete bei einer frischen Installation „funktioniert nicht mit Contao 5.7.*“ und sperrte den Upload, obwohl die Pakete ab Contao 5.7.12 laufen. Theme-Basis, Shop-Theme und Seminar-Theme verlangen jetzt Contao 5.7 und schließen ältere Versionen als 5.7.12 auf anderem Weg aus; die Meldung erscheint nicht mehr. Bei älteren Paketversionen hilft: beim Contao-Paket über das Zahnrad die Versionsbedingung auf `~5.7.12` stellen.

**Nach dem Update:** Im Contao Manager den Prod-Cache leeren.

## 0.5.6 vom 23. Oktober 2026

**Neu**
- Shop-Theme: passt zum Mini-Shop 0.5 mit Produktarten. Die Demo-Produkte sind als „Kosmetik und Pflege“ angelegt.

**Nach dem Update:** Im Contao Manager den Prod-Cache leeren.

## 0.5.5 vom 14. Oktober 2026

**Behoben**
- Shop-Theme: Auf Unterseiten wie `/shop/lavendelseife` luden Stylesheets und Favicon nicht (404), weil das Demo-Layout sie ohne `/` am Anfang einband. Neue Demo-Importe verwenden absolute Pfade, bestehende Demo-Layouts korrigiert die Datenbankmigration.
- Shop-Theme: Demo-Produkte werden so gespeichert, dass der neue Kategorie-Filter des Mini-Shops 0.4.5 sie findet.

**Nach dem Update:** Im Contao Manager die Datenbank aktualisieren und den Prod-Cache leeren.

## 0.5.4 vom 5. Oktober 2026

**Verbessert**
- Shop-Hero: Das Bild hat jetzt die Contao-Auswahl „Bildgröße“. Ohne Angabe bleibt der bisherige Zuschnitt.
- Shop-Hero: Die Felder heißen „Ziel des ersten Buttons“ und „Ziel des zweiten Buttons“ und passen damit zu jeder Seite, nicht nur zu Shop und „Über uns“. Ohne eigenen Text trägt der erste Button den Namen der gewählten Seite.
- Abschnitte (Hero, Seitenkopf, Bild und Text, Person, Logos): mit dem Paket „Nordwerk Abschnitte“ 0.1.1 gibt es dort ebenfalls die Auswahl „Bildgröße“. Der Contao Manager holt es beim Update von selbst.

**Nach dem Update:** Im Contao Manager den Prod-Cache leeren.

## 0.5.3 vom 5. Oktober 2026

**Verbessert**
- Die Module und Elemente der Themes stehen dort, wo man sie in Contao sucht: Kopfzeile und Fußzeile beider Themes unter „Navigation“, Shop-Hero, Shop-Vorteile und Shop-Kategorien in der Gruppe „Mini-Shop“.
- Alle Theme-Module und Theme-Elemente haben jetzt den Bereich „Zugriffsschutz“, wie jedes Contao-Element.
- Shop-Theme: Im Modul „Kopfzeile“ zeigt das Feld „Mini-Warenkorb“ nur noch die Warenkorb-Module des eigenen Themes.
- Seminar-Theme: Im Modul „Termin und Buchung“ wählst du die Seminarbuchung aus einer Liste, statt eine ID einzutippen. Das Modul hat außerdem eine Template-Auswahl.

**Nach dem Update:** Im Contao Manager den Prod-Cache leeren. Am besten zusammen mit Mini-Shop 0.4.4 bzw. Seminare 0.2.3 aktualisieren, dann erscheinen auch deren Elemente in den neuen Gruppen.

## 0.5.2 vom 5. Oktober 2026

**Verbessert**
- Shop-Theme und Seminar-Theme verlangen jetzt mindestens die Theme-Basis 0.5.1. So kann kein Theme mehr mit einer älteren Basis laufen, in der der Link „Vertrag widerrufen“ und der Button der Kopfzeile noch fehlen.

**Nach dem Update:** Lade die Theme-Basis und dein Theme zusammen hoch und wende die Änderungen gemeinsam an. Danach den Prod-Cache leeren.

## 0.5.1 vom 4. Oktober 2026

**Verbessert**
- Kopfzeile und Fußzeile hängen nicht mehr an den Demo-Seiten: Das Logo führt zur ersten Seite deiner Website. Den hervorgehobenen Button der Kopfzeile stellst du im Modul „Kopfzeile“ ein (Ziel und Text); ohne Ziel erscheint kein Button.
- Shop-Theme: Im Modul „Fußzeile“ wählst du die Seite hinter dem Link „Vertrag widerrufen“. Der Wortlaut des Links bleibt fest.

**Nach dem Update:** Lade die Theme-Basis und dein Theme zusammen hoch, dann die Datenbank aktualisieren und den Prod-Cache leeren. Deine bisherigen Ziele (Termine-Button, Widerrufsseite) werden dabei übernommen.

## 0.5.0 vom 4. Oktober 2026

**Neu**
- Navigation mit Bordmitteln von Contao: Das Menü der Kopfzeile ist jetzt ein normales Modul „Navigationsmenü“, die beiden Spalten der Fußzeile sind Module „Individuelle Navigation“. Du findest sie unter Layout → Themes → Frontend-Module als „Hauptnavigation“, „Fußzeile: Seiten“ und „Fußzeile: Rechtliches“ und pflegst sie wie in jeder Contao-Website.
- Untermenüs: Erhöhst du im Modul „Hauptnavigation“ das Stoplevel, zeigt die Kopfzeile Unterseiten als Aufklappmenü, das Mobilmenü als eingerückte Liste.
- Weiterleitungsseiten (intern und extern) erscheinen jetzt im Menü.

**Verbessert**
- Die Module heißen wie die Layoutbereiche in Contao: „Kopfzeile“ und „Fußzeile“ statt „Kopf“ und „Fuß“. Das Feld im Theme heißt „Anordnung der Kopfzeile“.
- In den Modulen Kopfzeile und Fußzeile wählst du nur noch, welches Navigationsmodul erscheint. Die Felder „Startpunkt der Navigation“ und „Weitere Seiten“ entfallen.

**Nach dem Update:** Lade die Theme-Basis und dein Theme zusammen hoch, dann die Datenbank aktualisieren und den Prod-Cache leeren. Dabei entstehen die drei Navigationsmodule automatisch mit deinen bisherigen Links. Die Seitenspalte der Fußzeile ist danach eine feste Auswahl: Neue Seiten fügst du im Modul „Fußzeile: Seiten“ hinzu. Im Seminar-Theme heißt der Link „Alle Termine“ dort jetzt wie die Seite, also „Termine“.

## 0.4.0 vom 2. Oktober 2026

**Neu**
- Ein Assistent für den Start: Bei leerer Website fragt „Shop einrichten“ bzw. „Seminar einrichten“ zuerst, ob du mit einer fertigen Beispielseite oder ohne starten möchtest. Danach geht es direkt mit deinen eigenen Angaben weiter.
- Kopfbereich ohne Template-Änderung: Im Frontend-Modul „Kopf“ wählst du den Startpunkt der Navigation (Seiten blendest du wie gewohnt über „Im Menü verstecken“ aus) sowie Text und Ziel eines hervorgehobenen Buttons, oder blendest ihn aus.
- Die Buttons im großen Startbereich (Hero) haben eigene Texte, zum Beispiel „Zum Sortiment“ statt „Alle Produkte“.

**Verbessert**
- Die Navigation folgt jetzt der Website, auf der sie steht, auch wenn du die Demo-Seiten durch eigene ersetzt hast.

**Nach dem Update:** Lade die Theme-Basis und dein Theme zusammen hoch, dann die Datenbank aktualisieren (neue Felder) und den Prod-Cache leeren.

## 0.3.1 vom 2. Oktober 2026

**Verbessert**
- Frische Installation ohne Seiten: Die Contao-Startseite zeigt einen Hinweis mit dem Link „Demo-Seiten anlegen“, und „Shop einrichten“ bzw. „Seminar einrichten“ beginnt mit diesem Schritt. Ein Klick legt eine fertige Beispielseite an, beim Shop-Theme mit Startseite, Shop, Beispielprodukten und Kategorien, Warenkorb, Kasse und Rechtstext-Seiten. Danach passt du alles in Contao an oder löschst es. Sobald die Website Seiten hat, verschwindet der Hinweis.

**Nach dem Update:** Lade im Contao Manager beide ZIPs zusammen hoch, die Theme-Basis und dein Theme (Shop- oder Seminar-Theme), und wende die Änderungen gemeinsam an. Danach den Prod-Cache leeren.

## 0.3.0 vom 2. Oktober 2026

**Neu**
- Die Gestaltung pflegst du jetzt dort, wo man es in Contao erwartet: unter Layout → Themes → Theme bearbeiten, Bereich „Gestaltung“. Neu dazu: Seitenhintergrund, Textfarbe, zwei Flächenfarben, Ecken und Buttonform, jeweils mit Farbwähler. Leere Felder behalten die Vorgabe des Themes, und das Speichern warnt, wenn Text schlecht lesbar würde. Die Einrichtung verlinkt direkt dorthin.
- Fußzeile ohne Template-Änderung: Im Frontend-Modul „Fuß“ stellst du einen Freitext (z. B. Öffnungszeiten), die Spaltenüberschriften und zusätzliche Seiten ein. Der Demo-Hinweis ist ein Schalter und bei bestehenden Seiten aus.
- Gestaltungsvarianten für Artikel und Inhaltselemente: Hintergrund (Fläche 1, Fläche 2, Dunkel), Abstände, schmale Breite, zentriert, bei Produktlisten Hoch- oder Querformat und Karten mit Rahmen. Mit der kostenlosen Erweiterung „Component Style Manager“ als Auswahllisten, sonst über das Feld „CSS-Klasse“.
- Alle Theme-Elemente haben CSS-ID/Klasse und Template-Auswahl, wie Contao-Elemente.

**Behoben**
- Das Theme-Formular ließ sich nicht speichern, weil das Pflichtfeld „Autor“ leer war. Bestehende Themes bekommen den Eintrag beim Update automatisch.

**Nach dem Update:** Im Contao Manager die Datenbank aktualisieren und den Prod-Cache leeren. Für Mini-Shop-Nutzer zusammen mit Mini-Shop 0.4.2 aktualisieren.

## 0.2.1 vom 2. Oktober 2026

**Verbessert**
- Passt zu Mini-Shop 0.4: Das Shop-Theme erlaubt jetzt das Update, vorher hielt der Contao Manager den Mini-Shop auf 0.3 fest.
- In der Shop-Demo erscheint „Neu im Shop“ als Karussell zum Wischen, wenn der Mini-Shop 0.4 installiert ist.

## 0.2.0 vom 2. Oktober 2026

**Neu**
- Abschnitte für Inhaltsseiten: zwölf fertige Inhaltselemente (zum Beispiel für „Über uns“ oder Leistungen), die zur Gestaltung des Themes passen. Sie kommen aus unserem kostenlosen Abschnitte-Bundle, das automatisch mitinstalliert wird.

**Verbessert**
- Normale Contao-Inhaltselemente sehen im Theme stimmiger aus: ruhiger Abstand zwischen Texten, Bildunterschrift unter Videos, Code in einem Kasten.
- Menü und Bildergalerie schließen sich auf dem Handy über einen runden Schließen-Button, wie der Warenkorb.

## 0.1.0 vom 1. Oktober 2026

Erste Version.
- Shop-Theme mit der Demo „Seifenwerk“ und Seminar-Theme mit der Demo „Lernraum Mira“
- Logo, Farben und Schriften stellst du im Assistenten ein, mit Kontrollhinweis, wenn Text schlecht lesbar wird
- Demo-Seiten mit einem Klick: Startseite, Shop bzw. Termine, Über uns, Kontakt und Platzhalter für Rechtstexte
- Startseite mit Bild-Slider, Produkt- und Terminseiten mit Bildergalerie
- Warenkorb als Seitenleiste (Shop) und mobile Navigation
- Alle Schriften liegen auf deinem Server, nichts wird von fremden Diensten geladen
