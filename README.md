# CodeMirror Spell Checker
Spell checking so simple, you can set up in 60 seconds. It will highlight any misspelled words in light red. Works great in conjunction with other CodeMirror modes, like GitHub Flavored Markdown.

## Fork

This is a fork of [sparksuite's codemirror-spell-checker](https://github.com/sparksuite/codemirror-spell-checker).

Added fixes:
* Numbers aren't treated as spelling error.
* 27D isn't treated as a spelling error (for 27 dimensions).
* Switch to [`hunspell-en_US-large` dictionary](https://sourceforge.net/projects/wordlist/files/speller/2018.04.16/)
  via [NPM package hunspell-dict-en-us](https://www.npmjs.com/package/hunspell-dict-en-us)

![Screenshot](http://i.imgur.com/7yb5Nne.png)

## Install

Via [npm](https://www.npmjs.com/package/codemirror-spell-checker).
```
npm install @edemaine/codemirror-spell-checker --save
```

Via [bower](https://www.bower.io).
```
bower install @edemaine/codemirror-spell-checker --save
```

Via [jsDelivr](https://www.jsdelivr.com/package/npm/@edemaine/codemirror-spell-checker). *Please note, jsDelivr may take a few days to update to the latest release.*

```HTML
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@edemaine/codemirror-spell-checker/latest/spell-checker.min.css">
<script src="https://cdn.jsdelivr.net/npm/@edemaine/codemirror-spell-checker/latest/spell-checker.min.js"></script>
```

## Quick start
Once CodeMirror is installed and loaded, first provide CodeMirror Spell Checker with the correct CodeMirror function. Then, just set the primary mode to `"spell-checker"` and the backdrop mode to your desired mode. Be sure to load/require `overlay.min.js` if you haven't already.

```JS
CodeMirrorSpellChecker({
	codeMirrorInstance: CodeMirror,
});

CodeMirror.fromTextArea(document.getElementById("textarea"), {
	mode: "spell-checker",
	backdrop: "gfm" // Your desired mode
});
```

That's it!

## Customizing
You can customize the misspelled word appearance by updating the CSS. All misspelled words will have the `.cm-spell-error` class.

```CSS
.CodeMirror .cm-spell-error{
	/* Your styling here */
}
```

## Configuration

- **customWords**: Custom array of words that will not be designated as misspelled. Defaults to an empty array.

```JavaScript
// Most options demonstrate the non-default behavior
CodeMirrorSpellChecker({
	codeMirrorInstance: CodeMirror,
	customWords: ["CodeMirror", "GitHub"],
});
```
