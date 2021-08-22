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
* [vimwiki](./plugins/vimwiki.md)
* [CtrlP](./plugins/ctrlp.md)
* [fzf](./plugins/fzf.md)
* [Adding Markdown](,/plugins/adding-markdown.md)
* [Add E7 React Snippets](.md)
* [vim-projectionist](./nvim/plugins/vim-projectionist.md)

## Troubleshooting
[Python & Homebrew](./troubleshooting/python-homebrew.md) `( - Aug 21, 2021 - )`
