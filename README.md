# Power-BI-Kundenprojekt

Projekt-Repo fuer genau einen Bericht. Angelegt aus `projekt-vorlage/` des Setup-Repos
`KI-Builder-generic`, das Template, Skills, Befehle und Werkzeuge liefert. Hier liegt nur, was zu
diesem Bericht gehoert. Das Repo ist privat.

| Pfad | Inhalt |
|---|---|
| `<PROJEKT>.pbip`, `.Report/`, `.SemanticModel/` | Bericht mit eigenem Modell gegen Lakehouse bzw. Excel; bei Datenquelle "bestehendes Semantic Model" nur `.pbip` + `.Report/`, live gebunden (entsteht mit `/init-project`) |
| `<PROJEKT>.report-build.json` | Manifest von `tools/report-build` |
| `intake/` | Anforderungen (`01_requirements.md`), Gates (`_status.yaml`), Wireframe, RE-Template |
| `glossar/kennzahlen.md` | Kennzahlenglossar |
| `design/<kunde>/` | Kunden-Branding aus dem Skill `template-branding` (Profil, Website-Bilder, Hintergruende, Theme) |
| `_brief/` | Arbeitsnotizen, Specs, Build-Skripte (Screenshots und Validierungsausgaben bleiben ungetrackt) |

## Arbeiten

1. Setup-Repo klonen und einrichten (siehe dessen `INSTALLATION.md`).
2. Im Setup-Repo `claude` starten und `/start <URL dieses Repos> [REQ-ID]` aufrufen. Claude klont
   das Repo nach `KI-Builder-generic/projekte/<Repo-Name>/`, aktiviert den Pre-Commit-Hook und
   setzt es als aktives Projekt.
3. Gearbeitet wird auf `feat/<REQ-ID>-<slug>`, gesichert mit `/save`, gemergt per Pull Request
   (`/review`).

## Datenschutz

- Nur Metadaten (TMDL, PBIR-JSON, Spalten-/Sheet-Struktur) und Aggregate, nie Zeilendaten —
  auch nicht in `_brief/`.
- `.pbix`, `.csv`, `.xlsx`, Datencaches (`cache.abf`) und Screenshots werden nicht committet
  (`.gitignore` und `.githooks/pre-commit`).
