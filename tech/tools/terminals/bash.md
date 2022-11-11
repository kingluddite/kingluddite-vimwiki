# Bash

## Which shell?
* want to have the very basic bash shell when I teach so students learning the shell don't wonder why my shell looks so different but when I work i want my shell to be zsh and nice and pretty - how can I do this?

### Which shell am I running?
`$ echo $0`

Or you can just type gibberish in your command prompt and the error will tell you which shell you are running

## zsh or bash
* For license reasons modern Mac OS default to zsh

### change to bash
`$ chsh -s $(which bash)`

* My bash looked terrible as my zsh profile just didn't look right ever - never figured out how to get it to look cool but I need it to not look cook for students and go back to basics - the above change did not work and I also had to go into Terminal setting and point the start up of my Terminal to be `/bin/bash` (https://i.imgur.com/fCT7ao2.png)
* After making Terminal changes to settings always shut down and reset to see your changes take affect (shells have sessions and you need a new session to see any modifications to settings)
* **I also use Kitty and iTerm and they also reverted to bash and I did not want this so I used `$ chsh -s $(which zsh)` and restarted iterm and kitty to get them working
* I also turned off fig.io app to make sure my bash terminal is just like the students

### Reference
https://www.moncefbelyamani.com/which-shell-am-i-using-how-can-i-switch/
