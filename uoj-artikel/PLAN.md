# Plan: „Mit dem Kreuz durch die Stadt“ als UOJ-Artikel

**Ziel:** Aus dem Grundtext (`uoj-artikel/grundtext.md`, ca. 1.190 Wörter) einen vollständigen, ausführlichen journalistischen Artikel (Reportage-Feature, kein nüchterner Bericht) für UOJ Deutschland (orthodoxnews.de) machen. Er soll im Format der dortigen Feature-Artikel erscheinen.

**Ausgabe (zwei Dateien):**
1. `uoj-artikel/artikel.md`: lesbare Fassung mit allen Elementen (Titel, Lead, Bilder, Zwischenüberschriften, Hervorhebungen, Mehr-zum-Thema-Kasten, Tags, Metadaten).
2. `uoj-artikel/artikel-cms.html`: derselbe Text als HTML-Fragment im UOJ-Markup (Abschnitt 4), zum Einfügen ins Redaktionssystem. Kein `<html>`/`<head>`, nur der Artikelkörper plus Kommentarblock mit Metadaten.

---

## 1. Ermittelte UOJ-Parameter (orthodoxnews.de, geprüft am 14.10.2026)

Ausgewertet wurden: „Die weinende Königin in der Blachernenkirche“ (Mensch und Kirche, ca. 1.100 Wörter), „Wenn die Welt verstummt“ (Mensch und Kirche, ca. 2.270 Wörter, mit Bildern aus Sofia), „Die Geschichte der Honigbruderschaft“ (Geschichte und Kultur, ca. 940 Wörter) sowie zwei Nachrichten (Wien, München).

| Element | UOJ-Konvention |
|---|---|
| Rubrik | Für dieses Stück: **Mensch und Kirche** (`/de/mensch-und-kirche/`). Weitere Rubriken: Nachrichten, Verteidigung des Glaubens, Geschichte und Kultur. |
| Titel (H1) | Kurz, bildhaft, ohne Doppelpunkt-Konstruktion bei Features (z. B. „Wenn die Welt verstummt“). Hier bleibt **„Mit dem Kreuz durch die Stadt“**. |
| Lead (H2 direkt unter dem Titelbild) | 1–3 Sätze, zugleich Meta-Description. Spannung oder These, kein Inhaltsverzeichnis. |
| Autorzeile | „Autor: …“. Weil der Text in der Ich-Form beginnt, steht hier ein Platzhalter: `Autor: [NAME EINTRAGEN]`. |
| Titelbild | Querformat 800×460. Bildunterschrift = Alt-Text, Muster: „Beschreibung. Foto: UOJ“ (ohne Schlusspunkt nach UOJ). |
| Zwischenüberschriften | **H3**, kurz (2–6 Wörter), neugierig machend, gern bildhaft („Nur zwei Zeugen“, „Tränen statt Glanz“). 5–7 Stück bei 1.000–2.000 Wörtern. |
| Hervorgehobene Kernsätze | `<blockquote>` mit fett + kursiv, je ein eigenständiger, zitierfähiger Satz aus dem Text (Pull-Quote). 3–5 Stück. |
| Bilder im Text | `<figure class="news-picture mceNonEditable">`, darunter die Bildunterschrift als zentrierter grauer Absatz: „Beschreibung. Foto: UOJ.“ (mit Schlusspunkt). Optional davor eine kursive, deutende Bildzeile in Anführungszeichen. |
| „Mehr zum Thema“ | Ein Kasten nach dem ersten oder zweiten Absatz, der auf einen verwandten UOJ-Artikel verweist. |
| Absätze | Kurz, 2–5 Sätze. Szenische Einstiege, Präteritum für das Geschehen, Präsens für Deutung. |
| Schluss | Kein „Fazit“. Ein ruhiger, pointierter Schlussgedanke, gern mit Rückbezug auf das Eingangsbild. |
| Tags | Am Ende, Muster `/de/tag/<slug>-<id>`. Vorhanden und passend: Orthodoxie, Feiertag, Christentum, Kirchengeschichte. |
| Schreibweisen | „Göttliche Liturgie“, „Gottesmutter“, „heilige/hl.“, Namen eingedeutscht (Daniil, Kyrill, Johannes Chrysostomos). UOJ schreibt „Patriarchalkathedrale St. Alexander Newski“. |

