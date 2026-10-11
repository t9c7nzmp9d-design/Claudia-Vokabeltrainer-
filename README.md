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
- **Vokabellisten scannen:** über „Text scannen“ des iPhones (Live Text, läuft auf dem Gerät) – die App trennt Spanisch/Deutsch automatisch, erkennt die Spaltenreihenfolge und zeigt eine Vorschau zum Korrigieren
- **Datensicherung:** Lernstand, eigene Vokabeln & Einstellungen als Datei speichern (iPhone: Teilen → „In Dateien sichern“) und wieder laden
- **Eigene Vokabeln** abtippen oder einfügen (eine pro Zeile, z. B. `el perro = der Hund`)

## Dateien
| Datei | Inhalt |
|---|---|
| `index.html` | die komplette App |
| `grundwortschatz.js` | Grundwortschatz Lernjahr 1 & 2 (ca. 270 Wörter, 18 Themen) |
| `vokabeln.js` | Wortschatz Lernjahr 3+ (leicht erweiterbar) |
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
- **Lehrwerk:** *Encuentros hoy* 1 & 2 (Cornelsen). Der eingebaute Grundwortschatz ist eine eigene Zusammenstellung, thematisch angelehnt – **keine Kopie der Buchlisten** (Urheberrecht). Die exakten Buchvokabeln werden privat auf dem Gerät eingescannt („📷 Eigene“).
- **Später:** Verbkonjugation, weitere Sprachen

## Datenschutz
Private, nicht-kommerzielle Seite – kein Tracking, keine Cookies, keine externen Ressourcen, kein Konto.
- Lernstand nur im `localStorage` des Geräts; „Alle Daten löschen“ in der App und auf der Datenschutzseite
- Vorlesen & Spracherkennung über die Browser-Dienste (iPhone: Apple; Chrome: bevorzugt Google-Stimmen) – auf der Datenschutzseite erklärt
- `noindex`: die Seite wird nicht in Suchmaschinen aufgenommen
