# Vimwiki

## Default vim that no longer work because I overwrote them 
| binding      | action                                | notes                                             |
|--------------|---------------------------------------|---------------------------------------------------|
| `<leader>ww` | open vimwiki                          |                                                   |

## Navigation
| binding       | action                          | notes |
|---------------|---------------------------------|-------|
| `<CR>`        | follow/create link              |       |
| `<C-s-CR>`    | follow/create link in new tab   |       |
| `<backspace>` | go back to previous wiki page   |       |
| `<Tab>`       | go to next link on current page |       |
| `<S-Tab>`     | go to next link on current page |       |

## Editing 
| binding     | action                        | notes  |
|-------------|-------------------------------|--------|
| `<C-Space>` | toggle list item on/of        |        |
| `=`         | add header level              |        |
| `-`         | remove header level           |        |
| `+`         | create/decorate links         |        |
| `glm`       | increase indent of list item  |        |
| `gll`       | decrease indent of list item  |        |
| `gl*`       | switch or insert "*" symbol   | or gl8 |
| `gl#`       | switch or insert "#" symbol   |  |
| `gl-`       | switch or insert "-" symbol   |  |
| `gl1`       | switch or insert "1." symbol  |  |

## Wiki Management

- [number] `<leader> ww` - open wiki index file
- [number] `<leader> wt` - open wiki index file in new tab
- `<leader> ws` - list and select available wikis
- `<leader> wd` - delete wiki page
- `<leader> wr` - rename wiki page

## Diary management

- [number] `<leader> wi` - open diary index file for wiki
- `<leader> w <leader> i` - update current diary index
- [number] `<leader> w <leader> w` - open today’s diary file for wiki
- [number] `<leader> w <leader> t` - open today’s diary file for wiki in new tab
- `<C-Up>` - open previous day’s diary
- `<C-Down>` - open next day’s diary

## Table shortcuts

- `<A-Left>`	move column left
- `<A-right>`	move column right
- `<CR>`	(insert mode) go down/create cell
- `<Tab>`	(insert mode) go next/create cell
- `gqq` or `gww`	reformat table

## Text objects

`ah`	section between 2 headings including empty trailing lines
`ih`	section between 2 headings excluding empty trailing lines
`a\`	table cell
`i\`	inner table cell
`ac`	table column
`ic`	inner table column
## Setup
* I made my vimwiki file a repo on Github <a href="https://github.com/kingluddite/kindluddite-vimwiki" target="_blank">My Vimwiki</a>
* There are changes in Dropbox (mid 2019 Dropbox dropped it's support for symlinks that link to outside your Dropbox folder for performance reasons). The new way to sync up is below and I used it to sync my vimwiki with dropbox
<a href="https://www.cloudwards.net/how-to-sync-folders-outside-the-dropbox-folder/" target="_blank">This article: how to sync folders outside the Dropbox folder in 2021</a>

### Sync vimwicki with Dropbox instructions:
* The full command `$ ln -s <PATH_TO_ORIGINAL_FOLDER> <PATH_TO_TARKET_FOLDER> ` will create your symlink when you press “enter.” Then you can use Finder to access the files as if they were still in their original place.

![IMG sync command](https://i.imgur.com/Edb2QlM.png)

## Useful articles
* [working with vimwiki](https://mkaz.blog/working-with-vim/vimwiki/)
* [cheatsheet](https://gist.github.com/drkarl/4c503bccb62558dc85e8b1bc0f29e9cb)
* [steve.dondley.com](https://steve.dondley.com/vimwiki/)
* [thedardestthing.com](http://thedarnedestthing.com/vimwiki%20cheatsheet)

## Open Absolute URLs in new tab
* The best way to do this is just code an HTML `<a href="URL" target="_blank">EXTERNAL LINK</a>`

## How to create a table
* Make sure you are in command mode
* `:VimwikiTable 5 3` to create a table with 5 columns and 2 rows
* Press tab to advance to the next column (it auto-formats as you go)
* Press enter on the last row to create another row

## Indent a list item
`<Ctrl-t>`

## Outdent a list item
`<Ctrl-d>`

## Searching and navigating a vimwiki quickly
* Use [CtrlP](./ctrlp.md) plugin to jump to files
* Searching the wiki:
  * use `:VWS /term/`
    * use `:lopen` to see results

## Useful articles
* [working with vimwiki](https://mkaz.blog/working-with-vim/vimwiki/)
* [cheatsheet](https://gist.github.com/drkarl/4c503bccb62558dc85e8b1bc0f29e9cb)

## How to create a table
* Make sure you are in command mode
* `:VimwikiTable 5 3` to create a table with 5 columns and 2 rows
* Press tab to advance to the next column (it auto-formats as you go)
* Press enter on the last row to create another row

## Indent a list item
<kbd>ctrl</kbd> + <kbd>t</kbd>

## Outdent a list item
<kbd>ctrl</kbd> + <kbd>d</kbd>

## Resources
* https://gist.github.com/drkarl/4c503bccb62558dc85e8b1bc0f29e9cb
