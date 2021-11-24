# Command-Line Mode
* Command-Line Mode prompts us to enter an `Ex` command, a search pattern, or an expression

| Trigger           | Effect                                                    | Notes                                    |
|-------------------|-----------------------------------------------------------|------------------------------------------|
| `<C-w>`           | delete backward to start of word                          |                                          |
| `<C-u>`           | delete backword to start of line                          |                                          |
| `<C-v>`           | insert characters not on keyboard                         |                                          |
| `<C-k>`           | insert characters not on keyboard                         |                                          |
| `<C-r>{register}` | insert contents of any register                           |                                          |
| `:copy.`          | copy line (shorthand is `:t`)                             |                                          |
| `:co.`            | copy line (shorthand is `:t`)                             |                                          |
| `:t`              | a synonym for `:copy.`                                    | as a mnemonic think "copy to"            |
| `:6t.`            | copy line 6 to just below the current line                |                                          |
| `:t6`             | copy the current line to just below line 6                |                                          |
| `:t.`             | duplicate the current line                                | similar to Normal mode `yyp`             |
| `:t$`             | copy the current line to the end of the file              |                                          |
| `:'<,'>t0`        | copy the visually selected lines to the start of the file |                                          |
| `:move`           | move lines                                                | shorthand is `:m`                        |

* `<C-r><C-w>` - mapping copies the word under the cursor and it inserts it at command-line prompt |
* place your cursor on a setting in `.vimrc` then type `:help <C-r><C-w>` to look up the documentation for that setting
* `yyp` uses a **register** but `:t.` does not
  - **tip** use `:t.` when you don't want to override the current value in the default register
  
`:[range]copy {address}`

`:6copy.` - "Make a copy of line 6 and put it below the current line"

## Meet the command line window
* `q:` and you enter the command line window

| Trigger | Effect                                                          |
|---------|-----------------------------------------------------------------|
| `q/`    | Open the command-line window with history of searches           |
| `q:`    | Open the command-line window with history of Ex commands        |
| `<C-f>` | Switch from `Command-Line` mode to the command-line window      |
| `:q`    | Close command-line window                                       |
| `<CR>`  | It will execute the item highlighted in the command-line window |

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

## Using * to help replace multiple words
```
var tally;
for (tally = 1; tally <= 10; tally++) {
  // do something with tally
}
```

1. Place cursor in `Normal` mode on `t` of `tally`
2. `*` (it will highlight all `tally` instances)
3. `cwcounter<Esc>`
4. `:%s//<C-r><C-w>/g`

All `tally` instances are replaced with `counter`

## Run Normal Model command across a range
### What if you want to append `;` at the end of every line
* The `.` would have to be pressed to repeat `A;` which is inefficient if you have 5000 lines (you would have to type `.` 5000 times!)
* This is more efficient:

1. `A;`
2. `<Esc>`
3. `jVG`
4. `:'<,'>normal .'`

This `#4` can be read as follows: "For each line in the visual selection, execute the Normal mode `.` command"

## Semi colon at the end of every line
`:%normal A;`

## Comment out every line
`:%normal i//`

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
