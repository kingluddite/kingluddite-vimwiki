# Spell Check

| binding    | action                               | notes                                            |
|------------|--------------------------------------|--------------------------------------------------|
| `s]`       | go to next error                     |                                                  |
| `[s`       | go to previous error                 |                                                  |
| `]S`       | only go to next bad words            | (not rare words, or words from other region)     |
| `[S`       | only go to previous bad words        | (not rare words, or words from other region)     |
| `z=`       | after locate word, find suggestions  | (pick correct word by typing number + `<ENTER>`) |
| `zg`       | add word to spellfile                | these are non-words you use a lot                |
| `zug`      | remove word from spellfile           |                                                  |
| `zw`       | add bad word                         |                                                  |
| `zuw`      | add bad word                         |                                                  |
| `<ctrl-n>` | select next word to autocomplete     | `Insert` mode                                    |
| `<ctrl-p>` | select previous word to autocomplete | `Insert` mode                                    |
 
* **note** Please read my notes on the [gruvbox](./nvim/plugins/themes/gruvbox.md) theme as it needs some configuration to get spell check working with it 

## How to enable Spell Check
`:set spell`

## Word Completion
``````
" let us press <ctrl-n> or <ctrl-p> in insert-mode to complete the word when
"  are typing
set complete+=kspell
```

## How to set Spell Language
* I use English

`:set spell spelllang=en_us`


### Variations of English regions are:
* en - all regions
* en_au - Australia
* en_ca - Canada
* en_gb - Great Britain
* en_nz - New Zealand
* en_us - USA

## How to add words to Spellfile
* When you want to add some words as exceptions (words you use a lot but are not in dictionary) add these words in the `Spellfile` (**tip** Add this inside your Dropbox folder so you can sync across computers)

1. Create the file
2. Set spellfile with `:set spellfile=/PATH_TO_SPELLFILE`
3. Locate the words you want to add using `[s` and/or `]s` and type `zg`
4. To remove a word from spellfile type `zug` while over that word
5. To mark the mispelled word type `zw` (to undo this action type `zuw`)

## How to Disable Spell Check in Vim 
`:set nospell`

## Enable Spell Check
`:set spell`

## Help with Spell Check
`:help spell`

```
:help ]s
:help [s
:help z=
:help zg
:help zug
:help zw
:help zuw
:help spelllang
:help spellfile
:help spellfile-cleanup
```

## Show how to add settings in `.vimrc` instead of as `EX commands`
TODO

## What is bg color of SpellBad?
`:verbose highlight SpellBad` - If the `xxx` at the start of the line is not highlighted, then badly spelled words will not be highlighted, either

## Resources
* <a href="https://thoughtbot.com/blog/vim-spell-checking" target="_blank">Vim Spell-Checking</a>
* <a href="http://vimdoc.sourceforge.net/htmldoc/spell.html" target="_blank">Online Vim Spell docs</a>
* <a href="https://vi.stackexchange.com/questions/18295/how-to-set-a-colorscheme-that-still-shows-spelling-errors" target="_blank">Hot to set a colorscheme that still shows spelling errors?</a>
* <a href="https://ostechnix.com/use-spell-check-feature-vim-text-editor/" target="_blank">How to use spell check in Vim</a>
* <a href="https://ostechnix.com/use-spell-check-feature-vim-text-editor/" target="_blank"></a>
