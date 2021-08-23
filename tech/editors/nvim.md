# Nvim
[Nvim inside VS Code](nvim-inside-vscode.md)

* I made an alias to open my `nvim` with just `v`
* How can I open two files in separate windows from the terminal?
`$ v -O blog-{classic,modular}/.projections.json`

* How to select an item in vim autocomplete list 
`<Ctrl-y>` (think of it as 'Yes' I want that item)

## Command Line
* In ZSH I have autosuggest setup and to accept the autosuggestion I have set up clicking the backtick to do that - this saves a ton of time
* See the screenshot below that shows the CLI autosuggest in action and if I type the backtick it will type the rest of the autosuggest for me

![IMG - autosuggest working](https://i.imgur.com/o7JWDJi.png)

* TODO - find where this settings is in dotfiles

## Editing
| key binding | action                      | note |
|-------------|-----------------------------|------|
| `d0`        | delete to beginning of line |      |

## Buffers
| key binding | action                  | note |
|-------------|-------------------------|------|
| `:bd`       | close a tab             |      |
| `:buffers`  | get buffer numbers      |      |
| `:bd 6`     | delete buffer by number |      |

### Plugin Install Instructions
1. Update your nvim plugins with `:source %`
2. Then install the new package with `:PlugInstall` (Assuming you are using <a href="https://github.com/junegunn/vim-plug" target="_blank">Plug</a>) - A popular Vim plugin manager

## Plugins
[NerdTree](./nvim/plugins/nerdtree.md)
[vimwiki](./plugins/vimwiki.md)
[CtrlP](./plugins/ctrlp.md)
[fzf](./plugins/fzf.md)
[Adding Markdown](./plugins/adding-markdown.md)
Add E7 React Snippets
[vim-projectionist](./plugins/vim-projectionist.md)

## Select word in VIM autocomplete list
<kbd>ctrl</kbd> + <kbd>y</kbd> (think of it as Yes I select this word) - more info here - https://unix.stackexchange.com/questions/162528/select-an-item-in-vim-autocomplete-list-without-inserting-line-break

## Splitting Screens horizontally and vertically

| binding                          | action                                                 | note |
|----------------------------------|--------------------------------------------------------|------|
| <kbd>ctrl+w</kbd> + <kbd>v</kbd> | open window NEXT to existing window                    | na   |
| <kbd>ctrl+w</kbd> + <kbd>s</kbd> | open window at bottom of the currently selected window | na   |

## Navigate Screens

| binding                           | action                                          | note                          |
|-----------------------------------|-------------------------------------------------|-------------------------------|
| <kbd>ctrl+w</kbd> + <kbd>l</kbd>  | Move to the RIGHT window of the selected window | This is the lowercase "L" key |
| <kbd>ctrl+w</kbd> + <kbd>h</kbd>  | Move to the LEFT window of the selected window  |                               |
| <kbd>ctrl+w</kbd> + <kbd>j</kbd>  | Move to window BELOW the selected window        |                               |
| <kbd>ctrl+w</kbd> + <kbd>k</kbd>  | Move to window ABOVE the selected window        |                               |

## Searching
:grep ADD YOUR PATTERN (this searches all files in your project)

## Navigation
| keyboard binding  | action  | notes |
|---|---|---|
| <kbd>k</kbd> | move up 1 line  | `k` is an [ascendor](https://en.wikipedia.org/wiki/Ascender_(typography)) so movement is up
| <kbd>j</kbd> | move down 1 line  | `j` is an [descender](https://en.wikipedia.org/wiki/Descender) so movement is down
| <kbd>h</kbd> | move left 1 space | `h` is to the left of `j`
| <kbd>;</kbd> | move right 1 space | `;` is to the right of `l`
| <kbd>ctrl</kbd> + <kbd>u</kbd>| move up half page | 
| <kbd>ctrl</kbd> + <kbd>d</kbd>| move down half page | 

* delete line `dd`

## Delete all console logs (in a directory and recursively)
* Work in progress
* [source](https://stackoverflow.com/questions/53196504/how-can-i-remove-all-console-logs-using-vim)
* You'll have to set args to files you want to update first and then call argdo
* You'll have to set args to files you want to update first and then call argdo.

`:args ./*.js`
* above will select all the javascript files in the current directory. If the current directory has sub-directories and you want to select files recursively you could use

`:args **/*.js` (watch out for node_modules!)

* After setting the args you can call the global command using argdo

`:argdo g/console\.log/d | update`

## Custom Key Mappings
* Set up in your mappings config file

| keyboard binding            | action                              | notes |
|-----------------------------|-------------------------------------|-------|
| <kbd>j</kbd> + <kbd>k</kbd> | switch to command mode (custom map) |       |
| <kbd>z</kbd> + <kbd>z</kbd> | save file                           |       |

## Folding
| keyboard binding            | action                                | notes |
|-----------------------------|---------------------------------------|-------|
| <kbd>z</kbd> + <kbd>M</kbd> | close all folds                       |       |
| <kbd>z</kbd> + <kbd>R</kbd> | open all folds                        |       |
| <kbd>z</kbd> + <kbd>m</kbd> | with nested folds fold level by level |       |
| <kbd>z</kbd> + <kbd>r</kbd> | open folds level by level             |       |
## Troubleshooting
[Python & Homebrew](./troubleshooting/python-homebrew.md) `( - Aug 21, 2021 - )`
