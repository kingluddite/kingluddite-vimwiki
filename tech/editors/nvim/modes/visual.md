# Visual Mode

| Trigger | Effect                        |
|---------|-------------------------------|
| `<C-v>` | Enter `Visual Block` mode     |
| `gv`    | Select last visual selection  |
| `r`     | Replace                       |
| `V`     | Visually select line          |
| `yyp`   | Yank and put                  |
| `e`     | End of word                   |
| `c`     | Switch to `Insert` mode       |
| `A`     | Append at the end of the line |
| `$`     | Select to end of line         |

## Tips
* If we want to set up the dot command so that it repeats something useful, then we're better off staying out of `Visual` mode

## General Rule
* We should prefer operator commands over their `Visual` model equivalents

## Change columns of text
* We can use `Visual-Block` mode with code too
  - If I want to change all the paths from `img` to `assets/img`
  
```
<img href="img/one.jpg">
<img href="img/two.jpg">
<img href="img/three.jpg">
```

* To this

```
<img href="assets/img/one.jpg">
<img href="assets/img/two.jpg">
<img href="assets/img/three.jpg">
```
* I would:

1. Start in `Normal` mode on and have curson over first `i` of `img`
2. `<C-v>` to insert `Visual-Block` mode
3. `jje` to move down twice and select to end of word `img`
4. `c` to enter `Insert` mode
5. Type new path of `assets/img`
6. Enter `Normal` mode with `<Esc>`

* Note you will only see first line of changes until you enter Normal mode with `<Esc>` which seems counterintuitive but you will get used to it with practice

### `vitU` vs `gUit` (thinking the Vim way)
* Both have 4 keystrokes but their semantics are different

* `vitU` in `Visual` mode can be considered two separate commands:
  - `vit` to make a section
  - `U` to transform the selection
* `gUit` can be considered a single command comprised of an operator `gU` and a motion `it`

## Sub Types of Visual Mode
* In character-wise
  * Select anything from a single character up to a range of characters within a line or spanning multiple lines. This is suitable for working at the level of individual words or phrases
* Line-wise
  * Operate on entire lines
* Block-wise
  * Allows us to work with the columnnar regions of the document

## Visual Mode Sub Types key bindings
| trigger | Visual Mode                             | notes                            |
|---------|-----------------------------------------|----------------------------------|
| `v`     | character-wise                          | gateway into Visual mode         |
| `V`     | line-wise                               | hold `<Shift>`                   |
| `<C-v>` | block-wise                              |                                  |
| `gv`    | reselect the last visual selection      |                                  |
| `<Esc>` | Switch to Normal mode                   |                                  |
| `<C-[>` | Switch to Normal mode                   |                                  |
| `v`     | Switch to Normal mode                   | when in charter-wise Visual mode |
| `V`     | Switch to Normal mode                   | when in line-wise Visual mode    |
| `<C-v>` | Switch to Normal mode                   | when in block-wise Visual mode   |
| `o`     | Go to the other end of highlighted text |                                  |

## Toggling the Free End of a Selection
* What if you selected the wrong text and need to select new text
* There is a range of Visual Mode Selection that has two ends (one end is fixed and the other moves freely with the cursor)
  *  It is hard to understand at first but imagine this text:
    * You have `from here` visually selected but you want to change to `to here` visually selected
    * Just use the `o` key to move the free text to the new visual selection and use it a gain to change the other end - by doing this you can stay in visual mode and select whatever you want

### free end visual mode demo
`to here` and then I want to move the select `from here`

### Warning: Visual mode does not always work great with the "dot command" (.)
* So to avoid this issue we can use Normal mode operators when appropriate

### Prefer Operators to Visual Commands where Possible
* How to select the text inside the `<h1>`

```
<h1>this is my text</h1>
```

* `vit` (read as "visually" select "inside" the "tag" aka VisuallyInsideTag)
* **it** is a "text object" (a special kind of `motion`) 
  
## When Visual Mode is repeated (using dot command) it affects the same range of text
* Which will cause this to happen:

1. Cursor in Normal mode on first line
2. `vit`
3. `U` (makes `one` to `ONE`)
4. `j.` (down and repeat)
5. `j.` (down and repeat)
6. `j.` (down and repeat)

```
<a href="#">ONE</a>
<a href="#">TWO</a>
<a href="#">THRee</a>
```
