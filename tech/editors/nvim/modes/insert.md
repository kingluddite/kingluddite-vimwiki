# Insert Mode
* `zt`, `zz`, `zb` leaves the cursor in the current screen
* **note** I was having issues with my Sneak plugin with the `z.` command
* note I use `zz` to save so that command does not work
* **note** I was having issues until I set my `scrolloff=5` in my `.vimrc` (I did not set it to `scrolloff=0` to give me a little legroom)

| Trigger           | Effect                                            | Notes                     |
|-------------------|---------------------------------------------------|---------------------------|
| `<Esc>`           | Switch to normal mode                             | classic way               |
| `<C-[>`           | Switch to normal mode                             |                           |
| `<C-o>`           | Switch to normal mode                             |                           |
| `<j-k>`           | Switch to normal mode                             | custom                    |
| `z<CR>`           | Puts current line to top of screen                |                           |
| `zt`              | Puts current line to top of screen                |                           |
| `z.`              | Puts current line to center of screen             |                           |
| `zz`              | Puts current line to center of screen             | I overrode this with save |
| `z-`              | Puts current line to bottom of screen             | I overrode this with save |
| `<line#>z<t/z/b>` | Put the line number at top/center/bottom          |                           |
| `<C-h>`           | Delete back one character (backspace)             |                           |
| `<C-w>`           | Delete back one word                              |                           |
| `<C-u>`           | Delete back to start of line                      |                           |
| `<C-r>=10*10<CR>` | Use the `expression register` to do calculations  | will enter 100            |
| `<C-v>{code}`     | Add a symbol                                      | `<C-v>u00bf` ->  `¿`      |
| `<C-v>{code}`     | Add a symbol                                      | `:h i_CTRL-V_digit`      |

## Insert Unusual Characters (digigraphs)
* From time to time you will use this to insert uncommon characters
* The default key binding is `<C-k>` but in my setup that is already mapped to something else
* **remember** if you ever need to find if something is mapped to something else do this:

`:verbose imap <C-k>` (substitute what you mapping you are searching for)

* Since I won't use this a lot I like to temporarily remap `<C-k>` to `<C-n>` with this:

`:inoremap <C-n> <C-k>`

* Now if you type `<C-n>` you will see a grey `?` where your cursor was and now you use this digigraph key - <a href="http://www.alecjacobson.com/weblog/?p=443" target="_blank">digigraph symbols</a> or you can just type `:digigraph` to search for your symbol, enter the symbol and you will see it inside vim

| Keystrokes            | Effect                               |
|-----------------------|--------------------------------------|
| `<C-v>{123}`          | Insert character by decimal code     |
| `<C-v>{1234}`         | Insert character by hexadecimal code |
| `<C-v>{nondigit}`     | Insert nondigit literally            |
| `<C-k>{char1}{char2}` | Insert nondigit literally            |

## What are digigraphs?
* Pairs of characters that are easy to remember

## Man Pages: scroll-cursor
* You can get all this info using `help scroll-cursor`

## Insert Normal Mode
* Special mode that lets us fire off one single command then return us to normal mode
* So `<C-o>zz` should take you into Normal mode, you fire `z.` to take you to the middle of your page and then you are right back into Insert mode
  * **note** I overwrote Insert Normal Mode with `<C-o>` which opens up my NerdTree sidebar
