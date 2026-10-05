# Shop-Theme und Seminar-Theme: Was ist neu?

Seit dem 5. Oktober 2026 reicht eine ZIP je Theme: Du lädst nur dein Theme im Contao Manager hoch, die Theme-Basis holt der Manager selbst.

Hast du die Theme-Basis früher als eigene ZIP hochgeladen, lade sie bei Updates weiterhin zusammen mit dem Theme hoch. Du findest sie unter deinem persönlichen Download-Link mit dem Zusatz `contao-theme-base/latest.zip`. Die Hinweise „Theme-Basis und Theme zusammen hochladen“ in den Abschnitten unten gelten nur für diesen Fall.

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
