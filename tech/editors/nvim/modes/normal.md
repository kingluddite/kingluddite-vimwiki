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
  
### Everthing to do with Case
| Trigger    | Effect                                             |
|------------|----------------------------------------------------|
| `g~`       | Swap case                                          |
| `~`        | Changes the case of the current character          |
| `guu`      | Changes current line from upper to lower           |
| `gUU`      | Make current line uppercase                        |
| `guw`      | Change the end of current WORD from upper to lower |
| `guaw`     | Change all of the current WORD to lower            |
| `gUw`      | Change to end of current WORD from lower to upper  |
| `gUaw`     | Make word uppercase (aka SHOUTY case)              |
| `g~~`      | Invert case to entire line                         |
| `g~w`      | Invert case to current WORD                        |
| `guG`      | Change to lowercase until the end of document      |
| `gu`       | Make lowercase                                     |
| `gU)`      | Change until end of sentence to upper case         |
| `gu}`      | Change to end of paragraph to lower case           |
| `gU5j`     | Change 5 lines below to upper case                 |
| `gu3`      | Change 3 lines above to lower case                 |
| `gU`       | Make uppercase                                     |
| `gUgU`     | Make current line uppercase                        |
| `gUap`     | Make paragraph SHOUTY case                         |
| `}`        | Go to next empty line                              |

## Other useful commands
| Trigger    | Effect                                             |
|------------|----------------------------------------------------|
| `c`        | Change                                             |
| `d`        | Delete                                             |
| `dap`      | Delete around paragraph                            |
| `dd`       | Delete current line                                |
| `>>`       | Indent current line                                |
| `:History: | Search through Vim's command history               |
| `y`        | Yank into register                                 |
| `>`        | Shift right                                        |
| `<`        | Shift left                                         |
| `=`        | Autoindent                                         |
| `!`        | Filter {motion} lines through an external program  |
