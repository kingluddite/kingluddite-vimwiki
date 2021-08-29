# tmux

[Buffers](./tmux/buffers.md)
[Copy Mode](./tmux/copy-mode.md)
[Panes](./tmux/panes.md)
[Sessions](./tmux/sessions.md)
[Windows](./tmux/indows.md)

## What is tmux?
* tmux is a terminal multiplexer. It lets you use a single environment to launch multiple terminals, or windows, each running its own process or program

## Explaining the key bindings
* `<Ctrl-b>` means "press the `Ctrl` and `b` keys simultaneously"
* `<Ctrl-R>` means "press the `Ctrl` and `R` (holding `<Shift>` key down) keys simultaneously"
* `<Ctrl-b> d` means "press the `Ctrl` and `b` keys simultaneously, then release, and then press `d`"
* If you see a command prefixed with `$` this is a terminal command
* If you see a command prefixed with `:` this is inside tmux

## Prefix
The Prefix is huge in Tmux. This is the key you press before pressing another key. The default `Prefix` is `<Ctrl-b>` but I changed the `Prefix` to `<Ctrl-a>` which adds the advantage of keeping your hands on the "home keys"

## Tmux default Prefix
* I turned mouse off (this makes navigating harder)
* Default Prefix is `<ctrl-b>`
* But I changed it to `<ctrl-a>` (home keys!)
* I used <a href="https://karabiner-elements.pqrs.org/" target="_blank">Karabiner-Elements (A keyboard customizer for macOS)</a> to change my Prefix from the default `ctrl-b` to `ctrl-a` (see screenshot below)

![IMG switch caps lock to left <ctrl>](https://i.imgur.com/mANdoxO.png)

* I love this change because it keeps my Prefix on <a href="https://medium.com/usevim/the-importance-of-the-home-row-f65a43dde1fd" target="_blank">the Home Keys</a>

## High level key bindings for Tmux commands
* [Resurrect](https://github.com/tmux-plugins/tmux-resurrect) is a Tmux plugin

| binding           | action                   | notes                                                                  |
|-------------------|--------------------------|------------------------------------------------------------------------|
| `Prefix + ?`      | search Tmux key bindings |                                                                        |
| `Prefix + r`      | Reload Tmux config       |                                                                        |
| `$ tmux`          | start Tmux               |                                                                        |
| `$ killall tmux`  | kill all Tmux servers    |                                                                        |
| `Prefix <Ctrl-r>` | resurrect Tmux sessions  | even if you turn computer off this will restore all your Tmux sessions |
| `Prefix <Ctrl-s>` | save Tmux sessions       | save all your Tmux sessions                                            |

## Adding ruby for tmuxinator
* `tmuxinator` <a href="https://github.com/guyhughes/tmuxinator" target="_blank">tmuxinator docs</a> is a simple tool you can use to define and manage different tmux configurations
    - You can use tmuxinator to create complex layouts when you open a tmux session. See the screenshot below for an example

![IMG complex tmuxinator layout](https://i.imgur.com/EMrVgcq.png)
* tmuxinator requires the Ruby interpreter (so you need to have that on your system)
    - Ruby is already on Mac
    - However if y ou plan to use Ruby for anything beyond tmuxinator it is strongly incouraged to install Ruby through RVM
    - I used [this site](https://kemalmutlu.medium.com/installing-ruby-on-rails-macbook-pro-m1-4272da855fb3)
* On the macOs M1 use iTerm and open it via Finder and check `Open using Rosetta` option

### Install ruby and rbenv

`$ brew install rbenv ruby-build`

```
# Add rbenv to bash so that it loads every time you open a terminal
$ echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.zshrc
source ~/.zshrc
# Install Ruby
$ rbenv install 2.7.2
$ rbenv global 2.7.2
$ ruby -v
```

### Install tmuxinator
* Now you can install tmuxinator

`$ gem install tmuxinator`

## Resources
### cheatsheets
https://tmuxcheatsheet.com/
