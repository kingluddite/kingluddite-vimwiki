* Normal Mode
  * Do painters always have their brush on the canvas? No.
  * So normal mode is Vim's natural resting state, where the developer is in this mode when they are thinking about how they will manipulate their code
  * From we enter `Insert` mode until we return to `Normal` mode, everything we type (or delete) counts as a single change (so we can make the undo command operate on words, sentences, or paragraphs just by moderating our use of the `<Esc>` key)

## How often should you leave `Insert` mode?
* **tip** Make each "undoable chunk" correspond to a thought and when you are ready to continue type `A` to carry on where you left off
  # * If you mess up, switch to `Normal` mode and press `u`

## Operator + Motion = Action
* Vim's grammer rule
  * When an operator command is invoked in duplicate, it actions upon the current line 
| Trigger | Effect                                            |
|---------|---------------------------------------------------|
| `c`     | Change                                            |
| `d`     | Delete                                            |
| `dap`   | Delete around paragraph                           |
| `dd`    | Delete current line                               |
| `>>`    | Indent current line                               |
| `y`     | Yank into register                                |
| `g~`    | Swap case                                         |
| `gu`    | Make lowercase                                    |
| `gU`    | Make uppercase                                    |
| `gUgU`  | Make current line uppercase                       |
| `gUU`   | Make current line uppercase                       |
| `gUaw`  | Make word uppercase (aka SHOUTY case)             |
| `gUap`  | Make paragraph SHOUTY case                       |
| `>`     | Shift right                                       |
| `<`     | Shift left                                        |
| `=`     | Autoindent                                        |
| `!`     | Filter {motion} lines through an external program |
