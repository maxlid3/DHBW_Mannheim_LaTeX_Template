# Eine LaTeX-Vorlage für eine wissenschaftliche Arbeit an der DHBW Mannheim

Dieses GitHub Repository stellt eine Vorlage für eine wissenschaftliche Arbeit in der Fakultät Technik an der DHBW Mannheim dar und richtet sich primär an die [Leitlinien für die Bearbeitung und Dokumentation der Module Praxisprojekt I bis III Studienarbeit I / II  Bachelorarbeit der Fachkommission Technik Oktober 2021](https://www.dhbw.de/fileadmin/user_upload/Dokumente/Dokumente_fuer_Studierende/191212_Leitlinien_Praxismodule_Studien_Bachelorarbeiten.pdf).

Diese Vorlage ist inspiriert von [dieser ursprünglichen Vorlage](https://github.com/pfisterer/DHBW_LaTeX_Template) von [Dennis Pfisterer](https://github.com/pfisterer).

## Inhalte der Vorlage
Diese Vorlage enthält zentral folgendes:
- Eine Formatvorlage gemäß der Vorgaben in den [Leitlinien](https://www.dhbw.de/fileadmin/user_upload/Dokumente/Dokumente_fuer_Studierende/191212_Leitlinien_Praxismodule_Studien_Bachelorarbeiten.pdf)
- eine Titelseite
- einen Sperrvermerk
- eine ehrenwörtliche Erklärung
- eine Erklärung zur Verwendung von KI-Systemen
- darüber hinaus Beispiele zur Nutzung von:
    - Abkürzungen
    - Zitaten (IEEE)
    - dem Inhaltsverzeichnis

Diese Vorlage richtet sich an LaTeX-Anfänger, dennoch ist grundlegendes Wissen zur Nutzung von LaTex zu einem gewissen Maß vorausgesetzt. Ein schnelles Tutorial zu LaTeX-Grundlagen von Overleaf gibt es [hier](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes).

## Installationsanweisungen + VSCode Konfiguration
Falls nicht bereits eine eigene Umgebung zur Erstellung existiert gibt es hier einen schnellen Guide zum aufsetzen mit VSCode:

<details>
<summary>Zum Lesen ausklappen</summary>

1. Installation einer LaTeX-Distribution
    - Windows, Mac, Linux: [TexLive](http://www.tug.org/texlive/) (bei Linux oft bereits vorinstalliert)
    - Windows: [MikTex](http://www.miktex.org)
    - Mac: [MacTex](http://www.tug.org/mactex/index.html)
2. Installation von [VSCode](https://code.visualstudio.com/)
3. Installation des VSCode-Plugins [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
4. Bearbeiten der LaTeX-Workshop Konfiguration
    - VSCode Settings-JSON öffnen mit `Strg + Shift + P` -> `Preferences: Open User Settings (JSON)`
    - Die folgenden Code-Snippets sollten in die Settings.json eingefügt werden, je nachdem welche Funktionalität gewünscht ist
    - `latexmk` als einzigen Befehl zur Kompilierung festlegen (darauf achten, dass latexmk bei den latex.tools ganz oben steht oder alleine):
    ```json
    "latex-workshop.latex.tools": [
        {
        "name": "latexmk",
        "command": "latexmk",
        "args": [
            "-synctex=1",
            "-interaction=nonstopmode",
            "-file-line-error",
            "-pdf",
            "-outdir=%OUTDIR%",
            "-auxdir=build",
            "%DOC%",
        ],
        "env": {},
        }
    ],
    "latex-workshop.latex.recipes": [
        {
        "name": "latexmk 🔃",
        "tools": ["latexmk"],
        }
    ],
    ```
    - automatisches Kompilieren sobald eine Datei geändert (gespeichert) wurde:
    ```json
    "latex-workshop.latex.autoBuild.run": "onFileChange",
    ```
    - `latexindent` als Standard-Formatter festlegen und direkt beim Speichern einer Datei ausführen:
    ```json
    "latex-workshop.formatting.latex": "latexindent",
    "[latex]": {
        "editor.formatOnSave": true
    },
    ```
5. Jetzt kann man durch speichern von `.tex`-Dateien das LaTeX-Dokument kompilieren. Alternativ auch über den LaTeX-Tab -> Commands -> Build LaTeX project -> Recipe: latexmk 🔃
</details>

## Was angepasst werden muss
- Den Autor und Titel unter `BENUTZERDEFINIERTE BEFEHLE` in der `master.tex` anpassen
- Titelseite mit eigenen Daten befüllen
- Bibliografie in `literatur.bib` anpassen an eigene Quellen und Platzhalter-Quellen löschen
- Platzhalter-Abkürzung unter `ABKÜRZUNGEN` in der `master.tex` löschen und eigene Abkürzungen definieren

## Haftungsausschluss
Die in dieser Vorlage enthaltenen Informationen dienen ausschließlich allgemeinen Orientierungzwecken. Trotz sorgfältiger Erstellung wird keine Gewähr für Vollständigkeit, Richtigkeit oder Aktualität übernommen. Nutzer sind verpflichtet, alle Inhalte eigenständig auf sachliche, rechtliche und formale Richtigkeit zu prüfen. Für Folgen, die sich aus der Nutzung der Vorlage ergeben, wird keine Haftung übernommen.