---

## 2. Faktengrundlage: nur das, nichts erfinden

**Regel 1:** Alle Tatsachen stammen aus dem Grundtext oder aus der geprüften Liste unten. Keine neuen Namen, Zahlen, Uhrzeiten, Zitate, Wetterdetails, Teilnehmerzahlen, Gesänge oder Szenen hinzufügen.

**Regel 2:** Aussagen, die der Grundtext als indirekte Rede bringt (Patriarch Daniil zur Bitte für Sofia, Kyrill, Chrysostomos, Johannes von Damaskus, Abt Johannes), bleiben **indirekte Rede**. Keine Anführungszeichen erfinden. Einzige zulässige wörtliche Rede ist das geprüfte Daniil-Zitat (Liste unten, Punkt e).

**Regel 3:** Die vorsichtige Einordnung zu Wulfila bleibt erhalten: Die Debatte ist offen, Johannes „hinterfragt“ die Einordnung, eine anerkannte Antwort gibt es nicht.

**Geprüfte Zusatzfakten** (bulgarische Presse: BTA, Standart, dnes.dir.bg, Novinata, OrthoChristian). Diese dürfen eingebaut werden, um die Reportage anzureichern:
- a) Die Kirche zur Kreuzerhöhung („Въздвижение на св. Кръст Господен“) liegt in Sofia. Dort begann der Zug nach der kleinen Vesper.
- b) Mit dem Patriarchen gingen Metropoliten des Heiligen Synods, Bischöfe und Geistliche; dazu Gläubige aus Sofia und dem ganzen Land.
- c) Der Zug zog durch das Zentrum Sofias und wurde von einem Blasorchester der Nationalgarde begleitet.
- d) Staatspräsidentin Iliana Jotowa schloss sich der Prozession an. Höchstens ein Satz dazu, sachlich und ohne Wertung. Er passt gut zum Chrysostomos-Gedanken („Regierende und Regierte“), dort aber ohne Überhöhung.
- e) Vor der kleinen Vesper sagte Patriarch Daniil: „Das ehrwürdige Kreuz ist der Baum des Lebens, denn an ihm hat der Herr den Tod besiegt.“ Das darf als wörtliches Zitat stehen.
- f) Der Heilige Synod hatte beschlossen, die Festgottesdienste in Sofia am 12. und 13. September zu feiern.
- g) Der 12. September 2026 war ein Samstag.

**Nicht verwenden:** Uhrzeiten, Teilnehmerzahlen, Straßennamen.

---

## 3. Aufbau des Artikels (Ziel: 1.800–2.300 Wörter)

Jeder Abschnitt des Grundtexts wird inhaltlich vollständig übernommen, journalistisch umformuliert und erweitert. Erweitert wird durch **Szene, Übergänge, Erklärung und Einordnung**, nicht durch neue Fakten. Satzweise Kopie ist zu vermeiden; Kernformulierungen des Grundtexts dürfen bleiben.

**Kopf**
- Titel: „Mit dem Kreuz durch die Stadt“
- Lead (H2, 2–3 Sätze), etwa in diese Richtung: *Im strömenden Regen trugen Gläubige in Sofia eine Reliquie des Kreuzes Christi zur Patriarchalkathedrale. 1700 Jahre nach seiner Auffindung zeigte sich, was ein Gebetsweg durch die Straßen bewirken kann: Er führt Menschen zueinander und zurück zu Christus.* (Der Executor darf frei formulieren, aber nur mit Fakten aus Abschnitt 2.)
- Autorzeile: Platzhalter
- Titelbild: Platzhalter (Abschnitt 5, Bild 1)

