# Les Articles – Französischtrainer

Eine installierbare, iPhone-optimierte Lern-App (PWA) für die französischen Artikel.

## Funktionen

- **322 Übungsaufgaben** in fünf Levels: Grundlagen (160), Artikelwahl (32), Teilungsartikel (40), Besonderheiten (50), Transfer (40).
- Multiple Choice, freie Eingabe und französische Sprachausgabe als Hörtraining; auf dem jeweiligen Gerät muss dafür eine geeignete französische Stimme verfügbar sein.
- Adaptiver Wiederholungsplan: bei richtig und ohne Hinweis beantworteten Fragen 1 → 3 → 7 → 14 → 30 → 60 Tage; bei Fehlern Rückstufung und erneuter Versuch in der laufenden Einheit.
- 8, 12 oder 20 Aufgaben pro Runde; Training nur fälliger, neuer oder zuvor falscher Karten.
- Regelhinweise, Übersetzung jeder Aufgabe, Begründung nach der Antwort.
- Statistiken, Tagesziel, Lernserie, Schwierigkeitsschwerpunkte, lokale JSON-Sicherung und Wiederherstellung.
- Kein Login, keine Werbung, kein Tracking, keine externen Skripte. Daten bleiben lokal im Browser.
- Nach erster vollständiger Online-Ladung via GitHub Pages werden App-Dateien durch Service Worker für Offline-Nutzung gespeichert. Die Verfügbarkeit französischer Sprachsynthese offline ist geräteabhängig.
- Helles Eierschalen-Design (Standard), optional dunkles Farbschema.

## GitHub Pages – Installation

1. Auf github.com anmelden; ein neues Repository anlegen, z. B. `franzoesische-artikel`.
2. **Alle neun App-Dateien aus dieser ZIP-Datei entpacken und in das Stammverzeichnis des Repositories hochladen:** `index.html`, `app.js`, `questions.js`, `style.css`, `manifest.webmanifest`, `sw.js`, `icon-180.png`, `icon-192.png`, `icon-512.png`. (`README.md` ist optional.) Die ZIP-Datei allein reicht für GitHub Pages nicht.
3. GitHub → Repository → **Settings → Pages** → Source **Deploy from a branch** → Branch **main**, Folder **/(root)** → Save.
4. Die angezeigte Adresse öffnen; in der Regel `https://BENUTZERNAME.github.io/REPOSITORYNAME/`.
5. Auf dem iPhone mit **Safari** öffnen → **Teilen** → **Zum Home-Bildschirm** → hinzufügen.
6. Die App mindestens einmal online vollständig laden. Danach ist sie als installierte Web-App offline nutzbar. Wenn iOS Browserdaten löscht, können lokale Daten und Cache verloren gehen; daher unter Fortschritt eine JSON-Sicherung exportieren.

## Update

Dateien im GitHub-Repository ersetzen. Nach Änderungen an `app.js`, `questions.js` usw. muss in `sw.js` der Cache-Name (z. B. von `v1.0.0` auf `v1.0.1`) erhöht werden, damit offline eine frische Version ausgeliefert wird. Der Lernstand bleibt bei unveränderter Webadresse und gleichem Browserprofil normalerweise lokal erhalten; vorher eine Sicherung machen.

## Datenmodell / Grenzen

- Lernstand: `localStorage`, Schlüssel `fr-artikeltrainer-2026-v1`; Gerät/Browser/Origin-spezifisch; keine Synchronisierung.
- Eine Antwort **mit Hinweis** gilt als beantwortet, wird aber konservativ nur für 1 Tag eingeplant, nicht für ein länger werdendes Intervall.
- Fälligkeit hängt vom lokalen Datum ab, nicht von einer Cloudzeit.
- Die Intervallfolge ist eine didaktische Implementierungsentscheidung und **keine wissenschaftlich validierte individuelle Vorhersage**.
- Es werden keine automatischen Benachrichtigungen versendet.

## Primärquellen zu Grammatik und Didaktik

- OQLF – Artikel bestimmt: https://vitrinelinguistique.oqlf.gouv.qc.ca/fiche-gdt/fiche/26559614/determinant-defini
- OQLF – Artikel unbestimmt: https://vitrinelinguistique.oqlf.gouv.qc.ca/fiche-gdt/fiche/26559619/determinant-indefini
- OQLF – Teilungsartikel: https://vitrinelinguistique.oqlf.gouv.qc.ca/fiche-gdt/fiche/26559622/determinant-partitif
- OQLF – Verneinung: https://vitrinelinguistique.oqlf.gouv.qc.ca/23514/la-grammaire/les-determinants/determinants-indefinis/de-dans-une-phrase-negative
- OQLF – Verschmelzungen: https://vitrinelinguistique.oqlf.gouv.qc.ca/fiche-gdt/fiche/26506951/determinant-contracte
- OQLF – Adjektiv vor pluralem Nomen: https://vitrinelinguistique.oqlf.gouv.qc.ca/23496/la-grammaire/les-determinants/determinants-indefinis/des-devant-un-adjectif-antepose
- OQLF – h aspiré: https://vitrinelinguistique.oqlf.gouv.qc.ca/22203/la-prononciation/prononciation-de-certaines-lettres/la-prononciation-du-h-aspire
- Dunlosky et al., *Psychological Science in the Public Interest* (2013): DOI 10.1177/1529100612453266
- Carpenter et al., *Educational Psychology Review* (2012): DOI 10.1007/s10648-012-9205-z
- Forschung zur Kontextabhängigkeit gemischten Grammatiktrainings: DOI 10.1111/modl.70082
