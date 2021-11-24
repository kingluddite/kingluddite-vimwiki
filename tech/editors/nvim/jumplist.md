# Jumplist
* `>` is current spot
* When you open jump list choose number to jump to 
* You can't have more than one jump per line
* Scrolling through a file is not regarded as jumping 

| binding                         | action                                         | notes |
|---------------------------------|------------------------------------------------|-------|
| `:jumps`                        | display jump list for current window           |       |
| `<C-O>`                         | Jump to last spot                              |       |
| `<C-I>`                         | Jump to previous spot                          |       |
| `[count]G`                      | Jump to line number                            |       |
| `/pattern<CR>/?pattern<CR>/n/N` | Jump to next/prev occurence of pattern         |       |
| `%`                             | Jump to matching parenthesees                  |       |
| `(/)`                           | Jump to start of prev/next sentence            |       |
| `{/}`                           | Jump to start of prev/next paragraph           |       |
| `H/M/L`                         | Jump to top/middle/bottom of screen            |       |
| `gf`                            | Jump to file under cursor                      |       |
| `<C-]>`                         | Jump to definition of keyword under the cursor |       |
| '{mark}/`{mark}                 | Jump to a mark                                 |       |

## Difference between `motions` and `jumps`
* motions move around `within a file` (note - motions are also classified as `jumps`)
* jumps can move `between files`

## Tips
* `<C-o>` and `<C-i>` commands themselves are never treated as a motion
  * This means we can't use them to extend the reach of a Visual mode selection
  * Nor can we use them in Operator-Pending mode
  * "I tend to thenk of the jump list as a breadcrump trail that makes it easy to retrace my steps through the files I've visited during the course of an editing session"
  * Vim can maintain multiple jump lists at same time
    * Each separate window has it's own jump list
    * If we use split windows or multiple tab pages, then `<C-o>` adn `<C-i>` commands will always be scoped to the jump list of the active window
## Resources
<a href="https://vim.fandom.com/wiki/Jumping_to_previously_visited_locations" target="_blank">Jumping to previously visited locations</a>
