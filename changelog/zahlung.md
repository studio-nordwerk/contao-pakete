# Zahlung: Was ist neu?

Zahlung (`nordwerk/contao-payment-bundle`) ist Open Source (MIT) und wird mit Mini-Shop und Seminaren genutzt. Quellcode: [studio-nordwerk/contao-payment](https://github.com/studio-nordwerk/contao-payment).

## 1.3.0 vom 20. November 2026

**Neu**
- Mollie als weiterer Zahlungsanbieter, mit Erstattungen, Statusabfrage bei der Rückkehr und Webhook.
- Zahlungsanbieter sind austauschbare Module. Ein weiterer Anbieter, auch aus einem anderen Bundle, braucht zwei Klassen und seine Felder; Kasse, Einstellungen und Startklar-Check berücksichtigen ihn automatisch.
- Rückkehrseite: Bietet das nutzende Bundle eine eigene Seite an (z. B. Seminare die Buchungsseite), leitet die Rückkehr nach entschiedener oder abgebrochener Zahlung dorthin weiter.

**Verbessert**
- Schlüssel und Secrets aller Anbieter sind im Formular nur schreibbar, auch die aus anderen Bundles, und landen nicht in den Versionen.
- Webhooks antworten allen Anbietern mit 200 (Stripe bisher 204, Stripe akzeptiert jede 2xx).
- Das Paketarchiv bringt keine Entwicklungsdateien mehr mit; für Composer zeigt `dev-main` jetzt als 1.3.x.

**Nach dem Update:** Im Contao Manager die Datenbank aktualisieren und den Prod-Cache leeren. Mini-Shop 0.7.x und Seminare 0.4.x laufen unverändert weiter. Mollie an der Kasse nutzen erst die nächsten Versionen von Mini-Shop und Seminaren.

**Für Entwickler:** `PaymentProviderInterface` hat fünf neue Methoden (`id()`, `priority()`, `name()`, `label()`, `online()`), Anbieter werden per Autoconfiguration registriert. `PaymentService` bekommt die Anbieter als Liste. `secretKey()`, `webhookSecret()`, `mollieApiKey()`, `save()` und `fromRow()` bleiben, sind aber `@deprecated`. Neu für nutzende Bundles: `PaymentService::name()`, `online()`, `manual()`, `returnUrl()`, `PaymentSettings::update()`, `secret()`, `secretFields()`.

## 1.2.0 vom 26. Oktober 2026

**Neu**
- Die Zahlungseinstellungen stehen jetzt im gewohnten Contao-Formular unter Inhalte → Zahlung einrichten, mit Versionen und Texten auf Deutsch und Englisch. Wiederherstellbar sind Vorkasse, Bezahlung vor Ort und PayPal.me.
- Der Zugriff hängt nicht mehr an „nur Administratoren“, sondern an Benutzergruppen: Modul „Zahlung einrichten“, Tabellenrecht „Bearbeiten“ für die Zahlungseinstellungen und die erlaubten Felder. So kann eine Gruppe zum Beispiel Vorkasse und Bezahlung vor Ort schalten, ohne die Stripe-Schlüssel zu sehen oder zu ersetzen.

**Verbessert**
- Stripe-Schlüssel bleiben verschlüsselt, werden nie im Formular angezeigt und landen nicht in den Versionen. Ein leeres Feld behält den gespeicherten Schlüssel.
- Testmodus und „Stripe aktiv“ sind nicht Teil der Versionen: Eine ältere Version kann keinen Modus zurückbringen, der nicht zum gespeicherten Schlüssel passt.
- „Webhook bei Stripe anlegen“ verlangt dieselben Rechte wie das Speichern des Webhook-Secrets.
- Eine Version wiederherstellen darf nur, wer alle versionierten Felder bearbeiten darf.
- Die Fehlermeldung bei nicht ladbaren Routen nennt jetzt das Zahlungs-Paket statt des Mini-Shops.

Zahlungsabläufe, Mails und Pflichtangaben ändern sich nicht. Die Liste „Zahlungen“ bleibt unverändert.

**Nach dem Update:** Payment 1.2.0 lässt sich nur zusammen mit Mini-Shop 0.7.0 oder neuer betreiben und verweigert ältere Mini-Shops (bis 0.6.x), weil diese die Einstellungen sonst veraltet läsen. Lade deshalb beide ZIPs zusammen hoch. Seminare sind nicht betroffen. Danach im Contao Manager die Datenbank aktualisieren und den Prod-Cache leeren. Die Migration übernimmt Vorkasse, Stripe (samt verschlüsselter Schlüssel), Bezahlung vor Ort und PayPal.me, ohne Neueinrichtung. Der `APP_SECRET` der Installation darf sich dabei nicht ändern. Bis die Migration gelaufen ist, gelten die Standardwerte (nur Vorkasse).

**Rechte:** Administratoren behalten vollen Zugriff. Benutzergruppen, die bisher das Modul „Zahlung einrichten“ angehakt hatten, konnten damit nichts bearbeiten und bekommen auch jetzt nichts Neues; sie erhalten beim Öffnen eine Zugriffsverweigerung (403). Sollen Mitarbeitende die Zahlungseinstellungen ändern, gib in der Benutzergruppe das Tabellenrecht „Bearbeiten“ für die Zahlungseinstellungen und die gewünschten Felder frei. Für die Stripe-Schlüssel und das Anlegen des Webhooks sind die Felder „Secret Key“ und „Webhook-Secret“ nötig; lass sie weg, wenn nur Administratoren damit arbeiten sollen.

**Für Entwickler:** Die alte Spalte `data` bleibt vorerst erhalten, wird aber nicht mehr gelesen oder geschrieben. Wer die Einstellungen direkt aus der Tabelle liest, wechselt auf `PaymentSettings::stored()`, das dasselbe Format liefert.

## 1.1.0 vom 25. Oktober 2026

**Neu**
- Bezahlung vor Ort (bar oder PayPal): Unter **Inhalte → Zahlung einrichten** einschalten. Der Mini-Shop 0.6 bietet sie als „Bezahlung bei Abholung“ nur zusammen mit Abholung an. Die Zahlung bleibt offen, bis du sie unter **Zahlungen** oder in der Bestellung bestätigst; es gibt keine Zahlungserinnerung.
- PayPal.me-Link (optional): Bestätigungsmail und Danke-Seite zeigen dann einen QR-Code und Link, in denen der Betrag schon steht.

**Behoben**
- Der Contao Manager meldete bei einer frischen Installation „funktioniert nicht mit Contao 5.7.*“, obwohl das Paket ab Contao 5.7.12 läuft. Die Meldung erscheint nicht mehr.

**Nach dem Update:** Im Contao Manager den Prod-Cache leeren. Zusammen mit Mini-Shop 0.6.0 hochladen, wenn du den Shop nutzt.

## 1.0.0 vom 1. Oktober 2026

Erste stabile Version der Zahlungsschicht für Contao 5.7 (Mini-Shop und Seminare).

- Vorkasse per Überweisung mit Bankdaten und GiroCode zum Scannen
- eine automatische Zahlungserinnerung bei offenen Beträgen
- Zahlungen, Ereignisprotokoll und Erstattungen im Contao-Backend
- Stripe Checkout (Karte, Wallets und mehr), optional: erst aktiv, wenn es unter „Inhalte → Zahlung einrichten“ vollständig eingerichtet ist

Installation: im Contao Manager nach `nordwerk/contao-payment-bundle` suchen oder per Composer.
