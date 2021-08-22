# Vimwiki

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

