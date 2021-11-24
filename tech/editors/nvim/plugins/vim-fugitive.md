# Vim Fugitive
* Makes working with Git soooo easy

## vim-fugitive settings
```
nmap <leader>gh :diffget //3<CR>
nmap <leader>gu :diffget //2<CR>
nmap <leader>gs :G<CR>

```

## How to check your vim status
`<leader>gs` And that will open and show you your status

## Git add
* Check status and type `s` over unstaged to add all
* Or individually navigate to files and type `s` to do one by one

## Git commit
`:Git commit`

## Git push
`:Git push`

## Handle merge conflicts
1. Open the git status
2. Hover over the Unstaged file that caused the commit and type `dv`
3. That will open up 3 columns, the left and right are the two conflicting files and the middle is the merged content
4. Let's pretend we need to fix three conflicts in one file
5. Navigate to the middle part you want to first fix
6. If you want to bring the left file content to the middle file type `:diffget //2`
7. Navigate to the middle file to the second part you want to resolve the conflict 
8. If you want to bring the right column content to the middle file type `:diffget //3`
9. Navigate in the middle file to the 3rd and final conflict and manually resolve it
10. Now you need to close the window with `<C-w><C-O>`
11. Everything has been merged
12. If you're COC is confused with changes restart it with `:CocRes<CR>`
13. Check your status menu `<leader>gs`


