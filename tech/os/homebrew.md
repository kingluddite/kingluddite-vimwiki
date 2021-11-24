## homebrew
### homebrew (m1) 
* Working with Homebrew on Macs was super simple but then along came the M1 which is super fast but it has issues with Homebrew. If you get the following error use the homebrew m1 solution below

## Mac vs Mac M1
* Since I have a M1 I have to versions of mac
* brewARM and brew87 so to use either you would type `$ brewARM install tree` or `$ brew87 install tree` (I added these as aliases)

```
alias brew87="arch -x86_64 /usr/local/bin/brew"
alias brewARM="/opt/homebrew/bin/brew"
```

* **IMPORTANT** so all the following `$ brew bla bla bla` examples I will use `brew` but you will need to substitute `brewArm` or `brew87` if you have

### Homebrew common error
![IMG homebrew m1 error](https://i.imgur.com/irqIk4a.png)

#### Homebrew M1 Solution
* You must preface your commands with `$ arch -arm64 brew ENTER Commands here`
* So to run `$ brew doctor` you type: `$ arch -arm64 brw doctor`

### Useful homebrew packages
* Checkout my [dotfiles](https://github.com/kingluddite/dotfiles/blob/master/Brewfile)
## To view info on a package
`$ brew info htop` (htop is an sample app)

## Homebrew Packages I use
* tree
* [Taskwarrior](./macos/homebrew/task.md)
* htop (task managers shows you all tasks that are running)
  * settings - use `?` and arrow keys
  * `S` is setup
  * use `$ brew info htop` to see dependencies and requirements and install them