**Einstieg (ohne Zwischenüberschrift, 3–4 Absätze)**
1. Szene aus dem Grundtext in der Ich- bzw. Wir-Perspektive: Prozession suchen, aus dem Auto steigen, Regen, Kreuze und Ikonen, immer mehr Priester, Weihrauch, vorneweg der Patriarch. Die sinnlichen Eindrücke des Grundtexts ausgestalten, ohne neue hinzuzufügen.
2. Nachrichtenkern: wer, was, wann, wo, warum (12.09.2026, Samstag, Patriarch Daniil, Kreuzreliquie, Kirche zur Kreuzerhöhung → Alexander-Newski-Kathedrale, 1700 Jahre Auffindung, Vigil). Dazu b) und c).
3. Überleitung (Nut Graf): Worum es im Text geht, nämlich was dieser Weg über das Kreuz und die Gemeinschaft der Kirche zeigt.
4. **„Mehr zum Thema“-Kasten** nach dem 1. oder 2. Absatz: „Das Kreuz ist die beste Heilung der menschlichen Seele“, `/de/mensch-und-kirche/89041-das-kreuz-ist-die-beste-heilung-der-menschlichen-seele`, 27.09.2026, Teaser: „Emotionale Erschöpfung und Angst sind zur Lebensnorm geworden. Die alte christliche Tradition bietet einen unerwarteten Ausweg – die Annahme des eigenen Kreuzes.“

**H3-Abschnitte.** Die Überschriften des Grundtexts werden UOJ-typisch zugespitzt. Die folgenden Vorschläge dürfen leicht variiert werden.

| # | H3 (Vorschlag) | Inhalt aus dem Grundtext | Erweiterung | Elemente |
|---|---|---|---|---|
| 1 | **Ein Holz, das Hoffnung trägt** | Warum die Kirche das Kreuz erhebt: Helena, Fest am 14.09., Jubiläum, Kreuzreliquie, Kyrill (Kreuzholz an viele Orte; Bekenntnis wegen der Auferstehung), Leid und Sieg, festlicher Charakter | Daniil-Zitat e) hier einbauen und den Bogen zu „Baum des Lebens“ schlagen. Für Leser ohne orthodoxen Hintergrund erklären, warum ein Leidenswerkzeug festlich getragen wird. | Pull-Quote, z. B.: *In dem Zeichen seines Leidens erkennt die Kirche zugleich das Zeichen des Lebens.* |
| 2 | **Wenn die Stadt mitbetet** | Gebet auf den Straßen: Chrysostomos (Arme und Reiche, Einheimische und Fremde, Regierende und Regierte, Amtsträger ohne Wagen, Kaiserin zu Fuß), Übertragung auf Sofia, Häuser und Mitbürger im Gebet, Begegnung am Straßenrand | Rückbezug auf die Regenszene. Sachlich anknüpfen an d) (Präsidentin) und c) (Orchester). | Bild 2. Pull-Quote, z. B.: *Das Heilige wird durch die Stadt getragen – und seine Verehrung führt Menschen zueinander.* |
| 3 | **Verehrung ist nicht Anbetung** | Wem die Verehrung gilt: Johannes von Damaskus (Heiligung durch Berührung mit Leib und Blut; auch spätere Kreuzdarstellungen), Unterscheidung Verehrung und Anbetung, geschichtliche Wirklichkeit des Leidens, wahrer Gott und wahrer Mensch | Ruhig und erklärend für nichtorthodoxe Leser, ohne Polemik | – |
| 4 | **Zwei Balken, eine Person** | Vortrag Abt Johannes (14.09.2026, Universität hl. Clemens von Ochrid; Heilsgeschehen von der Menschwerdung bis zur Auferstehung; Baum des Lebens, Zeichen des Sieges; Horizontale und Vertikale als Bild für Christus) | Verbindung zum getragenen Kreuz. Zeitlich klarstellen: Der Vortrag war zwei Tage nach der Prozession, am Fest selbst. | Bild 3. Pull-Quote zur Horizontalen und Vertikalen. |
| 5 | **Die offene Frage nach Wulfila** | Buch „Wulfila von Gothien. Glaube und Werk des Germanenapostels“, Arianer-Frage, Dr. Rossen Milev, offene Debatte | Kurz erklären: Wulfila als Gotenbischof und Bibelübersetzer (steht im Grundtext). Die Vorsicht beibehalten. | Kurzer Abschnitt, 2 Absätze |
| 6 | **Von der Straße in die Kathedrale** | Einzug, Vigil (erklären: festlicher Abend- und Nachtgottesdienst), Reliquie zur Verehrung, 13.09. Göttliche Liturgie mit Patriarch, Bischöfen und Geistlichen, Kommunion; Eucharistie = Danksagung, Erklärung der Liturgie; Prozession und Gottesdienst als ein Weg | f) Synodenbeschluss hier einbauen | Bild 4. Pull-Quote, z. B.: *Auf den Straßen wird der Glaube sichtbar, in der Kathedrale setzt sich das Gebet fort.* |
| 7 | **Ein Segen für ganz Sofia** | Das Gebet gilt der Stadt: Bitte des Patriarchen in indirekter Rede (Heiligung der Straßen und Gebäude, Erleuchtung von Verstand und Herz aller Bewohner, Liebe zu Gott und zueinander, eigene Schwächen überwinden), Bedeutung für das Zusammenleben, auch für politisch Verantwortliche, Handeln der Gläubigen; Patriarch und Synod: Liebe Christi soll Gedanken, Worte und Taten prägen | Schlussbogen zum Anfang: Regen, Kreuz, der gemeinsame Weg | – |

