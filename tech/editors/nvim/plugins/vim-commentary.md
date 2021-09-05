# vim-commentary
* **note** I am using [tcomment_vim](./tcomment_vim.md)
* Adds a command for commenting and uncommenting lines of code in all languages supported by Vim
* The commentary command is triggered by `gc{motion}` which toggles commenting for the specified
* These are using custom operators 
  * To create your own custom operators read this `:h :map-operator` 
  
| Trigger | Effect                                                |
|---------|-------------------------------------------------------|
| `gcap`  | toggle commenting for the current paragraph           |
| `gcG`   | comments from the current line to the end of the file |
| `gcc`   | comments current line                                 |
