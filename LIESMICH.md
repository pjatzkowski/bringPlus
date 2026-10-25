# bring+

Einkaufsvorlagen für verschiedene Szenarien (Woche mit/ohne Kinder, Lange Fahrt, Camping …),
die per Klick in die Bring!-App übernommen werden.

## Inhalt des Ordners

| Datei | Zweck |
|---|---|
| `index.html` | Die App (läuft auch ohne Internet) |
| `manifest.webmanifest`, `icon*.png`, `apple-touch-icon.png`, `icon.svg` | App-Name und Logo für den Homescreen |
| `sw.js` | Offline-Cache, wenn die App online liegt |
| `daten.json` | Alle Listen und Kategorien (Austauschformat, mit jedem Texteditor lesbar) |
| `listen/*.html` | Eine Seite pro Liste, die Bring! importiert |

## Warum ein Online-Ordner?

Bring! übernimmt Listen von außen nur über denselben Weg wie Rezepte aus dem Internet:
Bring ruft eine **öffentliche Web-Adresse** auf und liest dort die Zutaten im
schema.org-Rezeptformat (JSON-LD, Feld `recipeIngredient`). Genau solche Seiten erzeugt
bring+ in `listen/`. Eine Datei, die nur auf dem Handy liegt, kann der Bring-Server
nicht abrufen. Außerdem zeigen iPhone und Android ein eigenes App-Icon nur für Web-Adressen an.

Ohne Online-Ordner funktioniert alles andere trotzdem, und der Knopf **📋 Text**
teilt/kopiert die Liste (ein Artikel pro Zeile).

## Einrichtung mit GitHub Pages (kostenlos, ca. 10 Minuten, einmalig)

1. Auf github.com ein Konto anlegen und ein neues, **öffentliches** Repository erstellen, z. B. `bringplus`.
2. „Add file → Upload files“: den **gesamten Inhalt** dieses Ordners hochladen (inkl. Ordner `listen`).
3. Settings → Pages → „Deploy from a branch“, Branch `main`, Ordner `/ (root)` → Save.
4. Nach 1–2 Minuten ist die App erreichbar unter `https://<dein-name>.github.io/bringplus/`.
5. Auf dem Handy diese Adresse öffnen und zum Homescreen hinzufügen:
   - **iPhone (Safari):** Teilen-Symbol → „Zum Home-Bildschirm“
   - **Android (Chrome):** ⋮-Menü → „Zum Startbildschirm hinzufügen“ / „App installieren“

Hinweis: Ein öffentliches Repository bedeutet, dass die Einkaufslisten im Internet lesbar sind
(wer die Adresse kennt). Für Einkaufslisten meist unkritisch – nichts Privates hineinschreiben.

## Listen ändern

- **Am Handy:** direkt in der App. Gespeichert wird im Browser des Geräts.
- **Am Computer:** `index.html` im Browser öffnen (Doppelklick genügt) oder die GitHub-Pages-Adresse,
  ⚙️ → „Listen importieren“ → `daten.json` wählen, bearbeiten.
  Alternativ `daten.json` direkt im Texteditor ändern – das Format ist selbsterklärend.

### Änderungen für Bring veröffentlichen

1. In der App: ⚙️ → **Veröffentlichungs-Paket erstellen** → `bringplus-veroeffentlichen.zip`.
2. Zip entpacken und `daten.json` sowie den Ordner `listen` ins GitHub-Repository hochladen (überschreiben).
3. Auf dem Handy erscheint beim nächsten Öffnen „Neuere Listen auf dem Server – Laden“.

Wurde eine Liste geändert, aber noch nicht veröffentlicht, zeigt die App einen gelben Hinweis.

## Import in Bring

„🛒 In Bring importieren“ öffnet die Bring!-App mit der Liste wie ein Rezept.
Dort lassen sich vor dem Hinzufügen einzelne Artikel abwählen, z. B. was noch im Haus ist.

## Format von daten.json

```json
{
  "categories": [{ "id": "obst", "name": "Obst & Gemüse", "icon": "🍎" }],
  "lists": [{
    "id": "woche-mit-kindern", "name": "Woche mit Kindern", "emoji": "👨‍👩‍👧",
    "items": [{ "id": "a1", "name": "Äpfel", "spec": "Elstar oder Pink Lady", "cat": "obst" }]
  }]
}
```

Die `id` einer Liste bestimmt den Dateinamen in `listen/` und bleibt beim Umbenennen gleich.