**Schluss** (letzter Absatz unter H3 Nr. 7): ein bis drei Sätze, die den letzten Satz des Grundtexts aufnehmen („Der gemeinsame Weg unter dem Kreuz findet seine Fortsetzung in einem Leben nach dem Vorbild Christi“), gern als fett-kursiv abgesetzter Einzelsatz wie bei UOJ („**_Zu Gott._**“).

**Fuß:** Tags und Metadaten (Abschnitt 6).

---

## 4. HTML-Markup für `artikel-cms.html` (genau so verwenden)

```html
<!-- META
Rubrik: Mensch und Kirche
Titel: Mit dem Kreuz durch die Stadt
Lead/Meta-Description: …
Autor: [NAME EINTRAGEN]
Titelbild-Alt/Bildunterschrift: … Foto: UOJ
Tags: …
-->
<h2>LEAD-TEXT</h2>
<p>Absatz …</p>

<!-- MEHR ZUM THEMA: /de/mensch-und-kirche/89041-das-kreuz-ist-die-beste-heilung-der-menschlichen-seele -->

<h3>Zwischenüberschrift</h3>
<p>Absatz …</p>

<blockquote> <p><em><strong>Kernsatz.</strong></em></p> </blockquote>

<figure class="news-picture mceNonEditable"> <div class="box-img"><picture><img class="news-picture-image" src="[BILD-2-DATEI]" alt="Kurzbeschreibung"></picture></div> </figure>
<p style="text-align: center; font-size: 14px; color: #666;">Bildunterschrift. Foto: UOJ.</p>
```

- Buchtitel und Werke kursiv (`<em>`), deutsche Anführungszeichen „…“, Gedankenstrich –.
- Kein CSS, kein JavaScript, keine weiteren Klassen.

---

## 5. Bilder und Bildunterschriften (Platzhalter, keine Bilder erfinden oder herunterladen)

Es liegen keine Fotos vor. Bilddateien bleiben deshalb `[BILD-n-DATEI]`. Die Unterschriften beschreiben nur Motive, die laut Grundtext tatsächlich vorkamen. Der Fotonachweis lautet „Foto: UOJ“ und wird mit dem Vermerk `[Nachweis prüfen]` im META-Block markiert. Stammen Bilder von BTA, lautet der Nachweis „Foto: BTA“.

