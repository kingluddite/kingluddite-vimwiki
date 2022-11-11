# Sessions 
  
| key binding                             | action                                    | notes                                             |
|-----------------------------------------|-------------------------------------------|---------------------------------------------------|
| `<Ctrl-a> s`                            | show sessions                             |                                                   |
| `<Ctrl-a> d`                            | detach from sessions                      |                                                   |
| `$ tmux new-session -s development`     | new session with name                     | outside tmux                                      |
| `$ tmux kill-session -t NAME_OR_NUMBER` | kill session with name or number          | Don't be inside the session you are trying to end |
| `C y`                                   | shortcut to kill session for session list | Don't be inside the session you are trying to end |

## Opening past session without creating a new session 
* If you just type `$ tmux` you will open all existing sessions and create a new one by default. This becomes problematic over time because you will be creating lots of sessions when this is not what you want, you just want to just back in to a past session - just type `$ tmux attach` you can name the session you want to attach to or just leave it off and it will attach to the last session you were in by default (if you have no sessions, you can use resurrect to bring the sessions back if you saved them)
* **TIP** Even better put this line in your tmux config file:

## Delete from list of sessions
* Hover over the session you want to delete in the dropdown list and press `x` and then confirm your decision with `y`
* Or `$ tmux kill-session -t [name of session]`
* example `$ tmux kill-session -t 0` (most of the time people forget to name sessions so they will be deleting a session named with a number)

`tmux config file`

```
# if run as "tmux attach", create a session if one does not already exist
new-session -n $HOST
```
## Rename a session 
* Most users when starting to use Tmux forget to name the session they are working in. But as the number of sessions increases with the workflow, it becomes a pain to remember the session you were working in and the related services that were running in them 
  * **Tip** Always start a session with a name to avoid any confusion 
    * But if you have forgotten to name a session while creating it, no problem, you can still give it a name or change an existing name

## Name a session when you first create it (otherwise it will default to a number)

`$ tmux new -s my_session_1`

### Give it a name
* To rename a session from shell prompt using Tmux ‘rename-session’ command, use the format:

`$ tmux rename-session -t old-session-name new-session-name`
 
* Example: 
* **Note** If you didn't create a session name when you first created a number, the session name will be an unhelpful number so you rename this session with:

#### TIP - Shortcut
* Rename current session (if you don't know name view inside tmux with `Prefix s` or outside tmux with `$ tmux ls`)
 
* [resource](https://linuxhint.com/rename-session-tmux/)
