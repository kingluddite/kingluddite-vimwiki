# Ultisnips
* Ultisnips integrates automatically with the auto-completion engine <a href="https://vimawesome.com/plugin/deoplete-nvim" target="_blank">deoplete</a>
* If you have installed deoplete, you will see the auto-completion menu for your snippet keywords without any settings

## All snippets used by ultisnips can be found here
<a href="https://github.com/honza/vim-snippets/tree/master/UltiSnips" target="_blank">all snippets</a>

## I had to modify the <tab> key
* In the custom config I used different keys to use ultiships as the `<C-i>` was conflicting with my vim jumps list
* Here is that config:

```
" Trigger configuration. Do not use <tab> if you use https://github.com/Valloric/YouCompleteMe.
" I had to remap the <tab> key because it broke my jumps forward
" I want jumps backward to be <C-o>
" And I want my jumps forward to be <C-i>
" In vim <tab> and <C-i> do the same thing so you have to be very
" care when you remap tab
let g:UltiSnipsExpandTrigger="<c-e>"  " use <Tab> to trigger autocompletion
let g:UltiSnipsJumpForwardTrigger="<c-r>"
let g:UltiSnipsJumpBackwardTrigger="<c-t>"
" Here are my custom snippets
let g:UltiSnipsSnippetDirectories=["UltiSnips", "my_snippets"]
```

## Resources
<a href="https://jdhao.github.io/2019/04/17/neovim_snippet_s1/" target="_blank">Configuring Ultisnips for Neovim</a>


