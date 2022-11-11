# Kitty
Question: In tmux you have shortcuts view of sessions list - 0 through 1 shortcuts are self explanatory but what about (M-a) how can I use that shortcut?

![view of tmux list view](https://i.imgur.com/sW6EyRh.png)

Answer: M-a means "Meta-a", which is usually Alt-a in most terminal programs (in Apple's Terminal.app you must enable the app preference "Use option as Meta key" before this will work). So, in this case, the key combination Alt-a will take you to that session directly. Additional sessions will be reachable via Alt-b, Alt-c, Alt-d, etc.

* this Documentation of kitty shows best way is to use kitty config file with this option `https://github.com/kovidgoyal/kitty/issues/155`

uncommented this entry in the kitty configuration which I found further down.

macos_option_as_alt yes

so no you just hit the alt key and it will be the meta
so to hit the (M-a) shortcut you hit `alt-a` 

