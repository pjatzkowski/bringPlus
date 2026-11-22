# bring+

Einkaufsvorlagen für verschiedene Szenarien, gemeinsame **Bausteine** und ein **Rezeptbuch**.
Listen gehen per Klick in die Bring!-App. Online unter https://pjatzkowski.github.io/bringPlus/

## Dateien

| Datei | Zweck |
|---|---|
| `index.html` | Die App |
| `daten.json` | Alle Listen, Bausteine, Rezepte (Austauschformat) |
| `listen/*.html` | Eine Seite pro Liste, die Bring! importiert |
| `fotos/*.jpg` | Artikel- und Rezeptfotos (entsteht automatisch) |
| `manifest.webmanifest`, `icon*.png`, `apple-touch-icon.png`, `sw.js` | App-Icon, Offline-Betrieb |

## Update einspielen (einmalig)

1. Alle Dateien und den Ordner `listen` per **Add file → Upload files** ins Repository laden → **Commit changes**.
2. 1–2 Minuten warten, App am PC mit **Strg + F5** neu laden, am Handy einmal ganz schließen und neu öffnen.
3. Die App übernimmt die neue Struktur automatisch. Was du auf einem Gerät noch nicht hochgeladen hattest, bleibt erhalten.

## Einkaufszettel (wie Bring)

Unten auf **📝 Zettel** tippen (am PC links „Einkaufszettel“ oder Taste **Z**).
- Oben eintippen und Enter – mehrere Artikel mit Komma trennen, Kategorie wird erkannt.
- **📥 Aus Liste übernehmen** oder in einer Vorlage **📝 Auf den Einkaufszettel**: Artikel abwählen, die noch da sind.
- Im Rezept: **📝 Zutaten auf Zettel**.
- **Antippen = abhaken.** Abgehakte rutschen ausgegraut nach unten, in der Reihenfolge, in der sie abgehakt wurden.
  Nochmal antippen holt sie zurück. **Erledigte entfernen** räumt auf.
- Mit GitHub-Sync sehen Anika und du denselben Zettel; bei geöffnetem Zettel gleicht die App alle 20 Sekunden ab.

## Mengen & Personen

- Jeder Artikel kann Menge und Einheit haben (✏️ → Menge/Einheit, oder direkt „500 g Hackfleisch“ eintippen).
- Listenmenü ⋯ → „Mengen gelten für … Personen“. Dann erscheint oben ein 👥-Regler, der alle Mengen umrechnet
  (Gramm sinnvoll gerundet, Stück/Dosen aufgerundet). „Menge fest“ nimmt einen Artikel von der Umrechnung aus.
- Rezepte mit Portionsangabe haben einen 🍽-Regler; Zettel, Bring und Druck übernehmen die umgerechneten Mengen.
- Kommt ein Artikel mit gleicher Einheit nochmal auf den Zettel, wird die Menge addiert.

## ✨ KI-Assistent, 🌱 Saisonal, „Passt jetzt“

- **✨ Liste mit KI** (Startseite, in jeder Liste, Taste **I**): beschreiben, was gebraucht wird – Claude erstellt die
  Liste (inkl. Mengen, Personen, Fleisch/Veggie-Gruppen) und zeigt sie zur Kontrolle, bevor sie angelegt wird.
  In einer Liste auch „Zu … ergänzen“. Braucht einen eigenen Claude-API-Schlüssel (⚙️ → KI-Assistent,
  console.anthropic.com, Abrechnung pro Nutzung, meist 1–5 Cent pro Anfrage). Ohne Schlüssel: „📋 Prompt kopieren“,
  in der Claude-App einfügen, Antwort über „📥 Antwort einfügen“ importieren.
- **🌱 Saisonal**: Saisonkalender (Deutschland, regional inkl. Lagerware) je Monat – antippen und auf Zettel/Liste legen.
  Funktioniert ohne KI.
- **Rezepte „✨ Passt jetzt“** (Standard-Sortierung): Bewertung + Jahreszeit + saisonale Zutaten, kürzlich Gekochtes
  rutscht nach hinten. Funktioniert ohne KI.
