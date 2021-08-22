# Copy Mode
Copy mode is when you have ouput in your terminal and want to scroll through. There is a feature in tmux where you can enable or disable this. My preference is to disable this because I am trying to teach myself to use the mouse as little as possible. The default behavior is mouse is enable3d

## How to navigate with out a mouse 
* Example: You run `$ gatsby build` and you get an error in the terminal as it builds your Gatsby application locally. You will be stuck and not able to scroll up through the terminal. To use your keyboard you have to type the `Prefix [` + `up` or `/down` arrows. But that is slow and tedious. Below are ways to navigate Copy Mode Fast and efficiently

## Move faster than one key at a time n output
| binding                      | action                                   | notes |
|------------------------------|------------------------------------------|-------|
| `Prefix + [`                 | Enter Copy Mode                          |       |
| `w`                          | Move to next word                        |       |
| `b`                          | Move back one word                       |       |
| `f + <any character>`        | Jump forward that character on same line |       |
| `F + <any character>`        | Jump back that character on same line    |       |
| `Prefix + <CR>`              | Exit Copy Mode                           |       |

## Move Quickly Through the Buffer
| binding    | action                           | notes |
|------------|----------------------------------|-------|
| `<Ctrl-b>` | Move up one page                 |       |
| `<Ctrl-f>` | Move down one page               |       |
| `g`        | Move to top of buffer history    |       |
| `G`        | Move to bottom of buffer history |       |

## Searching through the Buffer
| binding             | action                                        | notes |
|---------------------|-----------------------------------------------|-------|
| `? + phrase + <CR>` | jumps up to first occurence                   |       |
| `n`                 | jumps to next occurence                       |       |
| `N`                 | jumps back to previous occurence |       |
|                     | <kbd>n</kbd> jumps to next occurence          |       |
|                     | <kbd>N</kbd> jumps back to previous occurence |       |
