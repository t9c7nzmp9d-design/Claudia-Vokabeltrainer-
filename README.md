# ¡Vamos! – Vokabeltrainer Spanisch

Webbasierter Vokabeltrainer für Schüler:innen (Klasse 9, 3.–4. Lernjahr Spanisch).
Läuft im Browser und lässt sich auf dem iPhone über Safari → „Teilen“ → „Zum Home-Bildschirm“ wie eine App installieren (PWA, funktioniert auch offline).

## Funktionen
- **6 Übungsarten:** Karteikarten, Schreiben (mit Akzent-Tasten á é í ó ú ñ ü ¿ ¡), Multiple Choice, Sprechen (Spracheingabe), Hören (Diktat), Mix
- **Sprachausgabe** (spanische Stimme des iPhones), auf Wunsch langsam
- **Spracheingabe** über die Web-Spracherkennung; Ersatz: Diktier-Mikrofon der iPhone-Tastatur
- **Lernkartei (Leitner-System):** Wörter kommen nach 1, 2, 4, 7, 14 Tagen wieder; falsch → zurück an den Anfang
- Fehlertolerante Prüfung: fehlender Akzent = „fast richtig“, Tippfehler wird erkannt, Artikel optional, mehrere richtige Lösungen
- Themenauswahl, Lernrichtung DE→ES / ES→DE, Fortschritt, Lernserie (🔥 Tage)
- **Eigene Vokabeln** aus dem Schulbuch eintragen (`deutsch = spanisch`, eine pro Zeile)

## Dateien
| Datei | Inhalt |
|---|---|
| `index.html` | die komplette App |
| `vokabeln.js` | Wortschatz (leicht erweiterbar) |
| `datenschutz.html` | Datenschutzhinweise, Widerruf der Spracherkennung, Daten löschen |
| `manifest.json`, `sw.js`, `icons/` | Installierbarkeit & Offline-Betrieb |

## Lokal testen
```
python3 -m http.server 8000
```
→ http://localhost:8000 öffnen. Fürs iPhone muss die App über **HTTPS** erreichbar sein (z. B. GitHub Pages).

## Festlegungen & Planung
- **Sprachvariante:** Spanisch aus Spanien (Stimme & Spracherkennung `es-ES`, Wortschatz z. B. *móvil*, *piso*, *deberes*)
- **Hosting:** GitHub Pages aus dem Branch `main`
- **Speicherung:** Lernstand nur auf dem jeweiligen Gerät (kein Konto, kein Server)
- **Offen:** Wortschatz passend zum Schulbuch (Lehrwerk & Lektion folgen)
- **Später:** Verbkonjugation, weitere Sprachen

## Datenschutz
Private, nicht-kommerzielle Seite – kein Tracking, keine Cookies, keine externen Ressourcen, kein Konto.
- Lernstand nur im `localStorage` des Geräts; „Alle Daten löschen“ in der App und auf der Datenschutzseite
- Sprachausgabe nur mit Stimmen, die auf dem Gerät laufen (`localService`)
- Spracherkennung im Browser (Audio geht an Apple/Google) ist **aus**, bis sie aktiv eingeschaltet wird
- `noindex`: die Seite wird nicht in Suchmaschinen aufgenommen
