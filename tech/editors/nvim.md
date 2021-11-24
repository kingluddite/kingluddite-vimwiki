# Nvim
[buffers](./nvim/buffers.md)
[command-line (CLI)](./nvim/command-line.md)
[jumplist](./nvim/jumplist.md)
[keybindings](./nvim/.nvim-keybindings.md)
[modes](./nvim/modes/index.md)
[motions](./nvim/motions.md)
[my key translation](./nvim/my-key-translation.md)
[nvim FAQs](./nvim/vim-faqs.md)
[nvim inside VS Code](nvim-inside-vscode.md)
[plugins](./nvim/plugins/index.md)
[spell check](./spell-check.md)

## help
* Just use `:h(elp)` + `term you want to look up`
* Quit help with `:q`

## My Tips
* Disable arrow keys

## Reload nvim
* If you make changes you need to reload nvim with the Ex command `:source $MYVIMRC`
* <a href="https://dev.to/reobin/reload-init-vim-without-restarting-neovim-1h82" target="_blank">Reload init.vim without restarting neovim</a>
* TODO I added the following keybinding but it doesn't wor

## $MYVIMRC
* Both in `Vim` and `nvim`, `$MYVIMRC` is an environment variable set to the path of your custom configuration file

### Test $MYVIMRC
* Use the ex command:

`:echo $MYVIMRC` inside of vim or nvim.

* The output should look like this:

```
# if you are using nvim
/Users/<user>/.config/nvim/init.vim

# if you are using vim
/Users/<user>/.vimrc
```

```
" Easy load of nvim 
nnoremap <silent> <Leader><Leader> :source $MYVIMRC<CR>

```
## My Custom Nvim Aliases
* Open my `nvim` with just `v`

```
// MORE CODE
 
alias v="nvim"

// MORE CODE
```

### Usage
`$ v`

## How can I open two files in separate windows from the terminal?
`$ v -O blog-{classic,modular}/.projections.json`

## Delete all console logs (in a directory and recursively)
* TODO: Work in progress
* [source](https://stackoverflow.com/questions/53196504/how-can-i-remove-all-console-logs-using-vim)
* You'll have to set args to files you want to update first and then call argdo

`:args ./*.js`
* above will select all the javascript files in the current directory. If the current directory has sub-directories and you want to select files recursively you could use

`:args **/*.js` (watch out for node_modules!)

* After setting the args you can call the global command using argdo

https://www.youtube.com/watch?v=1AnG04qnLqI`:argdo g/console\.log/d | update`

## Troubleshooting
[Python & Homebrew](./troubleshooting/python-homebrew.md) `( - Aug 21, 2021 - )`
