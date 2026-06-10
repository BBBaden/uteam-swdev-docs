# uteam-swdev-docs

Dokumentation für das U-Team *Software Development*.

## Wichtige Links

- [Deployte Seite](https://bbbaden.github.io/uteam-swdev-docs/)
- Konzept zur Dokumentation: [Markdown Source](./docs/doku-konzept.md), [live](https://bbbaden.github.io/uteam-swdev-docs/doku-konzept/)


## Lokale Entwicklungsumgebung aufsetzen

<div style="border:2px solid hsl(210, 100%, 40%); background: hsl(210, 50% 60%);padding:2rem;border-radius:4px;">

**ℹ️ Information**

Eine lokale Umgebung braucht nur aufgesetzt werden, wenn ...
- am Mechanismus selbst entwickelt wird.
- eine lokale Vorschau der Seiten gewünscht ist.
- eine lokale Vorschau des CHANGELOG.md gewünscht ist.

</div>

### MkDocs aufsetzen

- Python venv erstellen, z.B. `uv venv --with-pip` oder `python -m venv create .venv`
- Python venv aktivieren: `. ./venv/Scripts/activate` oder `.\.venv\Scripts\activate`
- Pakete installieren: `uv sync` oder `pip install -r requirements.txt`
- Webseite lokal ansehen: `mkdocs serve`


Für Details zu MkDocs: [mkdocs.org](https://www.mkdocs.org).

### git-cliff aufsetzen

Offizielle Webseite: [git-cliff.org](https://git-cliff.org/).

- Installation unter Windows: `winget install --source winget -e orhun.git-cliff`
- Neues Changelog erstellen: `git-cliff -o CHANGELOG.md`
