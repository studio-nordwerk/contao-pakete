# Widerrufsbutton: Was ist neu?

Der Widerrufsbutton (`nordwerk/contao-withdrawal-bundle`) ist Open Source (MIT) und wird mit Mini-Shop und Seminaren genutzt. Quellcode: [studio-nordwerk/contao-withdrawal](https://github.com/studio-nordwerk/contao-withdrawal).

## 1.2.2 vom 11. November 2026

**Verbessert**
- Mail-Editor (Widerruf, Shop-Mails, Seminar-Mails): Die Reiter der Mailtypen tragen lesbare Namen statt interner Schlüssel wie „seminar payment reminder“.
  - Seminar: Zahlungserinnerung, Buchungsbestätigung, Info an Anbieter, Warteliste, Platz frei, Erinnerung, Absage und Teilnahmebestätigung.
  - Shop: Zahlungserinnerung, Bestellbestätigung, Info an Händler, Zahlungseingang, Versandbestätigung und Storno.
  - Widerruf: Eingangsbestätigung und Info an Händler.
- Das gilt auch für die Überschrift über den Textfeldern. Im englischen Backend erscheinen die Namen auf Englisch.

**Nach dem Update:** Im Contao Manager den Prod-Cache leeren. Eine Datenbankänderung gibt es nicht. Die Version lässt sich allein oder zusammen mit Mini-Shop und Seminaren hochladen. Deine Mailtexte und Einstellungen bleiben erhalten.

## 1.2.1 vom 27. Oktober 2026

**Verbessert**
- Der Mail-Editor sieht aus wie ein normales Contao-Formular: Felder in zwei Spalten mit Hilfetexten, Speichern-Buttons in der gewohnten Leiste unten. Beschriftungen gibt es auf Deutsch und Englisch, passend zur Sprache des Backends.

**Behoben**
- Nach dem Speichern im Mail-Editor meldete die Browser-Konsole „Form responses must redirect to another location“. Der Editor leitet nach dem Speichern und nach einer Testmail jetzt wie jedes Contao-Formular weiter und zeigt die Bestätigung danach an. Bei einer fehlerhaften Eingabe bleibt das Formular mit der Fehlermeldung stehen.

**Nach dem Update:** Prod-Cache leeren. Eine Datenbankaktualisierung ist nicht nötig, Einstellungen und Mailtexte bleiben unverändert.

## 1.2.0 vom 26. Oktober 2026

**Neu**
- Die Einstellungen stehen jetzt im gewohnten Contao-Formular unter Inhalte → Widerruf einrichten: Händleradresse, Pfad und Grundgestaltung, mit Versionen und Wiederherstellung. Die Mailtexte erreichst du dort über „Mailtexte bearbeiten“. Alte Links zu den Mailtexten leiten weiter.
- Das Inhaltselement hat jetzt die üblichen Felder „Unsichtbar“ und „Anzeigen ab/bis“ sowie eine Überschrift mit wählbarer Ebene (h1 bis h6).

**Verbessert**
- Das Element gibt genau eine Überschrift aus: deine eigene mit der gewählten Ebene, ohne eigene Überschrift „Vertrag widerrufen“ als `h1`.
- Das Stylesheet wird einmal pro Seite im Seitenkopf geladen und ist versioniert, sodass Browser nach Updates die neue Fassung holen.
- Nach einer Änderung des Pfads zeigen auch zwischengespeicherte Seiten sofort den neuen Link im Footer.

**Behoben**
- Im Mail-Editor ließen sich Absender und Akzentfarbe nicht speichern („Invalid mail design or salutation.“), weil das Zeichen `#` umkodiert wurde. Klammern und `=` in Mailtexten wurden als Zeichencodes gespeichert. Beides funktioniert jetzt. Texte, die früher so gespeichert wurden, bleiben unverändert, bis du sie neu speicherst.

**Hinweis zu eigenen Anpassungen:** Hast du das Template `withdrawal` überschrieben und darin den Block `content` erweitert, kommt die Überschrift jetzt aus dem Block `inner`. Steht in deinem `content` eine eigene `<h1>`, erscheint sie doppelt. Zu „Anzeigen ab/bis“: Wie bisher in der README beschrieben, sollte das Widerrufsformular nicht zeitgesteuert ausgeblendet werden. Die Texte der Überschrift und des Footer-Links sind unverändert.

**Templates geändert:** `withdrawal`. Hast du es im Template Studio überschrieben, vergleiche deine Fassung mit dem neuen Original.

**Nach dem Update:** Die Version lässt sich vor oder zusammen mit den anderen Paketen hochladen. Danach im Contao Manager die Datenbank aktualisieren (es ändern sich keine bestehenden Spalten) und den Prod-Cache leeren. Deine Einstellungen, Mailtexte und Benutzerrechte bleiben erhalten, du musst nichts neu einrichten. Das Recht „Widerruf einrichten“ genügt weiterhin; zusätzliche Feld- oder Tabellenrechte sind nicht nötig. Bindet dein Layout `withdrawal-base.css` zusätzlich selbst im Seitenkopf ein (zum Beispiel das Seminar-Theme bis 0.5.x), wird das Stylesheet doppelt geladen. Das ist unschädlich; der Link im Layout kann entfallen.

## 1.1.1 vom 25. Oktober 2026

**Behoben**
- Der Contao Manager meldete bei einer frischen Installation „funktioniert nicht mit Contao 5.7.*“ und sperrte den Upload, obwohl der Widerrufsbutton ab Contao 5.7.12 läuft. Die Meldung erscheint nicht mehr.

**Nach dem Update:** Im Contao Manager den Prod-Cache leeren.

## 1.0.0 vom 29. September 2026

Erste stabile Version des Widerrufsbuttons (§ 356a BGB) für Contao 5.7. Installation: ZIP im Contao Manager unter „Pakete hochladen“, danach Datenbank aktualisieren.
