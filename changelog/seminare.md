# Seminare: Was ist neu?

## 0.2.3 vom 5. Oktober 2026

**Verbessert**
- Eigene Gruppe „Seminare“: Seminarbuchung und Seminarliste stehen in der Auswahl der Inhaltselemente nicht mehr unter „Text-Elemente“. Bestehende Elemente bleiben unverändert.
- Beide Elemente haben jetzt den Bereich „Zugriffsschutz“, wie jedes Contao-Element.

**Nach dem Update:** Im Contao Manager den Prod-Cache leeren.

## 0.2.2 vom 2. Oktober 2026

**Verbessert**
- Preise gibst du am Termin in Euro ein, zum Beispiel „490,00“ oder „1.290,50“, nicht mehr in Cent. Auch die Buchungen zeigen den Preis in Euro.
- Die Mails haben einen eigenen Menüpunkt: Inhalte → Seminar-Mails. Dort stehen alle Betreffzeilen und Texte mit Vorschau und Testmail.
- Im Assistenten gibt es die Betreffzeilen nicht mehr doppelt. Schritt 7 regelt nur noch die Erinnerung vor dem Termin und verlinkt auf die Mails. Eigene Betreffzeilen aus dem Assistenten werden beim Update übernommen.

**Nach dem Update:** Im Contao Manager die Datenbank aktualisieren und den Prod-Cache leeren. Dieses ZIP lässt sich allein hochladen.

## 0.2.1 vom 2. Oktober 2026

**Verbessert**
- Seminarbuchung und Terminliste haben CSS-ID/Klasse und Sichtbarkeitseinstellungen wie normale Contao-Elemente. Varianten aus dem Theme lassen sich so ohne Template-Änderung zuweisen.
- Mit dem Widerruf-Bundle 1.1 bekommen auch die Seminar-Mails das neue, ruhigere Mail-Layout; die Mail an dich selbst begrüßt nicht mehr die Teilnehmerin.

## 0.2.0 vom 2. Oktober 2026

**Neu**
- Eine neue, ruhigere Oberfläche: Terminkarten mit großem Bild, Datum und freien Plätzen, eine Detailseite mit klarem Buchungskasten und die Anmeldung in drei Schritten (Termin, Angaben, Prüfen).
- Verständliche Adressen für die Buchung, zum Beispiel `/seminare/kraeuter-workshop/buchen`, `/pruefen` und `/danke`. Alte Buchungslinks leiten automatisch weiter.
- Die Bestätigung zeigt den Überweisungsbetrag, die IBAN gut lesbar in Vierergruppen und einen GiroCode zum Scannen.
- Die Bankverbindung lässt sich im Assistenten ändern, und eine automatische Zahlungserinnerung geht raus, wenn eine Buchung nicht bezahlt wurde.

**Verbessert**
- Zwei Anmeldungen zum selben Termin in zwei Tabs bleiben getrennt, auch beim Korrigieren der Angaben.
- Die Bestätigungsseite bleibt erreichbar, auch wenn das Formular inzwischen abgelaufen ist.
- Ist ein Termin nicht mehr veröffentlicht, führen alte Buchungslinks zur Übersicht statt auf eine Fehlerseite.
- Die Buchung funktioniert auch, wenn du sie über Elementgruppen, Module oder die Event-Liste mit Leser-Modul einbindest.
- Leise Texte und Eingabefelder haben mehr Kontrast.

**Nach dem Update:** Im Contao Manager unter Systemwartung den Prod-Cache leeren und neu erzeugen. Hast du eigene Vorlagen im Template Studio überschrieben, sieh sie dir einmal an: Die neue Oberfläche bringt neue Vorlagen mit.

## 0.1.1 vom 30. September 2026

**Behoben**
- Die Installation brach bei älteren Contao-5.7-Versionen ab. Die Seminarverwaltung verlangt jetzt Contao 5.7.12 oder neuer.

## 0.1.0 vom 29. September 2026

Erste Version.
- Buchung direkt an Contao-Events, mit freien Plätzen, Warteliste und Anmeldeschluss
- Freizeitkurs oder berufliche Weiterbildung: Der Buchungsablauf zeigt das passende Widerrufsrecht
- Vertragsmails mit allen Angaben, Teilnehmerliste im Backend, Nachrücken von der Warteliste
- Bildungsurlaub je Bundesland, Teilnahmebescheinigungen und Nachweise zur Umsatzsteuerbefreiung
- Hinweise zum Fernunterrichtsschutzgesetz (FernUSG) im Startklar-Check
- Teilnehmerdaten werden nach einer einstellbaren Frist gelöscht
- Einrichtungsassistent im Contao-Backend
