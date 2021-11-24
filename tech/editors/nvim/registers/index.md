# Registers
## What are Registers?
* Vim's registers are simply containers that hold text
* They can be used in the manner of a clipboard for cutting, copying, and pasting text, or they can be used to record a macro by saving a sequence of keystrokes
* Instead of dealing with a single-wide clipboard, vim provides a couple dozen registers where we can store regions of text

## Unnamed Register
* Take this sentence with an error:

Practical lvim

| Keystrokes | Action                                                                           |
|------------|----------------------------------------------------------------------------------|
| `F `       | Find first space                                                                 |
| `x`        | Cut that empty space (character under cursor) and places in the unnamed register |
| `p`        | pastes contents of the unnamed register after the cursor position                |

`xp` - "Transpose the next two characters"

## Transpose Lines
* Same as above but we use the `dd` to delete a line
* The `p` in this case knows we are dealing with a "line-wise" chunk of text, so it will paste the contents of the unnamed register after the current line

`ddp` - "Transpose the order of this line and its successor"

## Duplicating Lines
* Vim calls this a "line-wise yank followed by a put"

| Keystrokes | Action                                             |
|------------|----------------------------------------------------|
| `yyp`      | Does a line-wise copy and paste (duplicate a line) |

## Clobber my yank!
* When you delete a word Vim puts that deleted word in the unnamed register
* The delete, yank and put commands all interact with one of Vim's registers

### Address a Register
`"{register}"`

* example - yank a word into the `a` register

`"ayiw`

And paste that `a` register with `"ap`

* example - cut a word into the `b` register

`"bdd`

And paste that `b` register with `"bp`



## Vim's Terminology
* Vim calls it `put` the rest of the world called it `paste`
* Vim calls copy `yank`
* Vim's delete command is equivalent to `cut` (but it puts the deleted text in the unnamed register)
* You can delete without putting in unnamed register using the special "black hole" register and that is addressed using `_`
