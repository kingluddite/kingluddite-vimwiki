# Adding Markdown
* Here's how I added Markdown and use it in nvim
* [great youtube video on setting up markdown in vim](https://www.youtube.com/watch?v=22JAs0kNA9k)
## Add these plugins to `.vimrc`
```
// MORE CODE

Plug 'godlygeek/tabular' | Plug 'tpope/vim-markdown'
Plug 'iamcco/markdown-preview.nvim', { 'do': 'cd app & yarn install' }

" Dim paragraphs above and below the active paragraph (optional theme)
Plug 'junegunn/limelight.vim'

" Distraction free writing by removing UI elements and centering everything.
Plug 'junegunn/goyo.vim'

// MORE CODE
```

| key binding        | action                        | note |
|--------------------|-------------------------------|------|
| `:MarkdownPreview` | open markdown file in browser |      |

* TODO: Images don't show up in MarkdownPreview
  - Solution: Change `127.0.0.1` to `localhost`
* Make Markdown look like GitHub Markdown CSS [repo](https://github.com/sindresorhus/github-markdown-css)

## Folding Markdown
* **note** Folding is enabled for headers by default

| key binding | action                                     | note |
|-------------|--------------------------------------------|------|
| `zr`        | reduces fold level throughout the buffer   |      |
| `zR`        | opens all folds                            |      |
| `zm`        | increases fold level throughout the buffer |      |
| `zM`        | folds everything all the way               |      |
| `za`        | open a fold your cursor is on recursively  |      |
| `zc`        | close a fold your cursor is on             |      |
| `zC`        | close a fold your cursor is on recursively |      |

## Other Import Key Bindings
| key binding | action              | note         |
|-------------|---------------------|--------------|
| `>`         | Indent bullet list  | hold <Shift> |
| `<`         | Outdent bullet list | hold <Shift> |

## Troubleshooting vim-markdown
* I was having a problem indenting with vim-markdown as described <a href="https://github.com/plasticboy/vim-markdown/issues/126" target="_blank">here</a>
* Essentially when you start a bullet list you want this to be the behavior:

```
* one
* two
```

*  But instead you are getting this:

```
* one
  * two
```

* The solution is to add this to your `.vimrc`

```
autocmd FileType markdown set indentexpr=
```

* Then refresh nvim with `:source $MYVIMRC`

## Getting Markdown to work with Ultisnips 
* I following <a href="https://jdhao.github.io/2019/01/15/markdown_edit_preview_nvim/" target="_blank">This tutorial</a> and when I tried to use `<tab>` i found the tab was being using by vimwiki and <a href="https://github.com/vimwiki/vimwiki/issues/357" target="_blank">This issue gave me the solution</a> which was to make my `vimwiki plugin settings` look like this: 
  
`/.config/nvim/plugin-config/vimwiki.vim`

  ```
  let g:vimwiki_list = [{'path':'~/vimwiki', 'syntax': 'markdown', 'ext': '.md'}]
  let g:vimwiki_ext2syntax = {'.md': 'markdown', '.markdown': 'markdown', '.mdown': 'markdown'}

  " makes vimwiki markdown links as [text](text.md) instead of [text](text)
  let g:vimwiki_markdown_link_ext = 1

  let g:taskwiki_markup_syntax = 'markdown'
  let g:markdown_folding = 1

  " I was having problems with ultisnips playing nice with vimwiki because of tab
  " This shows the issue and solution - https://github.com/vimwiki/vimwiki/issues/357
  let g:vimwiki_global_ext = 0
  let g:vimwiki_key_mappings = { 'table_mappings': 0 }
  ```

* I added these two plugins:

```
Plug 'SirVer/ultisnips'
Plug 'honza/vim-snippets'
```

* I added this to my ultipsnips config 
  
  
  ```
  " Trigger configuration. Do not use <tab> if you use https://github.com/Valloric/YouCompleteMe.
  let g:UltiSnipsExpandTrigger="<tab>"  " use <Tab> to trigger autocompletion
  let g:UltiSnipsJumpForwardTrigger="<c-j>"
  let g:UltiSnipsJumpBackwardTrigger="<c-k>"
  ```

* And now when I type in a markdown file `link` + `<tab>` it gives me the snippet `[Text](http://www.url.com)` 
  
## resources
https://jdhao.github.io/2019/01/15/markdown_edit_preview_nvim/
