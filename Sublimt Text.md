# Sublime Text
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
