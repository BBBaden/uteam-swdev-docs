# Test Framework für C\#

Wir haben beschlossen, dass wir in allen Modulen, die das *U-Team Softwareentwicklung* wartet, das selbe Framework verwenden wollen.
Wir haben uns für das Framework **MSTest** entschieden. Die Hauptgründe dafür:

- Stand Dezember 2025 ist dies das Framework, das aktuell in den Modulen am meisten verwendet wird. (kleinster Änderungsaufwand)
- Wir sind bisher nicht an irgendwelche technischen Limiten gestossen, die MSTest als Framework ausschliessen würden oder dies nahelegen.


## Vorgehen in VisualStudio

- Projektmappe (Solution) öffnen
- Projekt hinzufügen
    - Typ MSTest
    - Vorschlag für Name: `${PROJECT}.Tests` (z.B. getestetes Projekt = `Calculator` → Test = `Calculator.Tests`)
- Projektabhängigkeit hinzufügen (Test-Projekt hängt ab vom getesteten Projekt)
