# vim-textobj-entire
* Adds two new text objects to Vim: `ie` and `ae`, which act upon the entire file
* **note** We can define new motions and text objects (learn more here `:h omap-info`)

## How can we auto-indent the entire file?
* `gg=G` (`gg` to jump to top of file and then `=G` to autoindent everything from the cursor position to the end of the file)
* But with `vim-textobj-entire` installed we can just use `=ae`
  * It doesn't matter where our cursor was when we ran this command, it would always act upon the entire file
  * With the commentary plugin and vim-textobj-entire plugin both installed we can use them together
  * `gcae` will toggle commenting throughout the current file

## Troubleshooting
* You will get an error unless you also install <a href="https://vimawesome.com/plugin/textobj-user" target="_blank">textobj-user</a>
