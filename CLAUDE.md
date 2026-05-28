# Augenblick Landing – Projektdokumentation

## Übersicht
Statische Landingpage für die Augenblick-Meditations-App.
Single-File-HTML, kein Build-Schritt, kein Framework.

**Geplante Live-URL:** https://augenblick.tinnituspraxis-seedorf.de
**App-Repo (verlinkt):** https://github.com/Boris1900/Meditation-App
**Praxis-Hauptseite:** https://www.tinnituspraxis-seedorf.de

## Dateistruktur
```
AugenblickLanding/
├── index.html             # komplette Landingpage
├── gong.png               # Gong mit Halterung (Buddha-Modus)
├── gong_ohne_halter.png   # Gong ohne Halterung (Farbmodus) + Logo im Hero
├── background.jpg         # Buddha-Hintergrund (für ersten Slide)
├── screen-menu.png        # Screenshot des App-Menüs (letzter Slide)
├── CNAME                  # Subdomain für GitHub Pages
└── CLAUDE.md              # Diese Datei
```

## Aufbau der Seite
1. **Hero:** Gong-Logo + "Augenblick" + Untertitel + Phone-Mockup mit Slider (6 Ansichten)
2. **Features:** 5 Karten (Klangschale, Hintergrund, Bildschirm, Zwischen-Gong, Kostenlos)
3. **Download:** Zwei Boxen (Android-APK + iPhone-PWA-Anleitung)
4. **Footer:** Zeile mit Link zur Praxis

## Phone-Mockup-Slider
Sechs Slides, durchblätterbar per Pfeile / Dots / Touch-Swipe:
1. Buddha-Bild + Original-Gong + Timer 30:00
2. Schwarz + Gong ohne Halterung + Timer
3. Dunkelblau + Gong ohne Halterung + Timer
4. Grasgrün + Gong ohne Halterung + Timer
5. Warmes Gelb + Gong ohne Halterung + Timer
6. Screenshot des App-Menüs

## APK-Download
Der APK-Button im "Android"-Block holt die neueste Version automatisch
via GitHub-API (`releases/latest`). Wenn die API ausfällt, greift der
hardgecodete Fallback-Link aus dem HTML.

**Wichtig:** Der dynamische Link sucht im Release nach einem Asset, dessen
Name mit `Augenblick-` beginnt und auf `.apk` endet. Wenn das Naming geändert
wird, muss die Suchlogik in `index.html` angepasst werden.

## iPhone-Installation
Aktuell verlinkt der iPhone-Button auf `https://boris1900.github.io/Meditation-App/`,
wo die PWA gehostet wird. Nutzer öffnen das in Safari → Teilen → "Zum Home-Bildschirm".

## Deployment
- GitHub Pages serviert direkt aus dem `main`-Branch
- Subdomain bei All-Inkl. per CNAME-Eintrag auf `boris1900.github.io`
- CNAME-Datei im Repo teilt GitHub mit, für welche Domain die Seite ausgeliefert werden soll

## Arbeitsregel
**Immer erst fragen bevor größere Änderungen umgesetzt werden.**
Texte, Farben, Reihenfolge – das alles ist Boris-Entscheidung.

## Kontext
- Zielgruppe: Freunde und Interessierte, kein Massenmarketing
- Kein E-Mail-Capture, freier Download
- Mobile-first, aber Desktop-Version sieht gleich aus (kein Overlay)
- Boris: Heilpraktiker, beurteilt visuell, kein Entwickler
