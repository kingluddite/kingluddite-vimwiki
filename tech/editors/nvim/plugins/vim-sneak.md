# vim-sneak
* Jump to any location specified by two characters

## Problem with `s`
* The `s` command compounds two steps into one: it deletes the character under the cursor and then enters `Insert` mode but vim-sneak overrides this
  - In the "how dare you remap `s`" section of <a href="https://github.com/justinmk/vim-sneak" target="_blank">the vim-sneak docs</a> they let you know that:
    - `cl` is equivalent to `s`
    - And `cc` is equivalent to `S`
