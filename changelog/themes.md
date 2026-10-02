# Shop-Theme und Seminar-Theme: Was ist neu?

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
