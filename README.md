# Nyxveil

Ein eigenständiges Arcade-Survival-Spiel im Browser. Du steuerst einen
Energie-Kern per Wisch-Steuerung durch eine scrollende Neon-Arena, sammelst
Chroma-Splitter, entwickelst deinen Kern weiter und stellst dich alle
5 Wellen einem Overseer-Boss.

Komplette Eigenentwicklung: reines HTML/CSS/JavaScript mit Canvas-Grafik,
selbst synthetisierter Sound (Web Audio API), keine externen Bibliotheken,
keine externen Schriftarten oder Tracker, keine fremden Assets.

## Umfang

- **2 Bosstypen**, die sich alle 5 Wellen abwechseln: *Overseer* (Rundum-
  Salven, Rammangriff) und *Fracture* (beschwört Kristall-Diener, feuert
  langsame Ringe).
- **3 optische Zonen**, die sich alle 10 Wellen automatisch wechseln
  (Spectrum → Ember → Void) — reine Atmosphäre, aber ein sichtbares
  Zeichen für den erreichten Fortschritt.
- **2.5D-Look**: Schlagschatten unter Spieler/Gegnern/Powerups, Rauten-
  Bodenmuster statt flachem Raster, Bildschirm-Vignette — alles per
  Canvas simuliert, kein echtes 3D nötig, bleibt vollständig offline-fähig.
- **Boss-Momente**: Beim Erscheinen und beim Sieg gibt es Zeitlupe,
  Kamera-Zoom und ein groß eingeblendetes Namens-Banner.

## Spielen

Einfach `index.html` im Browser öffnen — läuft offline, ohne Installation.
Am Handy: zusätzlich über „Zum Home-Bildschirm" installierbar.

Eine ausführliche Anleitung ist im Spiel selbst über den Button
„Anleitung" auf dem Startbildschirm hinterlegt.

## Veröffentlichen über GitHub Pages

1. Neues Repository auf GitHub anlegen (z. B. `nyxveil`).
2. Alle Dateien aus dieser ZIP in das Repository hochladen
   (`index.html`, `impressum.html`, `datenschutz.html`, `README.md`).
3. Im Repository unter **Settings → Pages**:
   - Branch: `main`
   - Ordner: `/ (root)`
   - Speichern.
4. Nach ein bis zwei Minuten ist das Spiel unter
   `https://<dein-benutzername>.github.io/<repository-name>/` erreichbar.

## Vor der Veröffentlichung unbedingt prüfen

- **Impressum & Datenschutz**: `impressum.html` und `datenschutz.html`
  enthalten Platzhalter (rosa markiert). Bitte mit echten Angaben füllen
  und im Zweifel rechtlich prüfen lassen (siehe Hinweis am Ende beider
  Dateien) — das sind Vorlagen, keine Rechtsberatung.
- Beide Seiten sind vom Startbildschirm aus verlinkt.

## Technische Hinweise

- **Speicherstand**: Bestwelle, Highscore, Essenz, Upgrades und die Top-5-
  Bestenliste werden per `localStorage` direkt im Browser der Spielenden
  gespeichert — es gibt keinen Server und keine Datenübertragung.
- **Sound**: komplett selbst synthetisiert per Web Audio API (keine
  Sound-Dateien, kein Copyright-Risiko). Ein-/ausschaltbar über den
  „Sound"-Button auf dem Startbildschirm, Einstellung wird gespeichert.
- **Kombo-System**: Aufeinanderfolgende Kills ohne Treffer erhöhen einen
  Punkte-Multiplikator (bis zu +100 % bei 20er-Kombo). Ein Treffer setzt
  die Kombo zurück.
- **Vibration**: Bei Treffern vibriert das Gerät kurz, sofern der Browser
  die Vibration API unterstützt. iOS Safari (iPhone/iPad) unterstützt
  diese API grundsätzlich nicht — das Spiel funktioniert dort trotzdem
  vollständig, nur eben ohne Vibration.
- **Steuerung**: reine Wisch-/Drag-Steuerung (Touch und Maus), kein
  Keyboard nötig.

## Struktur

```
index.html        Das Spiel selbst (Single-File, keine Abhängigkeiten)
impressum.html     Impressum-Vorlage (Platzhalter ausfüllen)
datenschutz.html   Datenschutz-Vorlage (Platzhalter ausfüllen)
README.md          Diese Datei
```
