# uteam-swdev-docs

Dokumentation für das U-Team *Software Development*.

## Wichtige Links

- [Konzept zur Dokumentation](./docs/doku-konzept.md)


## Lokale Entwicklungsumgebung aufsetzen

<div style="border:2px solid hsl(210, 100%, 40%); background: hsl(210, 50% 60%);padding:2rem;border-radius:4px;">

**ℹ️ Information**

Eine lokale Umgebung braucht nur aufgesetzt werden, wenn ...
- am Mechanismus selbst entwickelt wird.
- eine lokale Vorschau der Seiten gewünscht ist.

</div>

- Python venv erstellen, z.B. `uv venv --with-pip` oder `python -m venv create .venv`
- Python venv aktivieren: `. ./venv/Scripts/activate` oder `.\.venv\Scripts\activate`
- Pakete installieren: `uv sync` oder `pip install -r requirements.txt`
- Webseite lokal ansehen: `mkdocs serve`


Für Details zu MkDocs: [mkdocs.org](https://www.mkdocs.org).
