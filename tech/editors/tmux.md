# tmux
* tmux is a terminal multiplexer. It lets you use a single environment to launch multiple terminals, or windows, each running its own process or program

## Explaining the key bindings
* `<Ctrl-b>` means "press the `Ctrl` and `b` keys simultaneously"
* `<Ctrl-R>` means "press the `Ctrl` and `R` (holding `<Shift>` key down) keys simultaneously"
* `<Ctrl-b> d` means "press the `Ctrl` and `b` keys simultaneously, then release, and then press `d`"
* If you see a command prefixed with `$` this is a terminal command
* If you see a command prefixed with `:` this is inside tmux

[Buffers](./tmux/buffers.md)
[Copy Mode](./tmux/copy-mode.md)
[Panes](./tmux/panes.md)
[Sessions](./tmux/sessions.md)
[Windows](./tmux/indows.md)

## Prefix
The Prefix is huge in Tmux. This is the key you press before pressing another key. The default `Prefix` is `<Ctrl-b>` but I changed the `Prefix` to `<Ctrl-a>` which adds the advantage of keeping your hands on the "home keys"

## Tmux default Prefix
* I turned mouse off (this makes navigating harder)
* Default Prefix is `ctrl-b`
* But I changed it to `ctrl-a` (home keys!)

## High level key bindings for Tmux commands
* [Resurrect](https://github.com/tmux-plugins/tmux-resurrect) is a Tmux plugin

| binding           | action                   | notes                                                                  |
|-------------------|--------------------------|------------------------------------------------------------------------|
| `Prefix + ?`      | search Tmux key bindings |                                                                        |
| `$ tmux`          | start Tmux               |                                                                        |
| `$ killall tmux`  | kill all Tmux servers    |                                                                        |
| `Prefix <Ctrl-r>` | resurrect Tmux sessions  | even if you turn computer off this will restore all your Tmux sessions |
| `Prefix <Ctrl-s>` | save Tmux sessions       | save all your Tmux sessions                                            |

## Resources
### cheatsheets
https://tmuxcheatsheet.com/
