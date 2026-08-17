# Anweisung für Claude Code: THG-Prämien-App-Prototyp

> Diese Anweisung als Prompt an Claude Code geben. Die Referenz-Screenshots aus
> `docs/screens/` (01–10) mitgeben bzw. anhängen — sie zeigen das Zielbild jedes Screens.

---

## Prompt (Copy & Paste)

Baue einen App-Prototyp für Vermögensberater, mit dem sie die THG-Prämie für
E-Auto-Kunden abwickeln. Halter reiner Elektrofahrzeuge können ihre
Treibhausgasminderungsquote einmal pro Kalenderjahr verkaufen; der Kunde erhält
dafür 250 Euro, der Berater eine Vermittlungsvergütung von 30 Euro. Weil die
Quote jedes Kalenderjahr neu vermarktet wird, wiederholt sich der Vorgang
jährlich mit demselben Kunden. Die angehängten Screenshots (01–10) zeigen das
exakte Zielbild — bitte pixelgenau in diesem Stil umsetzen.

### Technik

- Eine einzige Datei `thg-praemie/index.html`: HTML + CSS + Vanilla-JavaScript,
  keine Frameworks, keine externen Ressourcen (Icons als Inline-SVG).
- Mobile-first, max. 480 px breit, zentriert; Persistenz über `localStorage`.
- View-Wechsel per JS-Rendering in ein `<main>`-Element (Views: Übersicht,
  Auftragsliste, Auftragsdetail, Wizard, Erfolgsseite).
- Beim ersten Start einen Beispiel-Auftrag aus dem Vorjahr seeden
  (Status „Ausgezahlt“), damit die jährliche Wiederholung sofort sichtbar ist.

### Designsystem (siehe Screenshots)

- Farben: Gold `#C0A32B` (dunkler `#A98F1F`), Hintergrund rosé-weiß `#FAF3F6`,
  Karten weiß mit Radius 14 px und weichem Schatten, Text `#26262B`,
  gedämpft `#8E8E98`, Erfolgsgrün `#3E8E5A`, Warnton `#B3541E`.
- Goldene Hero-Header mit diagonal angeschnittener Unterkante (clip-path),
  darin große weiße Headline (~34 px) und Untertitel; erste Karte überlappt
  den Header nach oben.
- Wizard-Kopf: „‹ Abbrechen“ links, zentrierter Titel „THG-Antrag“, darunter
  5 nummerierte Schritt-Kreise mit Verbindungslinien (erledigt = gold mit
  Häkchen, aktiv = gold, offen = grau umrandet).
- Buttons: „Weiter“ goldgefüllt (deaktiviert: blasses Gold), „Zurück“ mit
  Goldrahmen; Formulare mit Label über dem Feld, Platzhalter „Bitte eingeben“.
- Untere Navigation: Haus-Icon links, mittig eine um 45° gedrehte goldene
  Raute als Plus-Button (startet neuen Antrag), Klemmbrett-Icon rechts;
  im Wizard ausgeblendet.
- Footer-Plakette auf Übersicht und Erfolgsseite: „Deutsche Vermögensberatung ·
  THG-Prämie · Prototyp“.

### Übersicht (Screenshot 01)

- Goldener Header „THG-Prämie“ mit Untertitel „250 € für Ihre E-Auto-Kunden –
  jedes Jahr aufs Neue.“, Glocke mit Zähler-Badge und Berater-Avatar
  („Pablo Meier“, VB-Nummer 4962100, Initial im blaugrauen Kreis).
- Goldene CTA-Karte „Neuer THG-Antrag – Fahrzeugschein scannen & abschließen“.
- Karte „Mein THG-Geschäft“ mit drei Kacheln: Eingereicht / Ausgezahlt /
  € Vergütung gesamt.
- Karte „Jetzt wieder fällig · <Jahr>“: Kunden aus Vorjahren, deren Quote im
  laufenden Jahr noch nicht eingereicht ist (Vergleich über FIN), mit Badge
  „Erneut sichern“. Ein Klick übernimmt alle Daten des Vorjahresauftrags und
  springt direkt zu Wizard-Schritt 2 — nur Aufklärung und Unterschrift sind
  neu nötig. Info-Hinweis dazu unter der Liste.
