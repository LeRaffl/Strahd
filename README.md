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
    sessions/               # Session-Summaries
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
| [Lazar](charaktere/lazar/charakterbogen.md) | Andi | Tabaxi | Mönch |
| [Major Sempft](charaktere/major-sempft/charakterbogen.md) | Felix | Halbling | Paladin |
| [Moxi](charaktere/moxi/charakterbogen.md) | Svenja | Goblin | Jäger |

## Kampagnen
| Kampagne | Status | Sessions |
|----------|--------|----------|
| [Requiem of Wings](kampagnen/requiem-of-wings/party.md) | One-Shot (abgeschlossen) | 1 |

## Biblo (Web-Interface)
Biblo läuft als Single-Page-App in `index.html`, deployed als GitHub Page. Der Web-Chat nutzt **Claude mit Tool-Use**: Biblo bekommt den Manifest-Index und ruft über `read_file` gezielt einzelne Dateien nach, wenn eine Frage Detail braucht. So bleibt der Initial-Prompt klein und das Archiv kann beliebig wachsen.
