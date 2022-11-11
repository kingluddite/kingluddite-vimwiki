# Panes

## Synchronize Panes
* **note** if you have fig installed and are running `$ npm start` you will see sync works but if you see fig drop down and press `enter` it will only fire in one terminal. You need to press `esc` key to escape out of fig drop down, then press `enter` and `$ npm start` will work across tmux window panes
* Open a bunch of windows and type in one and then type in all at same time

1. Create a new session. `$ tmux new -t random`
2. Split the window into multiple panes. For vertical splitting you can use the shortcut `[prefix] %` , for vertical use `[prefix] "`
3. Synchronize Panes. Use the command prefix `:setw synchronize-panes` to run the same command on all panes
4. To disable this you can re-run the above command(`[prefix]:setw synchronize-panes`) to toggle the functionality 

## Resizing panes
* Prefix H,J,K,L (shift)

| keyboard binding    | action                  | notes                       |
|---------------------|-------------------------|-----------------------------|
| Prefix <kbd>z</kbd> | Zoom pane               | >= version 1.8              |
| Prefix <kbd>%</kbd> | Split pane horizontally | Prefix -                    |
| Prefix <kbd>"</kbd> | Split pane vertically   | Prefix PIPE (shift)         |
| Prefix <kbd>k</kbd> | Move to the TOP pane    |                             |
| Prefix <kbd>l</kbd> | Move to the RIGHT pane  |                             |
| Prefix <kbd>j</kbd> | Move to the BOTTOM pane |                             |
| Prefix <kbd>h</kbd> | Move to the LEFT pane   |                             |
| exit                | Close pane exit         |                             |