- Karte „Aufträge <Jahr>“ mit den Aufträgen des laufenden Jahres
  (Initialen-Kachel, Name, Fahrzeug · Kennzeichen · Datum, Status-Badge).

### Wizard: 5 Schritte im Durchklickprinzip

**Schritt 1 – Fahrzeugschein (Screenshots 02, 03):** Große gestrichelte
Scan-Fläche „Zulassungsbescheinigung Teil I fotografieren“. Zwei Optionskarten:
„Mit Kamera scannen“ (öffnet `<input type="file" accept="image/*"
capture="environment">`, Foto wird auf max. 900 px verkleinert und gespeichert)
und „Demo ohne Foto“ (Beispieldaten für Präsentationen). Nach Auswahl läuft
eine Scan-Animation (~2 s, wandernde Lichtlinie, Overlay „Texterkennung
läuft …“), dann wird die Texterkennung simuliert: ein zufälliger von drei
Beispieldatensätzen (VW ID.3 Pro / Tesla Model 3 / Renault Zoe R135, jeweils
mit Halter, Adresse, Kennzeichen, FIN, Erstzulassung, Klasse M1, Antrieb
Elektro) füllt alle Felder. Grüne Bestätigung, erst dann wird „Weiter“ aktiv.

**Schritt 2 – Daten prüfen (Screenshot 04):** Alle Felder editierbar, mit den
Feldkürzeln der Zulassungsbescheinigung Teil I: Halter (Vorname C.1.2,
Name C.1.1, Straße C.1.3, PLZ/Ort), Fahrzeug (Kennzeichen A, Marke D.1,
Handelsbezeichnung D.3, FIN E, Erstzulassung B als Datumsfeld, Antriebsart P.3
als Auswahl Elektro/Hybrid/Benzin/Diesel). Ist die Antriebsart nicht „Elektro“,
erscheint eine Warnung „Nur reine Elektrofahrzeuge sind berechtigt“ und
„Weiter“ ist blockiert. Pflichtfelder: Vorname, Name, Kennzeichen, FIN.

**Schritt 3 – Bankverbindung (Screenshot 05):** IBAN-Feld mit automatischer
4er-Gruppierung während der Eingabe und echter Mod-97-Prüfung (deutsche IBAN:
22 Stellen); Live-Hinweis „IBAN geprüft ✓“ bzw. „IBAN unvollständig oder
ungültig“, „Weiter“ nur bei gültiger IBAN. Optionskarte „Demo-IBAN verwenden“
setzt eine gültige Muster-IBAN ein. Info-Hinweis: Auszahlung nach Bestätigung
durch das Umweltbundesamt, i. d. R. 10–16 Wochen nach Einreichung.

**Schritt 4 – Aufklärung (Screenshot 06):** Sechs Pflichtpunkte, streng im
Durchklickprinzip: immer nur eine Karte sichtbar (Icon, Titel, Erklärtext,
Bestätigungszeile mit Checkbox), „Bestätigen & weiter“ erst nach gesetztem
Häkchen aktiv; darüber ein Segment-Fortschrittsbalken (6 Segmente) und Zähler
„Punkt x von 6“. Bestätigungszeitstempel je Punkt speichern. Die Punkte:

1. **Reines Elektrofahrzeug** – Das Fahrzeug ist ein reines
   Batterie-Elektrofahrzeug (Antriebsart „Elektro“ laut Feld P.3). Hybrid- und
   Plug-in-Hybrid-Fahrzeuge sind nicht berechtigt.
2. **Halter laut Fahrzeugschein** – Nur der in der Zulassungsbescheinigung
   Teil I eingetragene Halter darf die THG-Quote verkaufen.
3. **Quote noch nicht vergeben** – Die THG-Quote kann je Fahrzeug nur einmal
   pro Kalenderjahr vermarktet werden; für das laufende Jahr wurde sie noch
   keinem anderen Anbieter übertragen.
4. **Widerrufsrecht – 14 Tage** – Widerruf innerhalb von 14 Tagen ohne Angabe
   von Gründen in Textform; Widerrufsbelehrung kommt mit der
   Auftragsbestätigung.
