# Organize your Window Layouts with Tab pages
## Opening and Closing Tabs
| Command                 | Effect                                            | 
|-------------------------|---------------------------------------------------|
| `:tabe[dit] {filename}` | Open {filename} in a new tab                      |
| `<C-w>T`                | Move the current window into it's own tab         |
| `:tabc[lose]`           | Close the current tab page and all of its windows |
| `:tabo[nly]`            | Keep the active tab page, closing all the others  |       |

## Switching Between Tabs
| Ex Command       | Normal Command | Effect                          |
|------------------|----------------|---------------------------------|
| `:tabn[ext] {N}` | {N}gt          | Switch to tab page number {N}   |
| `:tabn`          | gt             | Switch to the next tab page     |
| `:tabp[revious]` | gT             | Switch to the previous tab page |
| `:tabmove {N}`   |                | Rearrange tab pages             |
 
* Vim's tabbed interface is different than many other editors
* we can use tab pages to organize split windows into a collection of workspaces

## What is a tab page?
* In Vim, a `tab page` is a container that can hold a collection of windows

## Traditional IDE tabs 
* Feature a main workspace for editing files and a sidebar that shows a directory tree of the current project
  - You click a file in the sidebar it opens a new tab in the main workspace for the specified file
  - In this model, we could say that the tabs represent the set of files that are currently open

## tabs in Vim
* When opening a file with `:edit` command, Vim doesn't automatically create a new tab
  - Instead, Vim creates a new buffer and loads it into the current window
  - Vim keeps track of the set of files that are open using the buffer list
  - Vim's tab pages are not mapped to buffers in a 1-to-1 relationship
    - Instead think of a tab page as a container that can hold a collection of windows

## How to use tabs
* Use Vim tabs to partition work into different workspaces
