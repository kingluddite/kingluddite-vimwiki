# NERDtree

| binding     | action                      | notes                      |
|-------------|-----------------------------|----------------------------|
| `$ cd CD`   | change to current directory |                            |
| `t`         | change current directory    | not great, adds wacky tabs |
| `<C-[>`     | toggle sidebar              |                            |
| `<s>`       | split file to right         |                            |
| `<m>`       | open menu                   | hover over sidebar         |
| `<Shift-i>` | view hidden files           |                            |


## Menu options
* (a)dd a child
* (m)ove the current node
* (d)elete the current node
* (r)eveal in finder the current node
* (o)pen the current node with the system editor
* (q)uicklook the current node
* copy (p)ath to the clipboard
* (l)ist the current node
* Run (s)ystem command in this directory

## Make NERDTree open in the correct cwd (current working directory)
* From time to time I open a Tmux session in one directory but when I use the `<c-[>` to open NERDTree, NERDTree opens in a different directory. If this happens to use use this:

`:set autochdir`

<a href="https://vi.stackexchange.com/questions/2969/how-to-set-up-nerdtree-to-cd-to-current-folder-when-opening-it-for-the-first-tim" target="_blank">Make sure NERDTree is opening in the current Directory</a>

## Troubleshooting
* I wanted to highlight and delete 3 files inside a folder in NERDTree 
*  but got 'E21 - can not make changes modifieable is off'
* ref -  <a href="https://stackoverflow.com/questions/5745506/vim-modifiable-is-off" target="_blank">modifieable is off error</a>

### adding below allows me to delete multiple files
`set modifiable`
 
* Or ex mode command `:set ma`
