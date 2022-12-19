# My Keyboard Shortcuts
* [source](https://medium.com/usevim/vim-101-quick-movement-c12889e759e0)

## help
* Remember that `:help command` will display detailed help for all of the
  following commands (example `:help f`)

## Vim
<LEADER> is changed to `<SPACEBAR>`

## Screen Position
* Want to quickly move around the screen

<C-u> scroll screen up half screen increment
<C-d> scroll screen down half screen increment
<C-f> scroll full screen up
<C-b> scroll full screen down
<z+return> will move the current line to the top of the screen
<50+z+return> will make top of screen start at line 50
<z> will move current line to the centre of the screen
<z- > will move to the bottom

### move screen without scrolling it
<shift-H> move cursor to top line
<shift-M> move cursor to middle
<shift-L> move cursor to last line

### tip - remember simple mnemonics
* Up
* Down
* Forward
* Back
* Home
* Middle
* Last

## Word Movement
<e> move to end of the next word
<w> moves forward, but leaves the cursor at the start of the word
<b> moves backward a word
<E> move to end of the next word (doesn't count symbols or punctuation as
seperate words)
<W> moves forward, but leaves the cursor at the start of the word (doesn't count symbols or punctuation as seperate words)
<B> moves backward a word (doesn't count symbols or punctuation as seperate words)
* tip Most of time programming you'll use <E>,<W>, and <B>

## Text Block Movement
<()> move to beginning of the next or previous sentence
<{}> move through paragraphs
<%> moves through next or previous related item (includes [])

* **note** the definition of a paragraph is based on `nroff` (read `man nroff` for more info

## Line Movement
<44G> moves to 44th line in file
<G> goes to last line
<gg> goes to first line
<``> moves back to the last position (also moves back to the last edit if an
edit was made, or the position before a search was started)

## Character Movement
<f{char}> move the next occurrence of {char} within current line
<F{char}> move the previous occurrence of {char} within current line
<2f:> move to second occurrence of `:` after the current position

## Vimwiki
1. navigate to your `notes` folder `$ z notes`
2. `<leader>ww` opens vimwiki and navigate to what you want

