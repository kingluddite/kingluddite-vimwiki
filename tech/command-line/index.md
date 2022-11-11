# Command Line
## Copy a File or Folder Path to the Terminal by Dragging and Dropping
* Did you know you can quickly copy a files path to the Terminal just by dragging and dropping the folder or file into the Terminal window? Try it out, open any terminal window then take something from the Finder and drop it into that Terminal, it’ll instantly print out the full path to the file, effectively copying the file path from the Macs Finder GUI to the command line.
* Prefixing the drag & drop with a command makes it easy to execute with the path or file in question as well, for example:

`$ cd (drag and drop a folder here)`

* Open some deep file in nvim by doing the same thing:
 
`$ nvim (drag and drop a folder here)`

* Or if you just wanted to see the contents of a specific file in the Finder as dumped through ‘cat’ or ‘less’ you could do something like this:

`$ less (drag and drop a folder here)`

## Copy the Current Path from Terminal to the Clipboard in Mac OS X
* While it’s fairly easy to copy a folder path from the Mac GUI and Finder, or even to copy the path into the Terminal with a drag & drop trick, going the other direction and getting the current path from the command line and then having it accessible to the broader OS X clipboard is a little trickier… well, at least until you know this handy little tip.

`$ pwd|pbcopy`

* Tip - If you plan on using this often, you could always make an alias for it within your profile by adding a line like this to `.bash_profile` or `.zshrc`:

.zshrc

```
alias copypath='pwd|pbcopy'
```
