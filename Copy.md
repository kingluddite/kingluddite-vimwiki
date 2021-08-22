# Copy Mode
* All of the following instructions pertain to being in Copy Mode

## How to navigate with out a mouse 
* example scenario: You build Gatsby `$ gatsby build` and you get an error in the terminal as it builds your application locally. You will be stuck and not able to scroll up through the terminal. To use your keyboard you have to type the `Prefix` + <kbd>[</kbd> + `up` or `/down` arrows. To exit scroll mode type the `Prefix` + <kbd>enter</kbd>. But that is kind of slow and tedious. Below are ways to navigate Copy mode faster

## Scroll through output with Copy Mode
Copy mode is when you have ouput in your terminal and want to scroll through. There is a feature in tmux where you can enable or disable this. My preference is to disable this because I am trying to teach myself to use the mouse as little as possible. The default behavior is mouse is enable3d

### Move faster than one key at a time n output
| binding                      | action                                   | notes               |
|------------------------------|------------------------------------------|---------------------|
| Prefix + <kbd>[</kbd>        | Enter Copy Mode                          |                     |
| Prefix + <kbd>enter</kbd>    | Exit Copy Mode                           |                     |
| <kbd>w</kbd>                 | Move to next word                        |                     |
| <kbd>b</kbd>                 | Move back one word                       |                     |
| <kbd>b</kbd>                 | Move back one word                       |                     |
| <kbd>f</kbd> + any character | Jump forward that character on same line |                     |
| <kbd>F</kbd> + any character | Jump back that character on same line    |                     |

### Move Quickly Through the Buffer
| binding           | action                           | note |
|-------------------|----------------------------------|------|
| <kbd>ctrl-b</kbd> | Move up one page                 |      |
| <kbd>ctrl-f</kbd> | Move down one page               |      |
| <kbd>g</kbd>      | Move to top of buffer history    |      |
| <kbd>G</kbd>      | Move to bottom of buffer history |      |

### Searching through the Buffer
| binding                       | action                                        | note |
|-------------------------------|-----------------------------------------------|------|
| <kbd>?</kbd> + phrase + Enter | jumps up to first occurence                   |      |
|                               | <kbd>n</kbd> jumps to next occurence          |      |
|                               | <kbd>N</kbd> jumps back to previous occurence |      |
| <kbd>/</kbd> + phrase + Enter | jumps up to first occurence                   |      |
|                               | <kbd>n</kbd> jumps to next occurence          |      |
|                               | <kbd>N</kbd> jumps back to previous occurence |      |


