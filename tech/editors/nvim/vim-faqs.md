# NVIM FAQs
## How do I vertically select the column
* I want to capitalize 10 lines of code

`C-v` over the first line, first character and type `j` to highlight the next line below and repeat as needed

## How can i wrap long lines?
1. highlight range to wrap
2. `gq`

## How can I quickly create lots of folders?
`$ mkdir section-{03,04,05,07,08,09,10,11,12,13,14,15,16,17,18}`

## How can I copy the current path into the clipboard (macos)?
`$ pwd|pbcopy`

## Fast way to copy all text of a file
`gg"+yG`

* Explanation
  * `gg` to get the cursor to the first character of the file
  * `"*y` to start a yank command to the register `*` from the first line, until...
  * `G` to go the end of the file

| key binding   | action                                        |
| ------------- | --------                                      |
| `vip`         | select all of a block of css (be inside `{}`) |
| `dip`         | delete block of code (be inside `{}`)         |

## How can I check vim mapping?
* Use this if you feel a mapping is overwriting the mapping you want to use
  * **note** I use `imap` in the below example but replace with what map you are checking 

`:verbose imap <tab>`
## How can I check loaded files in vim?
`:scriptnames`
 
* **notes**
  * plugins that are optional will have `/opt` in their path
  * if the path to a plugin contains `start` instead of `opt` it will be enabled by defualt

  