5. **Auszahlungszeitpunkt** – 250 € nach Bestätigung durch das
   Umweltbundesamt, i. d. R. 10–16 Wochen nach Einreichung, auf die
   angegebene IBAN.
6. **AGB & Datenschutz** – Kenntnisnahme der AGB und Datenschutzerklärung,
   Einwilligung in Datenverarbeitung und Weitergabe der Fahrzeugdaten an das
   Umweltbundesamt.

**Schritt 5 – Unterschrift (Screenshot 07):** Kompakte Zusammenfassung
(Fahrzeug, Prämie, „6 von 6 bestätigt ✓“), darunter eine Canvas-Signaturfläche
(Pointer-Events für Finger/Stift/Maus, gestrichelter Rahmen, Hinweis „Hier
unterschreiben“, ✕-Grundlinie). „Auftrag abschließen“ erst nach erfolgtem
Strich aktiv; „Löschen“ setzt zurück und deaktiviert wieder; „Demo-Unterschrift“
zeichnet einen geschwungenen Muster-Schriftzug per Bezierkurven und schaltet
frei. Unterschrift als PNG-DataURL im Auftrag speichern.

### Abschluss & Verwaltung

- **Erfolgsseite (Screenshot 08):** Aufploppender goldener Häkchen-Kreis,
  „Auftrag eingereicht“, zwei Geldkacheln (250 € Kunde / 30 € Vergütung),
  Karte „Wie geht es weiter?“ (Prüfung & Meldung ans Umweltbundesamt →
  Auszahlung 10–16 Wochen → ab Januar Folgejahr erneut vermarkten),
  Widerrufs-Hinweis, Buttons „Auftrag ansehen“ und „Zur Übersicht“.
- **Auftragsdetail (Screenshot 09):** Geldkacheln, Status, Fahrzeugdaten,
  Kunde & IBAN, Liste der bestätigten Aufklärungspunkte mit grünen Häkchen,
  Bild der Unterschrift. Bei Vorjahresaufträgen ohne aktuellen Folgeauftrag:
  Button „THG-Quote <Jahr> erneut sichern“ (startet vorbefüllten Wizard bei
  Schritt 2).
- **Auftragsliste (Screenshot 10):** Alle Aufträge, gruppiert nach Quotenjahr,
  absteigend sortiert, mit Anzahl-Badge je Jahr.
- Auftrags-Datensatz: id, jahr, status (eingereicht/pruefung/ausgezahlt),
  datum, Halter- und Fahrzeugfelder, iban, praemie, verguetung,
  aufklaerung[] mit Zeitstempeln, signatur (DataURL), foto (DataURL).

### Qualität

Zum Abschluss mit Playwright den kompletten Durchlauf testen: Demo-Scan →
Daten → ungültige IBAN blockiert / Demo-IBAN aktiviert → alle 6
Aufklärungspunkte nur mit Häkchen passierbar → Abschluss ohne Unterschrift
blockiert, mit (Demo-)Unterschrift möglich → Erfolgsseite → Detailansicht →
Wiederholung aus Vorjahr startet vorbefüllt bei Schritt 2. Keine
Konsolenfehler.

---

## Referenzbilder

| Datei | Screen |
|---|---|
| `docs/screens/01-uebersicht.png` | Übersicht mit CTA, Kennzahlen, „Jetzt wieder fällig“ |
| `docs/screens/02-scan.png` | Schritt 1: Scan-Auswahl |
| `docs/screens/03-scan-ergebnis.png` | Schritt 1: Texterkennung abgeschlossen |
| `docs/screens/04-daten-pruefen.png` | Schritt 2: Daten prüfen |
| `docs/screens/05-iban.png` | Schritt 3: IBAN mit Demo-IBAN |
| `docs/screens/06-aufklaerung.png` | Schritt 4: Aufklärungspunkt mit Häkchen |
| `docs/screens/07-unterschrift.png` | Schritt 5: Unterschrift |
| `docs/screens/08-erfolg.png` | Erfolgsseite |
| `docs/screens/09-detail.png` | Auftragsdetail |
| `docs/screens/10-auftraege.png` | Auftragsliste nach Quotenjahr |
