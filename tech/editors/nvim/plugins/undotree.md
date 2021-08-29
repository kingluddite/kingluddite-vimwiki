# undotree
* `Vim` maintains a tree (think of git and branches) structure when you `undo` and `redo`
* You can use this tree and move around it but not seeing the tree makes it almost impossible to use it
* The `undotree` plugin gives you a visual representation of the tree so you can easily move around
* <a href="https://www.youtube.com/watch?v=9msMqGdtVAE" target="_blank">UndoTree: Visualize and Explore Vim's Branching History Tree (Video)</a>

## Install undotree
1. Place this in your `.vimrc` (or nvim equivalent)

```
" MORE CODE

Plug `mbbill/undotree`

" MORE CODE
```

2. Run the following ex commands in `Vim`

`:source %`
`:PlugInstall` (I use the minimalist `VimPlug` Vim Plugin Manager)

## Using the undotree plugin
* Use `Ex` commands in `Vim` to show the visual undotree
* Vim always takes the left most branch
* `>n<` * Your current possition in the tree (`n` represents a number)
* `[n]` Is the most recent change
* `[S]` Is the last time you ran `Save`
* `[s]` Represents any other point where you saved the document
* To move to a point you want to go to navigate to that point and press `<CR>` (also works with branches)
* Bottom left corner is `Diff` state showing you before and after change
* Vim handle all merging in the background

`:UndotreeToggle`

* No changes happen to the tree structure as you make changes until you leave `Insert Mode` and if you make several changes to the document once you leave `Insert Mode` Vim will add a line in the tree for every change

| key binding | action                           | notes                    |
|-------------|----------------------------------|--------------------------|
| `u`         | undo                             | backward in history      |
| `<ctrl-r>`  | redo                             | forward in history       |
| `<`         | jump to previous save point      |                          |
| `>`         | jump to next save point          |                          |
| `<CR>`      | Select currently highlight point |                          |
| `<shift-K>` | Move up                          |                          |
| `<shift-J>` | Move down                        |                          |
| `k`         | Move up                          | custom key binding       |
| `j`         | Move down                        | custom key binding       |
| `D`         | Toggle Diff mode                 | good to keep open        |
| `T`         | Toggle Time mode short vs long   | good to keep open        |
| `<ctrl-c>`  | Clear the undotree               | will ask you to confirm* |
| `<alt-t>`   | Toggle undotree                  | custom key binding       |

* `*` If you confirm clearing undotree you won't be able to redo

## Persistent undo
* Out of the box all changes to Vim are lost when you quit out of a document in `Vim` you are going to lose your entire undo trees
  - So if you open a document from a day ago and you try to undo something you will not be able to undo it
  - But you can enable `Vim` to make the state changes persistent by enabling your persistent history (highly recommended because it makes undotree so much more useful because then you can actually quit out of the document come back to it and still have the ability to go backwards in the tree
  - We enable this in our `.vimrc`

`.vimrc`

* We check to see install of Vim have `persistent undo` enabled because some versions of Vim will be compiled without persistent history
* By adding the 4 lines below you will have `persistent history` enabled

  ```
  
  if has("persistent_undo")
    set undodir=~/.config/nvim/undodir
    set undofile " Maintain undo history between sessions
  endif
  ```
  
## Keybinding Your undotree
* Prefer to work with toggle trees
* **tip** Putting keys on <alt> keys is generally safer because most people don't put on the <alt>

```
" MORE CODE

" Undotree
nnoremap <A-t> :UndotreeToggle<CR>

" MORE CODE
```
