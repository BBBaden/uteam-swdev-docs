# Dokumentationskonzept

Im Nachfolgenden wird das Dokumentationskonzept und die Arbeitsweise damit beschrieben.

## Grobüberblick

Die drei grossen Fragen, die sich in unterschiedlichen Situationen stellen, sind:

1. Was gilt (genau jetzt)?
2. Was hat in letzter Zeit geändert?
3. Wieso haben wir das so bestimmt?

Diese werden von unterschiedlichen Artefakten beantwortet:

| Frage                             | Artefakt      | Bemerkung                                                                         |
| --------------------------------- | ------------- | --------------------------------------------------------------------------------- |
| Was gilt (genau jetzt)?           | Die Website   | Gehostet auf GitHub Pages                                                         |
| Was hat in letzter Zeit geändert? | CHANGELOG.md  | Automatisch generiert aus Commit messages. Verbindet Commits und Issues per Link. |
| Wieso haben wir das so bestimmt?  | GitHub Issues | Fragen, Diskussionen, Entscheidungen bleiben transparent.                         |


## Normaler Workflow

- Dokumentation unterhalb `/docs` erstellen, die ein Issue bearbeitet. (Egal, ob neue Datei oder Modifikation.)
- Commit im Repo erstellen (Commit Message mit Referenz zu diesem Issue, s.u.).
- Commit ins Repo pushen
- GitHub schliesst das Issue (mit Referenz zu diesem Commit)
- Bei Bedarf: Neue Version der Doku releasen (s.u.)

## Format der Commit-Message

Die Commit-Message muss wie folgt formatiert sein (siehe Beispiel weiter unten):

- Erste Zeile im Format `${SCOPE}: ${SUMMARY}`
- Leerzeile
- Optional
    - längerer Text mit Details
    - Leerzeile
- `closes #issue`

Beispiel:

```text
n: Coding Conventions hinzugefügt

Diesen Text hier schreibe ich nur, damit das Beispiel auch den
optionalen Text berücksichtigt. Sonst könnte man das gar nicht zeigen.

Einen Mehrwert bringt dieser Text sonst wirklich nicht.

closes #3
```

### Scopes

Die folgenden *Scopes* werden in der Commit-Message berücksichtigt:

| Scope | Mnemonic     | Emoji | Verwendet für...                                                                                                                     |
| ----- | ------------ | ----- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **n** | NEU          | ✨     | Neu hinzugekommene Dokumentation                                                                                                     |
| **k** | KORREKTUR    | 🐛     | Typos, Klarstellung missverständlicher Formulierungen (ursprüngliche Aussageabsicht **unverändert**; früher so, heute immer noch so) |
| **c** | CHANGE       | ♻️     | Geänderte Dokumentation (ursprüngliche Aussageabsicht **verändert**; früher so, heute anders)                                        |
| **e** | ENTFERNT     | ❌     | Dokumentationsteil wurde enfernt                                                                                                     |
| **t** | TOOL         | 🛠️     | Arbeit am Tooling (unter der Haube)                                                                                                  |
| **h** | HOUSEKEEPING | 🧹     | Aufräumen                                                                                                                            |
| **s** | SONSTIGES    | ⚙️     | Sonstiges                                                                                                                            |


## Neues Release

- Jetzige Version anschauen (Startseite oder Changelog)
- Auf GitHub die Action "Release" ausführen und eine neue Versionsnummer vergeben
