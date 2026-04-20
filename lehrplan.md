# Lehrplan: Schülerpraktikum — Claude + Code + Live-Video
**Datum:** Donnerstag  
**Themen:** APIs, HTML/JS, Claude als Pair-Programmer, vMix-Integration

---

## Prinzip des Tages

Der Schüler soll am Ende sagen können:
> "Ich habe heute selbst Code geschrieben — und der läuft live im Sendebild."

Claude ist dabei **kein Zauberer**, der fertige Lösungen ausspuckt, sondern ein **Gesprächspartner beim Denken**: Man erklärt, was man will, Claude schlägt vor, man hinterfragt, man versteht.

---

## Vorbereitung (vor dem Praktikumstag)

- [ ] Repo `adp-Lab/abfahrtsmonitor` auf GitHub anlegen
- [ ] `index.html` reingepusht, GitHub Pages aktiviert
- [ ] Laufende URL notieren: `https://adp-lab.github.io/abfahrtsmonitor/`
- [ ] vMix auf einem Rechner einsatzbereit
- [ ] Claude Code oder claude.ai im Browser offen

---

## Tagesablauf

### Block 1 — Ankommen & Orientierung (ca. 30 min)

**Ziel:** Schüler weiß, was heute passiert und warum es interessant ist.

Gespräch:
- Was interessiert dich an KI? Was hast du schon ausprobiert?
- Heute machen wir etwas, das direkt nützlich ist: einen Live-Abfahrtsmonitor
- Und nachmittags: der läuft im Sendebild einer TV-Produktion

Zeigen:
- Die fertige App im Browser öffnen — Haltestelle suchen, Abfahrten sehen
- Auf dem Handy öffnen → "das ist bereits online, überall erreichbar"
- Repo auf GitHub zeigen → "das ist der gesamte Code, eine Datei"

---

### Block 2 — Code verstehen mit Claude (ca. 60–75 min)

**Ziel:** Schüler versteht, wie die App funktioniert — nicht auswendig, sondern strukturell.

**Methode:** Code-Abschnitt zeigen → Schüler erklärt, was er vermutet → Claude fragen.

Abschnitte der Reihe nach:
1. **HTML-Struktur** — Was sind `<input>`, `<table>`, `<div>`? Was sieht man davon im Browser?
2. **CSS-Variablen** — Was ist `--bg`? Wo taucht es auf? Warum macht das Sinn?
3. **`fetchSuggestions()`** — Was ist eine API? Was ist JSON? API im Browser direkt aufrufen: `https://v6.db.transport.rest/locations?query=Berlin`
4. **`renderDepartures()`** — Wie kommt ein API-Objekt in eine Tabellenzeile?
5. **Auto-Refresh** — Warum `setInterval`? Was passiert alle 30 Sekunden?

Claude-Prompts zum Üben:
- *"Erkläre mir diesen Code-Abschnitt wie ich 16 bin und noch nie programmiert habe"*
- *"Was passiert, wenn ich `REFRESH_MS` auf 5000 setze?"*
- *"Warum steht da `esc(str)` — was würde passieren wenn wir das weglassen?"*

---

### Block 3 — Eigene Änderung (ca. 60 min)

**Ziel:** Schüler ändert etwas selbst — mit Claude als Hilfe.

**Stufe A (Einstieg / wenig Erfahrung):**
- Farbe des Hintergrunds ändern
- Anzahl der Abfahrten von 20 auf 10 reduzieren
- Titel der Seite ändern
- Refresh-Intervall ändern und Unterschied beobachten

**Stufe B (etwas Erfahrung):**
- Eine neue Tabellenspalte hinzufügen: "Produkt" (Bus / U-Bahn / S-Bahn)
- Emoji-Icons je nach Verkehrsmittel anzeigen (🚌 🚇 🚊 🚂)
- Den Countdown-Balken farblich ändern

**Stufe C (fortgeschritten):**
- Eine zweite Haltestelle gleichzeitig anzeigen (zwei Tabellen)
- Filterbuttons: nur Bus, nur U-Bahn, etc.
- Abfahrten nach Verspätung sortieren

