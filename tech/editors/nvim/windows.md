# Windows
[tab pages](./nvim/windows/tab pages.md)

* In vim's terminology, a window is a viewport onto a buffer
* We can open multiple windows, each containing the same buffer
* Or we can load different buffers into each window
* Vim opens with a single window
* **note** I have my `<C>` key also remapped to by `<LEFTTAB>` key

## Creating Split Windows
| key binding        | action                            | notes                          |
|--------------------|-----------------------------------|--------------------------------|
| `<C-w>s`           | divide window horizontally        | creates 2 windows equal height |
| `<C-w>v`           | divide window vertically          | creates 2 windows equal width  |
| `:sp[lit] {file}`  | split current window horizontally | loading {file} into new window |
| `:vsp[lit] {file}` | split current window vertically   | loading {file} into new window |

### Notes about splitting windows
* We can repeat the above commands as often as we like
* Each time we use the split commands the two resulting splits will contain the same buffer as the original window that was divided
* Having the same buffer open in two windows if we are working on a long file
* `<C-w>s` + `:edit {filename}` will divide our workspace and then open another buffer in one split window while keeping the existing buffer visible in the other split (`:sp[lit] {file}` and `:vsp[lit] {file}`) are faster because they combine two steps into one

## Changing focus between windows
| key binding | action                        | notes |
|-------------|-------------------------------|-------|
| `<C-h>`     | cycle between open windows    | CM    |
| `<C-j>`     | Focus the window to the left  | CM    |
| `<C-k>`     | Focus the windwow below       | CM    |
| `<C-l>`     | Focus the window above        | CM    |
| `<C-w>w`    | cycle between open windows    | OOB   |
| `<C-w>h`    | Focus the window to the left  | OOB   |
| `<C-w>j`    | Focus the windwow below       | OOB   |
| `<C-w>k`    | Focus the window above        | OOB   |
| `<C-w>l`    | Focus the window to the right | OOB   |

## Closing Windows
| key binding | action                         | notes |
|-------------|--------------------------------|-------|
| `:clo[se]`  | close the active window        | OOB   |
| `:on[ly]`   | keep active window, close rest | OOB   |

## Resizing Windows
* I recommend just using mouse (one of RARE times to use mouse)
