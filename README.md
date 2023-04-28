# AsciiDoc Presentation Template to use with reveal.js

## Initial setup
1. Install [Visual Studio Code](https://code.visualstudio.com/)
2. From extensions marketplace install [AsciiDoc](https://marketplace.visualstudio.com/items?itemName=asciidoctor.asciidoctor-vscode) and [AsciiDoc Slides](https://marketplace.visualstudio.com/items?itemName=flobilosaurus.vscode-asciidoc-slides) extenstions.
3. Open In Visual Studio Code `template.adoc` (or entire folder: this is even better)
4. Press Ctrl+Shift+P to open command pallette, find "AsciiDoc Slides: Open Slides In Browser"

Thats it!

## Presentation export
### To PDF
Most reliable way to have a PDF version of presentation is to open it in browser (like for normal slide show) and add *?print_pdf* to URL (please remove all hash symobols).

For example: instead of http://localhost:57951/#/_slide put http://localhost:57951/?print-pdf 

Use your browser printing capabilities to print presentation to PDF.

### To HTML
There are multiple options possible, but all of them are junk:

* Use export features of extension. They are available in command paletter (Cltr+Shift+P, "AsciiDoc Slides: Export...")

* Like in case with PDF use slide show and put _/export_ or _/export-inlined_ to URL

* Use corresponding _npm_ package from command line (will require node.js + npm installed):

Install required packages:
```
npm i @asciidoctor/reveal.js asciidoctor-kroki
```
Run the conversion:
```
npx asciidoctor-revealjs -r asciidoctor-kroki template.adoc
```
This way producing rather acceptable result. But can require extra HTML tweaking (more CSS & JavaScript). 

Please note it will require bunch of JS & CSS files from `node_modules` folder to operate correctly. But it can run presentation standalone with just browser.