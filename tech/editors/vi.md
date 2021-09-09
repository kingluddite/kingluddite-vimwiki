# History
## ed
* `ed` was the original Unix text editor (it was written when there were not many video displays)
* source code was usually printed onto a roll of paper and edited on a teletype terminal
* commands entered at the terminal would be sent to a mainframe computer for processing, and the output from each command would be printed
* `ed` went through several generations of improvements including:
  - `em` (dubbed the "editor for mortals")
  - `en`
  - And eventually `ex` when screens were more common
    + You would enter `:visual` to enter screen-editing mode (`:vi` for short) and that is where `vi` came from
* `Vim` stands for `Vi improved`

## Vi
* `Vi` is where the modal editing paradigm was conceived
* `Vi` came from a line editor called `ex` (This is why we have `Ex` commands) 

## Vi
* `Vi` stands for Visual
  - It is a text editor that is an early attempt to a visual text editor

## Vim
* `Vim` stands for ``Vi IMproved`
* `Vim` is an implementation of the `Vi` standard with many additions
  - `Vim` is the most commonly used implementation of the standard
  - Most Linux distributions come with `Vim` already installed

## Ex
`Ex` is essential to `vi` as it is used for core functions like **search** and **replace**

### Example of using ex
* If you are editing a file in vim and you want to search for all instances in that file of "cat" and replace with "dog" you would type: `:%s/cat/dog/g`
* In `Vi` and `Vim`, the ex mode is similar to a command line mode which allows you to enter ex commands
* If you wanted to use `ex` mode in the command line you don't preface with `:` and just type `%s/cat/dog/g`
* `Vi` and `Ex` are part of the <a href="https://en.wikipedia.org/wiki/POSIX" target="_blank">POSIX standard</a>  and a Unix implementation of that standard
* `Vim` is the most commonly found implementation of the standard on Linux systems
* Often, the command `$ vi` will start the `vim` command
* **note** Nowadays, `Vim` is also found on most Unix systems and macOS
* The improvements in `vim` are not part of the Vi/Ex POSIX standard although `Vim` is said to be 99% Vi compatible

## What are the difference between Vi and Vim? 
* `Vim` will start by default in a `Vi compatibility mode` which can be disabled

### How to benefit fully from `Vim` improvements disable the `Vi compatibility mode` with:
```
:set nocompatible
```

* Or you can start `Vim` with the `-N` flag
* **note** The `compatible` mode will be automatically turned off when a `.vimrc` file is found

## Beneifts of Vim over Vi
* Multi-level undo
  - `Vi` only had one level of undo using `u` (VERY LIMITING)
  - `Vim` has multi-level undo (default remembers 1,000 changes)
    + You can change this values using `undolevels`
    + You can `redo` the changes using `<ctrl-r>`
    + Also multiple levels of changes can be branched in an `undo-tree` to go back to any state of a text without the risk of loss
* Tabs, Multiple windows and buffers
* Flexible insert mode
* Macros
* Visual mode
* Online help system
* Command-line editing and history
* Command-line completion
* Horizontal scrolling
* Unicode and internationalization improvements
