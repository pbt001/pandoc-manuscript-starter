## Recommended Sublime Text packages

* Citer
* LaTeXTools
* Pandoc

## Recommended Pandoc package settings

Note that `pdflatex` and `pandoc-citeproc` need to be on your path

Pandoc.sublime-settings:
```json
{
	"default": {

		"pandoc-path": "/usr/local/bin/pandoc",

		"transformations": {

			"HTML 5": {
				"scope": {
					"text.html.markdown": "markdown"
				},
				"syntax_file": "Packages/HTML/HTML.tmLanguage",
				"pandoc-arguments": [
					"-t", "html",
					"--filter", "/usr/local/bin/pandoc-citeproc",
					"--to=html5",
					"--no-highlight", 
				]
			},

			"PDF": {
				"scope": {
					"text.html": "html",
					"text.html.markdown": "markdown"
				},
				"pandoc-arguments": [
					"-t", "pdf", 
					
					"--pdf-engine=pdflatex",
					"--filter", "pandoc-citeproc"
				]
			},

			"Microsoft Word": {
				"scope": {
					"text.html": "html",
					"text.html.markdown": "markdown"
				},
				"pandoc-arguments": [
					"-t", "docx",  
					"--filter", "/usr/local/bin/pandoc-citeproc"
				]
			},

		},
		"pandoc-format-file": ["docx", "epub", "pdf", "odt", "html"]

	}

}
```
