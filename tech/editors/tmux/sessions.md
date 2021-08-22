# Sessions 
  
| key binding                                                 | action                           | notes                                             |
|-------------------------------------------------------------|----------------------------------|---------------------------------------------------|
| `<Ctrl-a> s`                                                | show sessions                    |                                                   |
| `<Ctrl-a> d`                                               | detach from sessions             |                                                   |
| `$ tmux new-session -s development`                         | detach from sessions             | outside tmux                                      |
| `$ tmux kill-session -t NAME_OR_NUMBER`                     | kill session with name or number | Don't be inside the session you are trying to end |
| `Ctrl</kbd> + <kbd>x</kbd> + answer `y` to kill session     | detach from sessions             | Don't be inside the session you are trying to end |

## Delete from list of sessions
* Hover over the session you want to delete in the dropdown list and press `x` and then confirm your decision with `y`