| Nr. | Position | Motiv | Bildunterschrift (Vorschlag) |
|---|---|---|---|
| 1 | Titelbild | Prozession mit Kreuzen und Ikonen im Regen | Kreuzprozession mit Patriarch Daniil in Sofia. Foto: UOJ |
| 2 | in H3 Nr. 2 | Gläubige und Geistliche auf der Straße | Gläubige und Geistliche begleiten die Kreuzreliquie durch das Zentrum Sofias. Foto: UOJ. |
| 3 | in H3 Nr. 4 | Abt Johannes beim Vortrag | Abt Johannes vom Dreifaltigkeitskloster Buchhagen bei seinem Vortrag an der Universität des heiligen Clemens von Ochrid. Foto: UOJ. |
| 4 | in H3 Nr. 6 | Kathedrale bzw. Verehrung der Reliquie | Patriarchalkathedrale St. Alexander Newski, Sofia. Foto: UOJ. |

Optional unter Bild 4 eine kursive Deutungszeile im UOJ-Stil, z. B.: *„Was auf den Straßen begann, setzte sich im Gebet der versammelten Kirche fort.“*

---

## 6. Metadaten und Tags

- Rubrik: Mensch und Kirche
- Tags (vorhandene UOJ-Tags): Orthodoxie (`/de/tag/orthodoxie-1161`), Feiertag (`/de/tag/feiertag-1091`), Christentum (`/de/tag/christentum-1363`). Als neue Tags vorschlagen und als „neu“ kennzeichnen: Bulgarische Orthodoxe Kirche, Patriarch Daniil, Sofia, Kreuzerhöhung.
- Meta-Description = Lead.

---

## 7. Stil- und Sprachregeln

- Journalistischer Feature-Ton: anschaulich, ruhig und ehrfürchtig, nicht predigthaft, keine Floskeln („Es lässt sich festhalten“, „Zusammenfassend“).
- Ich-Perspektive nur im Einstieg und höchstens noch einmal im Schlussbogen. Sonst berichtend.
- Theologisch präzise nach orthodoxem Verständnis: Verehrung ≠ Anbetung; „wahrer Gott und wahrer Mensch“; Wandlung der Gaben „durch den Heiligen Geist“.
- Keine modernen Modewörter, keine Gendersprache, keine Anglizismen.
- Daten ausgeschrieben: „12. September 2026“.
- Neue deutsche Rechtschreibung. Vor der Abgabe auf Tippfehler prüfen.

---

## 8. Arbeitsschritte für den Executor

1. `uoj-artikel/grundtext.md` und diesen Plan vollständig lesen.
2. `uoj-artikel/artikel.md` schreiben: Kopf → Einstieg → 7 H3-Abschnitte → Schluss → Tags/Metadaten. Bilder, Pull-Quotes und der Mehr-zum-Thema-Kasten stehen als klar markierte Blöcke darin.
3. `uoj-artikel/artikel-cms.html` mit identischem Text im Markup aus Abschnitt 4 erzeugen.
4. Selbstprüfung mit Bash:
   - Wortzahl des Artikeltexts (ohne Meta) liegt zwischen 1.800 und 2.300: `wc -w`.
   - Genau 7 `<h3>`, 3–5 `<blockquote>`, 3 Inline-`<figure>`, 1 `<h2>` in der HTML-Datei: `grep -c`.
   - Jeder Inhaltspunkt aus Abschnitt 3 ist vorhanden: Namen und Daten per `grep` prüfen (Daniil, Helena, Kyrill, Chrysostomos, Damaskus, Abt Johannes, Buchhagen, Ochrid, Wulfila, Milev, 12. September, 13. September, 14. September, Vigil, Liturgie, Synod).
   - Keine Anführungszeichen um Aussagen, die im Grundtext indirekt stehen (Abschnitt 2, Regel 2).
5. Kurz berichten: Dateien, Wortzahl, Ergebnisse der Prüfungen, offene Punkte. Nicht committen.