- **✨ Ideen** im Rezeptbuch: 5 neue Gerichte passend zu euren Bewertungen und der Saison, mit Zutaten,
  „Ins Rezeptbuch“ und Suche bei Chefkoch/Google.

## Personengruppen (z. B. Fleisch / Vegan-Vegetarisch)

Listenmenü ⋯ → „Personengruppen“, z. B. `🥩 Fleisch 6, 🌱 Vegan/Vegetarisch 2`. Jede Gruppe bekommt einen eigenen
Regler; Artikel werden per ✏️ → „Für“ einer Gruppe zugeordnet (sonst für alle). Im Textformat:
`Gruppen: 🥩 Fleisch 6, 🌱 Vegan/Vegetarisch 2` und bei Artikeln `| für Fleisch`.
Hinweis: Bring selbst kennt keine Gruppen – für getrennte Mengen den Einkaufszettel in bring+ nutzen.

## Listen als Text importieren / teilen

Neue Listen (z. B. von Claude im Chat erstellt) ohne GitHub übernehmen: Text kopieren →
bring+ → ＋ Neue Liste → **📥 Fertige Liste aus Text importieren** → Einfügen → Importieren.
Android: Text markieren → Teilen → bring+. Format:

```
bring+ Liste
# 🧀 Raclette-Abend
Art: Einkaufsliste            (oder Packliste / Baustein)
Personen: 4                   (optional)
## Milchprodukte
- 800 g Raclettekäse | in Scheiben
- 1 Pck. Raclette-Gewürz | fest
```
Gibt es schon eine Liste mit gleichem Namen, kann sie ersetzt werden. Umgekehrt: Listenmenü ⋯ → **📤 Als Text teilen**.

## Bausteine (Untergruppen)

Ein Baustein ist eine Liste mit gemeinsamen Artikeln, die andere Listen **einbinden**.
Beispiel: „🧺 Wocheneinkauf (Basis)“ steckt in „Woche mit Kindern“ und „Woche ohne Kinder“.
Die beiden Wochenlisten enthalten nur noch die Artikel, die wirklich nur dort hingehören.

- Artikel aus Bausteinen erscheinen mit einem kleinen Schild (z. B. „🧺 Wocheneinkauf (Basis)“).
- Bearbeiten ändert den Baustein → gilt für alle Listen.
- 👁 blendet einen Baustein-Artikel nur in dieser einen Liste aus.
- Neuer Artikel: unter „Speichern in“ wählen, ob nur diese Liste oder der Baustein.
- Bring bekommt immer die komplette Liste (eigene + Baustein-Artikel).

## Packlisten

„💼 Dienstreise“ ist eine Packliste: Artikel antippen = abhaken, „↺ Neu packen“ setzt alle Haken zurück.
Die Haken gelten nur auf dem jeweiligen Gerät, die Liste selbst wird synchronisiert. ✏️ bearbeitet einen Eintrag.
Eigene Packlisten: ＋ Neue Liste → Art „🧳 Packliste“.

## Kopieren & Verschieben (PC)

- **Kästchen** anklicken oder **Strg/⌘ + Klick**; **⇧ + Klick** markiert einen Bereich.
- **C** = kopieren nach …, **V** = verschieben, im Dialog **1–9** für die Zielliste, **Enter**.
- Oder Artikel links auf eine Liste **ziehen** (mit ⇧ = verschieben).
- **D** dupliziert die Liste, **N** neuer Artikel, **↑ ↓** bewegen, **?** zeigt alle Kürzel.
- Am Handy: „☑ Auswählen“ → Artikel antippen → Kopieren / Verschieben.

## Rezeptbuch

- **＋ Rezept** → Link einfügen. Überschrift, Bild und Beschreibung werden automatisch geladen
  (über den Vorschau-Dienst microlink.io; klappt es nicht, einfach selbst eintragen).
