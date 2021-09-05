# gruvbox (theme)
* [Spell Check](../spell-check.md) with this theme is tricky
* Out of the box there was no background color for errors (Spell Bad)

## Give backgrounds to misspelled words
`g:gruvbox_guisp_fallback='bg'`

* So in my themes folder I added this to my gruvbox file 

```
" Enable true colors if available
set termguicolors
" Needed to give spellcheck bad words a background
let g:gruvbox_guisp_fallback = "bg" "this was the line I added"
colorscheme gruvbox
```

## Next Problem - The Spell Bad background color is blue
* <a href="https://github.com/gruvbox-community/gruvbox/issues/28" target="_blank">This post explains why</a> long story short is a person wanted to update add a PR to the gruvbox theme but the creator didn't seem to care to update and for several years it remained in limbo. It says there was an update but I updated the plugin and it is still the same code with the same blue background

### Here is where you can find the gruvbox theme stored
`/Users/YOURUSER/.config/nvim/autoload/plugged/gruvbox/colors/gruvbox.vim``

* This is a bad way to update the bg color because if there are any updates to this gruvbox theme and I perform a `:PluginUpdate` my changes will get overwritten (TODO: maybe I need to do a fork?)

#### Here is the code with the blue bg
```
if has("spell")
  " Not capitalised word, or compile warnings
  if g:gruvbox_improved_warnings == 0
    call s:HL('SpellCap',   s:none, s:none, s:undercurl, s:red)
  else
    call s:HL('SpellCap',   s:green, s:none, s:bold . s:italic)
  endif
  " Not recognized word
  call s:HL('SpellBad',   s:none, s:none, s:undercurl, s:blue)
  " Wrong spelling for selected region
  call s:HL('SpellLocal', s:none, s:none, s:undercurl, s:aqua)
  " Rare word
  call s:HL('SpellRare',  s:none, s:none, s:undercurl, s:purple)
endif
```
* And here is my update to make the background red
  - I just updated `SpellBad` to `red`

```
if has("spell")
  " Not capitalised word, or compile warnings
  if g:gruvbox_improved_warnings == 0
    call s:HL('SpellCap',   s:none, s:none, s:undercurl, s:red)
  else
    call s:HL('SpellCap',   s:green, s:none, s:bold . s:italic)
  endif
  " Not recognized word
  call s:HL('SpellBad',   s:none, s:none, s:undercurl, s:red)
  " Wrong spelling for selected region
  call s:HL('SpellLocal', s:none, s:none, s:undercurl, s:aqua)
  " Rare word
  call s:HL('SpellRare',  s:none, s:none, s:undercurl, s:purple)
endif
```

## Resources 
<a href="https://github.com/gruvbox-community/gruvbox/issues/28" target="_blank">Highlight for spelling errors is switched</a>
