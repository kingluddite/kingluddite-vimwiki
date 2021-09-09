# Top Web Troubleshooting Tips
## When I update my OS (macOS) stuff breaks
* Whenever you update the Mac OS, you need to do this, if not you will find Gatsby sites break, working with Git gives you errors, save yourself time and grief and just do this after every Mac OS update

`$ sudo rm -rf /Library/Developer/CommandLineTools`

`$ xcode-select --install`

* You will already have them installed so you first need to remove them and then re-install them
* [ref](https://stackoverflow.com/questions/34617452/how-to-update-xcode-from-command-line)

## How to update npm in a project
* Navigate to root of project

`$ npm update`

## Which of my npm packages are not up to date
`$ npm outdated`

* Go through all and update any "red" outdated modules to the "wanted" version 

## How do I output all my gatsby info?
* This is great for posting a problem to stackoverflow

`$ gatsby info --clipboard`


`$ rm -rf node_modules package-lock.json`

## Show environment info:
`$ npx envinfo --binaries --system`

* Will give output like:

```
  System:
    OS: macOS 11.5.2
    CPU: (8) arm64 Apple M1
    Memory: 111.70 MB / 8.00 GB
    Shell: 5.8 - /bin/zsh
  Binaries:
    Node: 16.7.0 - /opt/homebrew/bin/node
    Yarn: 1.22.10 - /usr/local/bin/yarn
    npm: 7.22.0 - /usr/local/bin/npm
```

`$ node -p 'process.arch'`

* On M1 mac will output - `arm64`

`$ arch` - outputs `i386`


`$ brew config`

* Add this to alias to get M1 ARM and Intell homebrew working
alias brew86="arch -x86_64 /usr/local/bin/brew"
alias brewARM="/opt/homebrew/bin/brew"

* Problem tmux uses intel

* show all aliases
* `$ alias`

## macOS M1
* Make sure you have tmux installed via arm64 homebrew

`uname -a` shows if you have arm64 or intel

Which tmux am I running? `file $(which tmux)`

* If you have arm you will get `/opt/homebrew/bin/tmux: Mach-O 64-bit executable arm64`
  - you install ARM homebrew in the `/opt/homebrew` path

## What is your default shell?  `$ finger $USER`

## where is the alacritty config? (TODO: put on github)
* Where is nvim?
* Where are dotfiles?
* TODO put alacritty and nvim on Github
* Consolidate Alacritty, dotfiles and nvim in one repo (dotfiles)

* after all was said and done and I finally separated arm and 
## Resources
<a href="https://github.com/lovell/sharp/issues/2460" target="_blank">Can't compile under Apple Silicon M1 arm64</a>

gatsby develop wasn't working with sharp
sharp not installing
brewARM upgrade
brewARM doctor
followed instructions to remove problems
zfrash
followed issue in resources for this:
$ brewARM info vips (missing dependencies)
$ brewARM reinstall vips (this took a few minutes to install)
$ brewARM info vips (now all the dependencies are there)
gatsby develop still didn't work
rm -rf node_modules/sharp
gatsby clean
rm -rf node_modules package.json
npm i --legacy-peer-deps
gatsby develop
