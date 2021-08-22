# tmux
## cheatsheets
https://tmuxcheatsheet.com/

[[Panes]]
[[Buffers]]
[[Sessions]]
[[Copy Mode]]

## Prefix
The Prefix is huge in Tmux. This is the key you press before pressing another key. The default `Prefix` is <kbd>ctrl-b</kbd> but I changed it to `Prefix` + <kbd>ctrl-a</kbd> which adds the advantage of keeping you hands on the "home keys"

## Here are high level key bindings for generic Tmux commands

| binding                 | action                   | note |
|-------------------------|--------------------------|------|
| `Prefix` + <kbd>?</kbd> | search tmux key bindings |      |

## Tmux default Prefix
* I turned mouse off (this makes navigating harder)ls
* Default Prefix is `ctrl-b`
* But I changed it to `ctrl-a` (home keys!)

## start up tmux
`$ tmux`

## kill a window
`ctrl-a` x then type `y` when it asks you to delete window


## reload tmux without closing down tmux
`Prefix-r`



## Save tmux resurrect 
`Prefix` + `ctrl-s`

## Restore tmux resurrect
`Prefix` + `ctrl-r`

## Resizing panes
* Prefix H,J,K,L (shift)


## Windows
### Move to next window
`Prefix` + `n`

### Move to previous window
`Prefix` + `p`e

### Kill all servers
`$ killall tmux`
