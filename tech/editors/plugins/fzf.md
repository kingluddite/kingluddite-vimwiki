# FZF
## What does it do?
Finding files using fuzzy path matching

## Search Ex command history
`:History:`

## Install with VimPlug
`.vimrc`

```
" more code
Plug 'junegunn/fzf'
" more code
```

* Then install with (in Vim)

`:source %`

`:PlugInstall`

* Then you want to remap to `<C-p>` with this:

`fzf-mappings.vim`

```
nnoremap <C-p> :<C-u>FZF<CR>
```

## Tips
* Use tab completion
* Open in split mode with
* Create a git repo to ignore all node_modules (and that will reduce files you are seach by thousands!)


## Search
| key binding       | action                                       | note                   |   |
|-------------------|----------------------------------------------|------------------------|---|
| `<C-j>`           | Select previous item from matchlist          |                        |   |
| `<C-k>`           | Select next item from matchlist              |                        |   |
| `<CR>`            | Open the selected file in the current window |                        |   |
| `<C-x>`           | Open the selected file in a horizontal split |                        |   |
| `<C-v>`           | Open the selected file in a vertical split   |                        |   |
| `<C-t>`           | Open the selected file in a new tab page     |                        |   |
| `<C-c>`           | Dismiss the fzf picker                       |                        |   |
| `:Files!`         | Open Files Fuzzy search in full screen       |                        |   |
| `:Buffers`        | Open Buffers Fuzzy search                    |                        |   |


* Count # of files: `$ find . -type f | wc -l`
* Don't search node_modules with `$ git ls-files | wc -l`
    - But that isn't the best solution because what about files not tracked (won't be searched) or non-git projects, won't search
    - A better solution is using `Ripgrep`
    - In your zsh add:
        - The `rg --files` command is able to filter out files that are marked to ignore in Git, Mercurial, and Subversion repositories. When used in a Git repo, this command does include files that have yet to be added to the Git index. When used outside of a version control repo, it falls back to listing all files

```
export FZF_DEFAULT_COMMAND='rg --files'
```

## Search
| key binding | action                      | note |
|-------------|-----------------------------|------|
| `ctrl+f`    | search                      |      |

## Update All matching phrases in our project
* [source](https://dev.to/iggredible/how-to-search-faster-in-vim-with-fzf-vim-36ko)

```
:grep "pizza"
:cfdo %s/pizza/donut/g | update
```

1. `:grep pizza` uses ripgrep to succinctly search for all instances of "pizza"
    * By the way, this would still work even if we didn't reassign `ripgrep` to replace default `grep`
    * We would have to do `:grep "pizza" . -R` instead of `:grep "pizza"`
2. We run `:cfdo` because `:grep` uses quickfix
    * `:cfdo` executes any command we pass (in this case, our command is `%s/pizza/donut/g)` on all entries in our quickfix list
    * To **run multiple commands**, we can chain it with pipe (|)
    * The first command we are executing is pizza-donut substitution: `%s/pizza/donut/g`
    * The second command, `update`, saves each file after the first is finished

## Updating specific files
1. Clear buffers
2. `:Files`
3. Select a file or multiple files with `Tab / Shift+Tab`
4. `:bufdo %s/pizza/donut/g | update`

## Resources
* [short useful fzf video](https://www.youtube.com/watch?v=DpURGnb4Fyk)
* [useful vimwiki](https://codevion.github.io/#!index.md()
