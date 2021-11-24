# THe Command-Line (CLI)

### CLI common command
| Trigger               | Effect                                                 |
|-----------------------|--------------------------------------------------------|
| `$ <C-r>`             | Search command-line history for commands I used before |
| `$ ls`                |                                                        |
| `$ pwd`               |                                                        |
| `$ touch [FILE.EXT]`  |                                                        |
| `$ mkdir [DIRECTORY]` |                                                        |
| `$ cd [DIRECTORY]`    |                                                        |
| `$ cd`                | Go to $HOME directory (aka `~`)                        |
| `$ ls -la`            | List all files and folders (even hidden)               |
| `$ ..`                | Go up one directory (ie `$ cd ..`)                     |

* Press `<C-r>` and type your term (example: `$ <C-r> ssh`)
* `<C-r>` will start search from most recent command to old one (reverse-search)
* If you have more than one command which starts with your search term (ie `ssh`), Press `<C-r>` again and again until you find the match
* Once you've found the match press `<Enter>` to execute the command or `left` / `right` cursor to just select the text of the command
