# Sessions 
  
  
| key binding                                                 | action                           | notes                                             |
|-------------------------------------------------------------|----------------------------------|---------------------------------------------------|
| <kbd>ctrl-a</kbd> + <kbd>s</kbd>                            | show sessions                    |                                                   |
| <kbd>ctrl-a</kbd> + <kbd>d</kbd>                            | detach from sessions             |                                                   |
| `$ tmux new-session -s development`                         | detach from sessions             | outside tmux                                      |
| `$ tmux kill-session -t NAME_OR_NUMBER`                     | kill session with name or number | Don't be inside the session you are trying to end |
| <kbd>ctrl</kbd> + <kbd>x</kbd> + answer `y` to kill session | detach from sessions             | Don't be inside the session you are trying to end                                      |



