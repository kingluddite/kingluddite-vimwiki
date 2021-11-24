# Sublime Text
* I primarily use Sublime Text for note taking in `markdown`

## Tell Sublime Text 3 to always default to "Word Wrap Column: Automatic"
* It won't work if you just put it in preferences
* You need to open the markdown file (I use sublime for markdown) and then Preferences > Settings - Syntax Specific, then add these rules

```
// Disables horizontal scrolling if enabled.
// May be set to true, false, or "auto", where it will be disabled for
// source code, and otherwise enabled.
"word_wrap": "auto",

// Set to a value other than 0 to force wrapping at that column rather than the
// window width
"wrap_width": 0,
```

### Resources
* <a href="https://stackoverflow.com/questions/62240589/tell-sublime-text-3-to-always-default-to-word-wrap-column-automatic" target="_blank">tell-sublime-text-3-to-always-default-to-word-wrap-column-automatic</a>

* cmd + shift + p opens the pallatte
	* install a package `package install` then choose a name
	
## My setting preferencess
* Choose a theme with MarkdownPreview
* Add line numbers and a gutter to settings:

```
// MORE CODE

"gutter": true,
"line_numbers": true,
	
// MORE CODE
```

`Sublime Text > Preferences > Settings` (`<cmd-,>`)

`Preferences.sublime-settings`

`spell_check: true` (default is false) <a href="https://www.sublimetext.com/docs/spell_checking.html" target="_blank">docs on spell_check</a>

* Preview Markdown
* Vim is running in Sublime Text
* I have bought a one time forever license (if you ever uninstall you need to grab that license number and reuse it or you will get ad popups)

## Open folder in sublime
`$ sop .`

## toggle sidebar
`cmd-k` + `cmd-b`

* I overrode this to be the same as VS Code <kbd>cmd</kbd> + <kbd>b</kbd> +

Preferences > Default bindings > on right side (left side is read only) add this 

```
// override default cmd k + cmb b to open sidebar
{ "keys": ["super+b"], "command": "toggle_side_bar" },
```
## enter command mode in vim
`jk`

## word wrap
* This is a pain and I want the horizontal scrolling to not happen
* Set these values in preferences
* [ref](https://stackoverflow.com/questions/62240589/tell-sublime-text-3-to-always-default-to-word-wrap-column-automatic)

```
	"word_wrap": "auto",
	"wrap_width": 0,
}

```
