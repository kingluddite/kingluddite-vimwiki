# nvim
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