- Vegan/vegetarisch, Jahreszeit und Gang werden vorgeschlagen und lassen sich anpassen.
- **Sterne**: jede Person bewertet für sich, angezeigt wird der Durchschnitt.
  Den eigenen Namen fragt die App beim ersten Bewerten ab (⚙️ → „Dein Name“).
- **Filter**: vegan, vegetarisch, Kinder mögen’s, bis 30 Min, Jahreszeit (aktuelle ist markiert),
  ★ 4+, noch nie gekocht, Gang. Sortierung nach Bewertung, neu, A–Z, häufig gekocht, Zeit.
- **🛒 Zutaten in Bring** übergibt das Rezept direkt an Bring (klappt bei den meisten Rezeptseiten).
- **✅ Heute gekocht** zählt mit.
- **Instagram-Rezepte:** Link einfügen – bring+ versucht die Caption automatisch über den Link zu lesen.
  Klappt das nicht: **📷 Screenshot(s) der Caption wählen** (auch mehrere, wenn die Caption lang ist).
  Die Texterkennung läuft im Browser auf dem Gerät; beim ersten Mal lädt sie einmalig ein Sprachpaket (einige MB). Zutaten, Portionen, Zubereitung und
  Überschrift werden erkannt (bitte kurz prüfen). „🛒 Zutaten in Bring“ funktioniert danach wie bei Webseiten.
  Instagram-Bilder verschwinden nach einiger Zeit – am besten einen Screenshot als eigenes Foto hinterlegen.
- **Android:** im Browser „Teilen → bring+“ legt ein Rezept direkt an.
  **iPhone:** Link kopieren → ＋ Rezept → 📋.

## Rezepte drucken

Rezept öffnen → **🖨 Drucken**. Es erscheint ein Rezeptblatt mit Bild, Zutaten (zum Abhaken) und nummerierter
Zubereitung – ohne Werbung. Bei Webseiten lädt bring+ dafür die strukturierten Rezeptdaten der Seite
(dieselben, die auch Google und Bring nutzen); Instagram-Rezepte werden aus den gespeicherten Zutaten und der
Zubereitung aufgebaut. Optionen: Bild an/aus, große Schrift. Im Druckdialog geht auch „Als PDF speichern“.
iPhone: Falls „Drucken“ in der Home-Bildschirm-App nicht reagiert, die Seite in Safari öffnen → Teilen → Drucken.

## Abgleich Handy ↔ PC ↔ Anika (GitHub-Sync)

Mit einem GitHub-Token schreibt die App Änderungen selbst ins Repository. Kein Zip-Hochladen mehr,
und Bring bekommt nach 1–2 Minuten automatisch den neuen Stand.

1. Am PC https://github.com/settings/personal-access-tokens/new öffnen.
2. Name `bring+`, Ablaufdatum z. B. 1 Jahr.
3. **Repository access** → „Only select repositories“ → `bringPlus`.
4. **Permissions** → **Repository permissions** → **Contents** → „Read and write“.
5. **Generate token** → kopieren → in bring+ unter ⚙️ einfügen → **Speichern & testen**.
6. Auf jedem Gerät einmal eintragen (PC, dein Handy, Anikas Handy). Tipp: Schick dir den Token
   einmal selbst als Notiz, trag ihn ein und lösch die Notiz danach.

Danach synchronisiert die App beim Öffnen und kurz nach jeder Änderung (☁️ oben: grün = synchron).
Ändern zwei Geräte gleichzeitig etwas, werden die Änderungen zusammengeführt. Nur wenn derselbe
Artikel auf beiden Geräten geändert wurde, gewinnt die neuere Änderung.

**Sicherheit:** Der Token liegt nur im Browser des jeweiligen Geräts und darf nur dieses eine
Repository ändern. Geht ein Handy verloren: Token auf GitHub löschen und einen neuen anlegen.
Das Repository ist öffentlich, d. h. Listen und Rezepte sind für jeden mit der Adresse lesbar.

**Ohne Token** holt sich die App beim Öffnen den Stand vom Server und mischt ihn ein (nur lesen).
Hochladen geht dann wie bisher über ⚙️ → „Veröffentlichungs-Paket“.
