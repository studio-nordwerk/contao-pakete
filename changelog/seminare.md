# Seminare: Was ist neu?

## 0.3.0 vom 26. Oktober 2026

**Neu**
- Alle Einstellungen im Formular: Unter Seminar einrichten → „Alle Einstellungen im Formular bearbeiten“ bearbeitest du die Seminar-Einstellungen im gewohnten Contao-Formular, mit Versionen und Rechten über Benutzergruppen. Der Assistent und das Formular schreiben dieselben Einstellungen.
- Rechtstextseiten und Stornobedingungen je Website: Im Startpunkt (Bereich „Seminarbuchung“) kannst du sie für diese Website oder Sprache abweichend festlegen. Leere Felder nutzen die Seminar-Einstellungen. Anbieterdaten und Bankverbindung gelten weiter für die ganze Installation. Buchung und Startklar-Check prüfen je Seminar-Website.
- Die Seminarliste hat eine Kalenderauswahl, mit der du sie auf bestimmte Kalender beschränkst. Ohne Auswahl zeigt sie wie bisher alle Kalender, bestehende Listen bleiben also gefüllt.
- Terminseite: Seitentitel, Beschreibung, Robots-Angabe und kanonische URL des Events werden wie in Contaos Event-Leser übernommen, die Inhaltselemente des Events werden angezeigt, der Teaser dient als Ersatz. Die Buchungsschritte sind auf „noindex“ gesetzt.
- Die Seminar-Texte, die Teilnehmeransicht, die Startklar-Warnungen und `seminar:doctor` gibt es auf Deutsch und Englisch; Preise erscheinen in der Sprache der Seite (`1.290,50 €` bzw. `€1,290.50`).

**Verbessert**
- Seminarliste und Terminseite beachten geschützte Kalender (nur für berechtigte Mitgliedergruppen) sowie „Anzeigen ab/bis“ und die Veröffentlichung des Events. Beim Abschluss einer Buchung wird das erneut geprüft.
- Liste und Terminseite sind cachebar und damit schneller. Buchungen, Stornos und Nachrücken aktualisieren die freien Plätze sofort; Reverse-Proxys ohne Tag-Unterstützung fallen auf die Cache-Zeit zurück. Die Buchungsschritte werden weiter nie zwischengespeichert.
- Die Terminseite legt keine Session mehr an. Sie beginnt erst, wenn jemand auf „Jetzt buchen“ klickt.
- Die Seminarliste nutzt die gewählte Überschriftenebene. Es gibt keine automatische `<h1>` „Seminare“ mehr; ohne Überschrift im Element erscheint keine.
- Die Teilnehmerverwaltung (Liste, Detail, CSV-Export, Zertifikat, Aktionen) zeigt nur Termine der Kalender, die du bearbeiten darfst.
- Die Mails bearbeitest du nur noch mit dem Recht „Seminar-Mails“. Ohne das Recht gibt es keinen Link und eine Zugriffsverweigerung (403). Alte Links leiten weiter.
- Das Zertifikat verschickst du per Button (Formular mit Sicherheits-Token). Der alte Link mit `mail_certificate=1` verschickt nichts mehr.
- Die Datumsfelder „Anmeldeschluss“ sowie Bescheid- und Gültigkeitsdaten von Bildungsurlaub und Steuerbescheinigung sind wirklich leer, wenn du nichts einträgst. Die Migration setzt frühere Nullwerte zurück.
- Englische Mails: Preise im englischen Format; „Ihre Buchung wurde storniert.“ und „Verwendungszweck:“ sind übersetzt.

**Behoben**
- Im Mail-Editor ließen sich Akzentfarben mit `#` nicht speichern, und Absendernamen wurden umkodiert gespeichert. Texte, die früher so gespeichert wurden (zum Beispiel `&amp;`), bleiben, bis du sie neu speicherst.
- Die Bestätigungsmeldungen in der Teilnehmeransicht (etwa nach dem Zertifikatsversand) werden jetzt angezeigt.

**Templates geändert:** `_accordion` (zeigt die Inhalte des Events im Abschnitt „Inhalte“) und `seminar_event_list` (Überschrift aus dem Element). Hast du eines davon im Template Studio überschrieben, vergleiche deine Fassung mit dem neuen Original. Stylest du `.seminar-list-intro h1`, stelle das auf `.seminar-list-intro :is(h1, h2, h3)` um. In der Buchung sind `requestToken` und `flowToken` auf der Terminseite leer, neu ist `eventContent`.

**Nach dem Update:** Seminar 0.3.0 lässt sich allein hochladen; das Seminar-Theme 0.6.0 braucht Seminar 0.3.0 und wird danach oder zusammen damit hochgeladen. Danach im Contao Manager die Datenbank aktualisieren und den Prod-Cache leeren. Die Migration übernimmt deine bisherigen Einstellungen in die neuen Felder, ohne Neueinrichtung. Zu lange Texte werden gekürzt und gemeldet; das Original bleibt gespeichert. Die alte Einstellungsspalte (`data`) wird im nächsten Release entfernt.

**Neue Rechte:** Die Seminar-Einstellungen im Formular nutzen Tabellen- und Feldrechte, weil sie Bankdaten und Rechtstexte enthalten. Die Migration gibt allen Gruppen und Benutzern mit eigenen Rechten, die „Seminar einrichten“ haben, einmalig die Felder und das Tabellenrecht „Bearbeiten“ für die Seminar-Einstellungen, damit niemand ausgesperrt wird. Danach gilt deine Rechtevergabe: Wer später Einstellungen im Formular ändern soll, braucht diese Rechte in der Benutzergruppe. Der Assistent selbst braucht nur das Modulrecht. Wer Teilnehmende sehen soll, braucht außerdem das Recht, den jeweiligen Kalender zu bearbeiten.

## 0.2.5 vom 23. Oktober 2026

**Behoben**
- Der Contao Manager meldete bei einer frischen Installation „funktioniert nicht mit Contao 5.7.*“ und sperrte den Upload, obwohl die Pakete ab Contao 5.7.12 laufen. Die Pakete verlangen jetzt Contao 5.7 und schließen ältere Versionen als 5.7.12 auf anderem Weg aus; die Meldung erscheint nicht mehr. Bei älteren Paketversionen hilft: beim Contao-Paket über das Zahnrad die Versionsbedingung auf `~5.7.12` stellen.

**Nach dem Update:** Im Contao Manager den Prod-Cache leeren.

## 0.2.4 vom 14. Oktober 2026

**Behoben**
- Die Terminseite ergab eine 404-Seite, wenn auf ihr Contaos eigene Eventliste ohne Leser-Modul stand. Die Seminarbuchung allein reicht jetzt für die Terminseite, ein Event-Leser-Modul ist nicht nötig. Die Anleitung nennt den Schritt ausdrücklich: Seminarbuchung auf die Seite, die im Kalender als Weiterleitungsseite eingetragen ist.

**Nach dem Update:** Im Contao Manager den Prod-Cache leeren.

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
