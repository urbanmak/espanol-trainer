# GitHub – Anleitung: Dateien einspielen & deployen

## Einmalige Einrichtung (nur beim ersten Mal)

### Schritt 1 – Repository erstellen

1. Gehe auf **github.com** und melde dich an
2. Oben rechts auf **„+"** klicken → **„New repository"**
3. Eingaben:
   - **Repository name:** `espanol-trainer`
   - **Visibility:** ✅ Public (wichtig für kostenlose Pages)
   - Alles andere so lassen
4. **„Create repository"** klicken

---

### Schritt 2 – Alle Dateien hochladen

Du siehst jetzt eine leere Repository-Seite.

1. Auf **„uploading an existing file"** klicken
2. Alle 5 Dateien aus dem `espanol-trainer`-Ordner per **Drag & Drop** ins Fenster ziehen:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `vocab.json`
   - `vokabelliste.md`
3. Unten auf den grünen Button **„Commit changes"** klicken

---

### Schritt 3 – GitHub Pages aktivieren

1. Im Repository oben auf **„Settings"** klicken
2. Im linken Menü auf **„Pages"** klicken
3. Unter **„Source"**:
   - **„Deploy from a branch"** auswählen
   - Branch: **„main"**
   - Ordner: **„/ (root)"**
4. **„Save"** klicken
5. **2 Minuten warten**, dann erscheint oben eine grüne Box:

```
Your site is live at:
https://DEIN-USERNAME.github.io/espanol-trainer
```

Diese URL funktioniert auf **jedem iPhone weltweit** – einfach im Safari öffnen und zum Homescreen hinzufügen.

---

## Vokabeln aktualisieren (vocab.json ändern)

### Option A – Direkt auf GitHub im Browser (einfachste Methode)

1. Gehe zu deinem Repository auf github.com
2. Klicke auf die Datei **`vocab.json`**
3. Oben rechts das **Stift-Symbol** (✏️ „Edit this file") klicken
4. Änderungen vornehmen (neue Einträge hinzufügen, Fehler korrigieren)
5. Unten auf **„Commit changes"** klicken → kurze Beschreibung eingeben (z.B. „Unidad 6 ergänzt")
6. Auf **„Commit changes"** klicken

→ Die App aktualisiert sich beim nächsten Öffnen automatisch.

---

### Option B – Datei lokal bearbeiten & hochladen

1. `vocab.json` lokal in einem Texteditor öffnen (z.B. Notepad++, VS Code)
2. Änderungen vornehmen
3. Auf github.com: Repository öffnen → `vocab.json` anklicken
4. Oben rechts **„..."** → **„Upload file"** (oder einfach die Datei per Drag & Drop auf die Repository-Seite ziehen)
5. **„Commit changes"** klicken

---

## Neue Vokabeln einfügen – Format

Jeder Eintrag in `vocab.json` hat dieses Format:

```json
{ "es": "spanisches Wort", "de": "deutsche Übersetzung", "chapter": "6A" }
```

### Beispiel – Eintrag zu Unidad 6A hinzufügen:

Suche in `vocab.json` den Block `"6"` → `"vocab"`, dann ans Ende des Arrays einen neuen Eintrag einfügen:

```json
{ "es": "el diccionario", "de": "das Wörterbuch", "chapter": "6A" }
```

**Wichtig:** Jeder Eintrag außer dem letzten braucht ein Komma am Ende.

---

### Neue Unidad hinzufügen (z.B. Unidad 7)

Nach dem letzten Block (`"6": {...}`) einfügen:

```json
"7": {
  "title": "Título de la unidad",
  "topic": "Thema auf Deutsch",
  "vocab": [
    { "es": "primera palabra", "de": "erstes Wort", "chapter": "7A" },
    { "es": "segunda palabra", "de": "zweites Wort", "chapter": "7A" }
  ]
}
```

→ Die App erkennt die neue Einheit beim nächsten Start automatisch und zeigt sie als neue Karte.

---

## Nach jeder Änderung: App neu laden

Nach einem Commit auf GitHub:

1. **iPhone:** App auf dem Homescreen antippen
2. Kurz nach unten scrollen (Pull-to-refresh) → oder App schließen und neu öffnen
3. Die neuen Vokabeln sind sofort verfügbar

---

## Fehler in einer Übersetzung korrigieren

1. `vocab.json` auf GitHub öffnen (Stift-Symbol)
2. Mit **Strg+F** (Browser-Suche) das spanische Wort suchen
3. `"de":`-Wert korrigieren
4. Commit → fertig

---

## Übersicht: Alle Dateien im Repository

| Datei | Zweck | Wann ändern |
|-------|-------|-------------|
| `vocab.json` | Alle Vokabeln | Beim Ergänzen / Korrigieren von Vokabeln |
| `vokabelliste.md` | Lesbare Vokabelliste | Nach größeren Änderungen aktualisieren |
| `index.html` | Die App | Bei UI-/Funktionsänderungen |
| `manifest.json` | App-Name & Icon | Selten |
| `sw.js` | Offline-Support | Nie (außer bei technischen Updates) |

---

## Nächste geplante Erweiterungen

- Thematische Trainingseinheiten (z.B. „Alle Reflexivverben U1–U6")
- Mehrere Unidades kombinieren
- Grammatik-Modus (Verbkonjugationen)
- Schwache Vokabeln häufiger zeigen (Spaced Repetition)
