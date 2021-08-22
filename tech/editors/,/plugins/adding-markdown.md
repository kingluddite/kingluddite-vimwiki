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
