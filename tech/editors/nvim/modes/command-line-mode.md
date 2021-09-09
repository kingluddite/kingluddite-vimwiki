# Command-Line Mode
* Command-Line Mode prompts us to enter an `Ex` command, a search pattern, or an expression

| Trigger           | Effect                                                    | Notes                         |
|-------------------|-----------------------------------------------------------|-------------------------------|
| `<C-w>`           | delete backward to start of word                          |                               |
| `<C-u>`           | delete backword to start of line                          |                               |
| `<C-v>`           | insert characters not on keyboard                         |                               |
| `<C-k>`           | insert characters not on keyboard                         |                               |
| `<C-r>{register}` | insert contents of any register                           |                               |
| `:copy.`          | copy line (shorthand is `:t`)                             |                               |
| `:co.`            | copy line (shorthand is `:t`)                             |                               |
| `:t`              | a synonym for `:copy.`                                    | as a mnemonic think "copy to" |
| `:6t.`            | copy line 6 to just below the current line                |                               |
| `:t6`             | copy the current line to just below line 6                |                               |
| `:t.`             | duplicate the current line                                | similar to Normal mode `yyp`  |
| `:t$`             | copy the current line to the end of the file              |                               |
| `:'<,'>t0`        | copy the visually selected lines to the start of the file |                               |
| `:move`           | move lines                                                | shorthand is `:m`             |

* `yyp` uses a **register** but `:t.` does not
  - **tip** use `:t.` when you don't want to override the current value in the default register
  
`:[range]copy {address}`

`:6copy.` - "Make a copy of line 6 and put it below the current line"

## :t. is more efficient
* If you use `yyp` instead

1. Jump to line you want to copy `6g`
2. Yank it `yy`
3. Snap back to where we started `<C-o>`
4. Use the `p` command to duplicate the line

## Symbols that can be used to create addresses and ranges for Ex commands
| Trigger | Effect                                    |
|---------|-------------------------------------------|
| `1`     | First line of the file                    |
| `$`     | Last line of the file                     |
| `0`     | Virtual line above first line of the file |
| `.`     | Line where the cursor is placed           |
| `'m`    | Line containing mark `m`                  |
| `'<`    | Start of visual selection                 |
| `'>`    | End of visual selection                   |
| `%`     | The entire file (shorthand for `:1,$`)    |

## Operate on text i a buffer
### What is the `:` key used for?
* This switches us from `Vim` into `Command-Line` mode
* It resembles the command line that we use in the shell

### How to execute commands in Command-Line mode
* Type command and press `<CR>`
* Jump back to Noral mode with `<Esc>`

### What are Ex commands 
* Commands we execute from `Command-Line` mode are called `Ex commands`

### Other ways to bring up Command-Line mode
* `/` Will bring up a search prompt
* `<C-r>` to access the expression register

### Special keys in Vim's Command-Line mode
* Command-Line mode is similar to `Insert` mode in that most of the buttons on the keyboard simply enter a character
* In `Insert` mode the text goes into a `buffer`
* But in `Command-Line` the text appears at the prompt
* But for both we use control keys chords to trigger commands

## Greatest feature that distinguises Ex commands 
* Their ability to be executed across many lines at the same time (Ex commands strike far and wide!)