Vorgehensweise für jede Änderung:
1. Schüler beschreibt, was er will
2. Gemeinsam: Wo im Code muss das hin?
3. Claude fragen: *"Wie würde ich in diesem Code X einbauen?"*
4. Schüler tippt die Änderung selbst
5. Browser-Reload → Ergebnis sehen

---

### Block 4 — Live schalten (ca. 20 min)

**Ziel:** Schüler pusht seinen eigenen Fork auf GitHub Pages.

Schritte live durchführen:
1. GitHub-Account anlegen (falls nicht vorhanden)
2. Repo forken: `adp-Lab/abfahrtsmonitor` → eigener Account
3. GitHub Pages aktivieren: Settings → Pages → main branch
4. URL aufrufen: `schuelername.github.io/abfahrtsmonitor/`
5. Auf dem Handy öffnen → fertig

**Botschaft:** *"Das hast du heute selbst gebaut. Das ist jetzt im Internet."*

---

### Block 5 — Video-Technik: Überblick (ca. 45–60 min)

Je nach Interesse und Kenntnisstand:

- Was ist ein Videoswitcher? (ATEM Mini als Beispiel zeigen)
- Was macht vMix? (Mehrere Quellen, Ausgabe, Overlays)
- Was ist Bitfocus Companion? (Hardware-Controller → Software-Aktionen)
- Was ist H2R Graphics? (Browser-basierte Grafiken im Livebild)

Grundprinzip erklären:
> "Alles, was ein Browser anzeigen kann, kann auch ins Sendebild."

---

### Block 6 — Integration: Abfahrtsmonitor im Sendebild (ca. 45–60 min)

**Das Wow-Moment des Tages.**

**Setup:**
1. vMix öffnen
2. "Add Input" → "Web Browser"
3. URL eingeben: `https://adp-lab.github.io/abfahrtsmonitor/?stop=8011160&name=Berlin+Hbf`
4. Als Overlay auf ein Kamerabild legen

**Diskussion:**
- Was würde man in einer echten Produktion damit machen?
- Welche anderen Daten könnte man live einblenden?
  - Sportergebnisse
  - Wetter
  - Social-Media-Zähler
  - Strompreise, Börsenkurse

**Optional — eigene Grafik:**
- Claude generiert eine animierte HTML Lower Third
- In vMix als zweiten Browser-Input laden
- Zwei selbst gebaute Overlays gleichzeitig im Sendebild

---

### Block 7 — Abschluss & Ausblick (ca. 20 min)

Rückblick:
- Was hast du heute gemacht? (Schüler erzählt)
- Was hat funktioniert, was war schwierig?

Ausblick — was wäre als nächstes möglich:
- Python-Version mit Flask (lokaler Server, mehr Kontrolle)
- Datenbankanbindung: Abfahrten speichern, Statistiken
- Eigene Grafik-Templates für Live-Produktion
- Claude API direkt ansprechen (eigene KI-Anwendung bauen)

**Mitgabe:**
- Link zum eigenen GitHub-Repo
- Link zur offiziellen Doku: https://v6.db.transport.rest/api.html
- Claude: claude.ai (kostenloser Zugang)

---

## Tipps für die Vermittlung

**Falls der Schüler keine Programmiererfahrung hat:**
- Nicht in Code-Syntax verlieren — Konzepte first: "API ist wie ein Kellner"
- Änderungen nur in der Konfigurationszone (obere Konstanten in `<script>`)
- Erfolgserlebnisse wichtiger als Verständnistiefe

**Falls der Schüler schon programmiert:**
- Früher zu Block 3 Stufe B/C wechseln
- JavaScript-Besonderheiten ansprechen (async/await, fetch, DOM)
- Gemeinsam eine eigene Feature-Idee entwickeln und umsetzen

**Mit Claude umgehen:**
- Claude macht Fehler — das ist normal und lehrreich
- Immer hinterfragen: "Verstehe ich, was Claude hier vorschlägt?"
- Claude als Gesprächspartner, nicht als Antwortmaschine

---

## Materialien

| Was | Wo |
|-----|-----|
| Live-App | https://adp-lab.github.io/abfahrtsmonitor/ |
| Source-Code | https://github.com/adp-Lab/abfahrtsmonitor |
| DB-API Doku | https://v6.db.transport.rest/api.html |
| Claude | https://claude.ai |
