# Roadmap

## 1.4.6

- [ ] Update code style so that it matches what most JavaScript code uses.
- [ ] Update DOM -> BBCode converter to convert directly to tokens used by the BBCode parser.
- [ ] Add option to disable pasting, plain text pasting and allow a callback to filter the pasted HTML/text


## 1.4.7

- [ ] Add support for BBCodes with just their BBCode and HTML replacement. (possibly 1.4.7)
- [ ] HTML5 drag-drop file upload plugin with callbacks to handle the upload and PHP/Node example


## 1.4.8

- [ ] Image resize plugin
- [ ] Add flash embedding command + BBCode in a plugin


## 1.4.9

- [ ] Add context menu support
- [ ] Table editing plugin. Move table command into the plugin


## Future

- [ ] Update dropdown to be able to work from an object to generate HTML instead of requiring HTML
- [ ] Spell checker plugin
- [ ] Possibly create a page which helps create custom commands and BBCodes
- [ ] Consider moving code into modules e.g. AMD modules to make it a bit easier to edit.


## Spell checker plugin ideas

It should:

   * Be generic so it can work with any contentEditable/designMode element and if possible any textarea too.
   * Have it's own repository instead of using the SCEditor one.
   * Allow multiple spell checker backends so PHP, Ruby, ASP.NET, Python, ect. can be used as well as web API's.
   * Get a list of unique words and check them and cache the result.
   * Have option for AYT spell checking with x seconds delay.
   * Grab previous words around range and also have manual spell check button.
   * Wrap the wrong words in a span with a class so it can have custom styling.
   * When the span is clicked/right clicked it should show a menu with suggestions, might want to preload them in case it's being done via AJAX.
   * Have an option to allow adding words so backends that support adding words can add them.
   * Have an ignore word option which adds the word to the cache.
   * Have options to ignore capitalised words, split words with hyphens.
   * Have an option to set a custom word handler which is passed a string to extract the words from.
   * Have an option to replace all words spelled a certain way with the suggested word.

**Possible check format:**

	{
		words: [
			"teh",
			"quick",
			"brown",
			"fox"
		]
	}

**Possible return format:**

	{
		 // Would be set to a string to show the user if an error occurs.
		errors: null

		// Assoc array with the key being the word and the value being an array of suggestions.
		// Suggestions array can be empty if there are none.
		corrections: [
			"teh": [
				"the",
				"ten"
			]
		]
	}