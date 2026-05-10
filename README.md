# Kampagnen-Archiv
**System:** D&D 5e
**Librarian:** Biblo — siehe `index.html` für das Web-Interface

---

## Struktur

```
charaktere/                 # GLOBAL — Charaktere sind kampagnen-übergreifend
  <name>/
    charakterbogen.md       # Stats, Klasse, Spells, Ausrüstung
    persoenlichkeit.md      # Traits, Voice, Reaktionsmuster
    beziehungen.md          # Beziehungen pro Kampagne (mit Dimensionen)

regeln/                     # GLOBAL — Regel-Bibliothek
  spells/                   # SRD-5.1-Spell-Texte + wer castet sie
  features/                 # Class- und Racial-Features
  magic-items/              # Magische Gegenstände

kampagnen/
  <kampagne>/
    party.md                # Wer ist dabei, Level, Status
    _kontext/welt.md        # Setting, Fraktionen
    _kontext/timeline.md    # Timeline der Kampagne
    sessions/               # Kuratierte Session-Summaries
    transcripts/            # Roh-Transkripte / händische Mitschriften (last-resort)
    npcs/                   # NPCs dieser Kampagne
    orte/                   # Schauplätze dieser Kampagne

_kontext/manifest.md        # Index für Biblo (wird per Tool-Use geladen)
_templates/                 # Blank-Templates für neue Dateien
index.html                  # Biblo Web-UI
```

## Charaktere
| Charakter | Spieler | Spezies | Klasse |
|-----------|---------|---------|--------|
| [Shii Take](charaktere/shii-take/charakterbogen.md) | Raffi | Human | Druide |
| [Nia Sommerfeld](charaktere/nia-sommerfeld/charakterbogen.md) | Raffi | Human | Bard (College of Lore) |
| [Lazar](charaktere/lazar/charakterbogen.md) | Andi | Tabaxi | Mönch |
| [Major Sempft](charaktere/major-sempft/charakterbogen.md) | Felix | Halbling | Paladin |
| [Moxi](charaktere/moxi/charakterbogen.md) | Svenja | Goblin | Jäger |

## Kampagnen
| Kampagne | Status | Sessions |
|----------|--------|----------|
| [Requiem of Wings](kampagnen/requiem-of-wings/party.md) | One-Shot (abgeschlossen) | 1 |

## Biblo (Web-Interface)
Biblo läuft als Single-Page-App in `index.html`, deployed als GitHub Page. Der Web-Chat nutzt **Claude mit Tool-Use**: Biblo bekommt den Manifest-Index und ruft über `read_file` gezielt einzelne Dateien nach, wenn eine Frage Detail braucht. So bleibt der Initial-Prompt klein und das Archiv kann beliebig wachsen.

## Biblo lokal via Claude Code / Codex
Alternativ kannst du Biblo direkt im Repo nutzen — über dein eigenes Claude- oder ChatGPT-Abo, ohne API-Kosten.

Setup:
1. **Repo klonen** (privat — du musst als Collaborator hinzugefügt sein).
2. **Agent installieren:** [Claude Code](https://docs.claude.com/claude-code) (`npm install -g @anthropic-ai/claude-code`) oder [Codex CLI](https://github.com/openai/codex).
3. **Im Repo starten:** `claude` bzw. `codex`. Beide laden automatisch `CLAUDE.md` (resp. `AGENTS.md`, ist ein Symlink) und verhalten sich entsprechend als Biblo.

Typische Nutzung:
- **Nachschlagen am Spieltisch** — "Was kann Lazars Mönchsklasse auf Level 3?", "Welche NPCs hatten wir in Session 1?"
- **Session loggen** — Erzähl die Session, paste eine Apple-Notes-Mitschrift oder ein Transkript rein. Biblo strukturiert nach `_templates/session.md` und legt die Datei an. Audio muss vorher transkribiert werden (Apple Voice Memos / MacWhisper).
- **Char-Building** — neue Spells/Items recherchieren und im Archiv anlegen.

## Transkripte / Mitschriften
Roh-Material aus den Sessions liegt in `kampagnen/<kampagne>/transcripts/`. Das sind Voll-Transkripte oder händische Notizen — ungekürzt, im Gegensatz zu den kuratierten `sessions/<nr>.md`. Biblo greift hier nur als Last-Resort drauf zu (wenn die kuratierte Session-Datei eine Frage nicht abdeckt) oder wenn explizit danach gefragt wird. Workflow nach einer Session:

1. Transkript in `kampagnen/<kampagne>/transcripts/<nr>-<slug>.md` ablegen — Template: `_templates/transcript.md`.
2. Eintrag in `_kontext/manifest.md` ergänzen, sonst sieht Biblos Tool-Use die Datei nicht.
3. Optional: Biblo bitten, die kuratierte `sessions/<nr>.md` aus dem Transkript nachzuziehen.
