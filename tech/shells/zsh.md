# The ZSH shell
ZSH, also called the Z shell, is an extended version of the Bourne Shell (sh), with some new features, and support for plugins and themes. Since it is based on the same shell as Bash, ZSH has many of the same features, and switching over is a relatively simple.

Here's my sale's pitch to switch to ZSH. This is what the plain Terminal looks like:

![IMG Terminal](https://i.imgur.com/OTyA3zw.png)

And this is what your Zsh can look like:

![IMG Zsh](https://i.imgur.com/IiHCOfe.png)

## Too Long; Didn't Read - TL;DR
* If you want to switch to ZSH and get your terminal looking sexy and have a walk through of setting up everything you need to start just watch this <a href="http://commandlinepoweruser.com/" target="_blank">Wes Bos Command Line Tutorial video</a>
* <a href="https://github.com/hmml/awesome-zsh" target="_blank">List of ZSH features</a>

### Some Pros of using ZSH 
  - Automatic cd (just type the name of the directory)
  - Recursive path expansion (example: "/u/lo/b" expands to "/usr/local/bin")
  - Spelling correction and approximate completion - If you make a minor typing mistake typing a directory, ZSH will fix it for you automatically
  - case insensative tab completion (example: `$ cd document` or `$ cd Document` both work with tab
  - The terminal `history` is based on what you have already typed in prompt
      + This means if you type `c` and hit up arrow, will only show you `commands with c`
  - Works better than `man page`
      + Example: If you type `$ ls -` + `<tab>` you will see all the possible `flags`
          * Flags are a way to set options and pass in arguments to the commands you run. Commands you run will change their behavior based on what flags are set. You should read the documentation (aka `man pages`) of each command to know what flags are available
          * Example: running `$ ls` with the `-l` flag (`$ ls -l`) will include more information in the result and change the format of what is returned for that command
      
## ZSH Keyboard commands
| key binding            | action                                            | notes |
|------------------------|---------------------------------------------------|-------|
| `$ <ctrl> + u`         | clears line                                       |       |
| `$ take [FOLDER_NAME]` | create new folder and change into it at same time |       |
| `$ cd - `              | go to previous directory                          |       |
| `<cmd>` + `click`      | links inside terminal                             |       |
| `<ctrl>` + `r`         | search through terminal history                   |       |
| `<cmd>` + `r`          | clear screen but maintain history                 |       |

### Command Line Control
* If you want to navigate around the Terminal use these commands

| key binding | action                            | notes                |
|-------------|-----------------------------------|----------------------|
| `<Ctrl-p>`  | move to previous history          |                      |
| `<Ctrl-n>`  | move to next history              |                      |
| `<Ctrl-b>`  | move left on command line         | TODO: broken on mine |
| `<Ctrl-f>`  | move right on command line        | TODO: broken on mine |
| `<Ctrl-a>`  | move to beginning of command line |                      |
| `<Ctrl-e>`  | move to end of command line       |                      |
| `<Ctrl-d>`  | delete session                    | TODO: buggy          |

* more tips - https://opensourcehacker.com/2012/09/19/five-zsh-tricks-to-optimize-your-shell-workflow/

### vi command edition mode
* Alternatively, you could set up your shell to use vi command edition mode, by adding `set -o vi` to your shell startup file (`.zshrc`)
* **note** I prefer this technique to the above commands as it enables me to just use my vim commands in the command line and I just hit `<ESC>` to enter command mode and I type my vim commands as I would do in the vim editor

### Install ZSH with homebrew (macOS) 
`$ brew install zsh`

* <a href="https://www.howtogeek.com/258518/how-to-use-zsh-or-another-shell-in-windows-10/" target="_blank">How to use ZSH (or another Shell) in Windows 10</a>

### Update ZSH 
* You will periodically be asked to update but you can update anytime with:

`$ omz update`

### Refresh ZSH
* Whenever you make changes to your `.zshrc` file you will not see those changes take effect until your `source` that file like this:

`$ source ~/.zshrc`

### If you can't find zsh
* You may get this error from time to time
* Just reinstall zsh and it should fix it

`$ brew reinstall zsh`

### Truncate the shell
1. Open `.zshrc`
2. Add this function

```
# more code
prompt_dir() {
    prompt_segment blue black "%-53<...<%~%<<"
}
```

3. Refresh your `.zshrc`

`$ source ~/.zshrc`

## Oh-My-Zsh
* Great people got together to make working with `zsh`` great.
*  <a href="https://github.com/robbyrussell/oh-my-zsh" target="_blank">Oh-My-Zsh Docs</a>
* <a href="https://www.youtube.com/watch?v=Tz4kScOIOW0" target="_blank">Video Installing Oh-My-Zsh</a>
* <a href="https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins-Overview
" target="_blank">Oh-My-Zsh Plugins Overview</a>
* You can also use `Oh-My-Zsh` which is the most popular plugin framework for ZSH, and it comes with many built-in plugins and themes as well. There are also a couple of other plugin frameworks, including Antigen, which is a full package manager for ZSH, but Oh-My-Zsh has loads of plugins built right in.

### Amazing Free Tutorial to install ZSH (and a lot of other stuff)
* There is an amazing free course to get you all set up with ZSH, iTerm2, oh-my-zsh, a great theme and a lot of other amazing things like `Z`, autosuggest, syntax highlighting. <a href="https://commandlinepoweruser.com/" target="_blank">Here is that video</a>

### Install Instructions
1. Install ZSH first

`$ brew install zsh`

2. Install Oh-My-Zsh

```
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

## ZSH-Z
* `ZSH-z` is a command line tool that allows you to jump quickly to directories that you have visited frequently in the past, or recently -- but most often a combination of the two (a concept known as "frecency"). It works by keeping track of when you go to directories and how much time you spend in them
* `Z` Works with a small DB so the more the use it the more it **learns**
* [link to z](https://github.com/rupa/z)

### Install Z
* [watch video of installing z.sh](https://www.youtube.com/watch?v=qbNn5zJLZU0)

1. Download `z.sh` file to your $HOME

`$ wget https://raw.githubusercontent.com/rupa/z/master/z.sh -O ~/z.sh`

2. Copy the `raw` code and save to $HOME directory
3. Save as `z.sh`
4. Open `~/.zshrc` and add this after your alias'
    
    ```
    # include Z
    . ~/z.sh
    ```
* Or you can just write the include from the command line with: `$ echo . /path/to/z.sh >> ~/.bashrc`

## Powerline fonts
* Powerline is a great statusline plugin for Vim editor, which is developed in Python and provides statuslines and prompts for many other applications such as bash, zsh, tmux and many more. Add Power to Linux Terminal with Powerline Tool
* Add powerline fonts
[fonts](https://github.com/powerline/fonts/blob/master/Inconsolata/Inconsolata%20for%20Powerline.otf)

## How to see hidden files on macOS
* When working with zsh you will <a href="http://ianlunn.co.uk/articles/quickly-showhide-hidden-files-mac-os-x-mavericks/" target="_blank">want to see hidden files on macOs</a> hidden files
  - Or just type this in the terminal:
  
```
$ defaults write com.apple.finder AppleShowAllFiles YES
```

1. Press `<CR>`
2. Relaunch finder (_hover over finder icon on dashboard and hold down option key, this will let you relaunch finder - You can also just choose from dropdown)
3. Now when you open up a directory with hidden files you will see hidden files like `.zshrc` and `.oh-my-zsh`

## Choose a theme for Oh-My-Zsh
* There are <a href="https://wiki.github.com/robbyrussell/oh-my-zsh/themes" target="_blank">lots of themes to choose from</a>
* Wes Bos using the <a href="https://github.com/wesbos/Cobalt2-iterm" target="_blank">Cobalt theme</a>

### What is ~/.zshrc for when it comes to Oh-My-Zsh themes?
* This is your profile config file for `zsh`. The `bash` shell has the `.bash_profile` file. `zsh` has the `.zshrc` file.
* It is located in the user directory (`~/.zshrc`)
* Open that file in your text editor and change the `ZSH_THEME`.

```
ZSH_THEME="agnoster"
```
* <a href="https://github.com/kingluddite/dotfiles/blob/master/zshrc" target="_blank">Here is a link to my current .zshrc file</a>

## Add Plugins to ZSH
### ZSH Syntax Highlighting Plugin
* This package provides syntax highlighting for the shell zsh. It enables highlighting of commands whilst they are typed at a zsh prompt into an interactive terminal. This helps in reviewing commands before running them, particularly in catching syntax errors
* <a href="https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md" target="_blank">ZSH Syntax Highlighting Docs</a>

#### Install ZSH Syntax Highlighting Plugin
1. Clone the repo to your Oh-My-Zsh install on your local machine

`$ git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting`

2. Add to your plugin list inside `.zshrc`

`.zshrc`

```
// MORE CODE

plugins=( [plugins...] zsh-syntax-highlighting)`

// MORE CODE
```

3. Refresh your `.zshrc` after making the following change

### Auto Suggest Plugin

#### Install Auto Suggest Plugin
1. Clone to your plugins folder for ZSH 

`$ git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions` 

* **note** The autosuggestions font may be hard to see after adding installing it if so adjust it accordingly inside the terminal you are using's configuration (iTerm or Alacritty)
* The font may be hard to see on autosuggest so go into iTerm2 (if you are using that terminal) and adjust it accordingly

2. Add to plugin list in `.zshrc`

```
// MORE CODE

plugins=(zsh-autosuggestions)`

// MORE CODE
```
3. Refresh your `.zshrc` after making the following change

* Screenshot below shows autosuggest in action
* When I type the <a href="https://www.computerhope.com/jargon/b/backquot.htm" target="_blank">backtick</a> it will type the rest of the autosuggest for me

![IMG - autosuggest working](https://i.imgur.com/o7JWDJi.png)

### Add alias-tips Plugin
* If you are using aliases and have a hard time remember your aliases this is the plugin for you, after you type the long version of a command, if you have an alias for that command it will let you know what it is
* <a href="https://github.com/djui/alias-tips" target="_blank">Here are the docs for alias-tips</a> 

#### Installing alias-tips pluign 
1. Go to your custom plugins folder with: 

`$ cd ${ZSH_CUSTOM1:-$ZSH/custom}/plugins`

2. Clone the alias-tips folder to your ZSH plugins folder:

`$ git clone https://github.com/djui/alias-tips.git`

3. Open your .zshrc and append `alias-tips` to the existing plugins:

```
// MORE CODE

plugins=(... alias-tips)
 
// MORE CODE
```

4. `$ source .zshrc` (to refresh your changes)

## ag
* A code searching tool similar to ack, with a focus on speed
* <a href="https://github.com/ggreer/the_silver_searcher" target="_blank">the_silver_searcher</a>
* TODO: Compare `Ripgrep` vs `Ag` vs `fzf` vs `grep`
* `Z` is great when you’re moving to a specific directory, but what if you want to find a certain file or line of code? That’s where the silver searcher comes in. The silver search, aka ag, is great. It is an improvement over the many tools there are for searching on the command line. The biggest thing is that it is SUPER FAST. There are a lot of technical things in does in the background to get that speed, but the thing you should know is that it is fast.
* You can easily search your entire codebase for a certain function call, or for a file you can’t remember where it was, anything you want. To put it in perspective, I just searched the entire WordPress codebase for wp_insert_post(), and it returned all the results in less than 1/10 of a second. And this is on a four year old machine. Pretty good.

### Install `ag`
`$ brew install the_silver_searcher`

## Where are my Zsh themes located?

Open up that theme by going to your themes folder

```bash
$ cd ~/.oh-my-zsh/themes/
```

## Troubleshooting

### Theme Issues
* <a href="https://github.com/robbyrussell/oh-my-zsh/issues/4182" target="_blank">Issues with Oh-My-Zsh Themes</a>

### WordPress Wordmove Problems after installing Oh-My-Zsh 
* Wordmove broke after installing `zsh` and changing the `~/.zshrc` config and alias
    - I received `ruby` errors saying I did not have permissions
    - I used `$ sudo gem install wordmove` and that would not let me install it because I didn't have a ruby 2.0.0 or greater. I did have it installed but it did not work. I tried modifying the `.zshrc` PATH config and that didn't work. I got GEM_PATH GEM_HOME errors says they weren't properly defined? I couldn't get brew installed on `vagrant ssh`. I tried to install the linux flavor of brew no luck

#### Wordmove Solution
* It was 2 hours of pain but I finally just uninstalled ruby and then reinstalled `rvm 2.2.2`
* I checked the version and then installed wordmove and all was well.

**VERY IMPORTANT TIP**: Don't install wordmove on osx. Install it on linux box. Following this tip will save you problems because the paths of wordmove are absolute paths based on the linux box.
* <a href="https://rvm.io/rvm/install" target="_blank">Installing rvm</a>

### Problems with ruby version
* The error: keeps kicking back to default install of ruby 1.9
**My Solution:** _(I'll walk you through how the error happened and how I fixed it)_

1. When I tried to use Wordmove

```
$ wordmove
```

2. `zsh` says `command not found`

![IMG command not found](https://i.imgur.com/hSVc130.png)

```
$ gem list
```

3. I use the above command and I see wordmove is a local install
4. I get these errors:

```
Ignoring executable-hooks-1.3.2 because its extensions are not built.
and
Ignoring gem-wrappers-1.2.7 because its extensions are not built.
```

5. I run these two lines to fix them:

```
gem pristine executable-hooks --version 1.3.2
gem pristine gem-wrappers --version 1.2.7
```

6. But it still doesn't find `wordmove` command
7. I try to install wordmove again

```
$ gem install wordmove
```

8. But get this error:

`wordmove requires Ruby versio ~> 2.0.`

9. I checked the ruby version

```
$ ruby --version
```

10. And I see I'm only using the default install of ruby 1.9.3p484
11. I then show my list of rvms with

```
$ rvm list
```

12. And see I have `ruby-2.2.1` and `ruby-2.2.2` installed
13. It Looks like `2.2.1` is current
14. I switch to `2.2.2` with

```
$ rvm use ruby-2.2.2
```

15. Success! it now understands `wordmove`

## Add Oh My ZSH to Vagrant
* Are you using Vagrant and VVV? If so, you can create your own `.zshrc` file inside your Vagrant box.

### Here's how you install your `zsh` shell inside your vagrant box.

```
# Add zsh shell.
$ sudo apt-get install zsh

$ wget --no-check-certificate https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh

$ sudo chsh -s /bin/zsh vagrant
zsh
```

* As a nice addition, make it so that your terminals don't look too similar on your different boxes
* You should visually be able to know that you are on your local computer or on a remote box. I also like to know, when I'm developing locally, when I am in vagrant ssh and when I'm not. If you use zsh on all your different server environments, you can visually know where you are at all times. This is huge for preventing unwanted mistakes from happening.

```
# Change the oh my zsh default theme.
sed -i 's/ZSH_THEME="robbyrussell"/ZSH_THEME="dieter"/g' ~/.zshrc
```

### Need Xcode agreement?
* <a href="https://www.studytonight.com/post/solved-mac-os-xcrun-error-invalid-active-developer-path-missing-xcrun" target="_blank">Are you have macOS Xcode agreement issues?</a>

### Switching between `bash` and `zsh`
* I like `ZSH` but I also like `BASH` as I've been using it so long and like the solarized and settings I set for it.
* To easily switch to bash from zsh (make zsh your defaut profile). You can have a `.bash_profile` and a `.zshrc` file with all your aliases then to switch to bash

```
exec bash -l
```

* That will log you in
* If you **don't** do that you will have to refresh your `.bash_profile` with the following terminal command:

```
$ source ~/.bash_profile
```

### Performance - Speed up ZSH
#### It might be your $PATH
* My terminal was slow and this sped it up

#### Super slow node npm commands
* Check if you have a lot of items in your PATH - This a common symptom of that scenario
* In your terminal, run:

`$ echo "$PATH"`

* If the output has more than 8 or 9 colons in it, or if there are big directories like the root directory / in there, then this very well may be the culprit.
* As a basis for comparison, my carefully crafted PATH on macOS is:

`/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin`

* And if I run `$ which npm`, the output is:

`/usr/local/bin/npm`

* This tells me that my npm is located early in my PATH, which is important for performance, as the PATH gets searched from left to right for the existence of npm within each directory.
* You can quickly try out my PATH from above without any permanent consequences by simply running:

```
OLDPATH="$PATH"
PATH='/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin'
```

* Now try running the commands that were previously fast and slow and see if there is any difference
* If you start seeing "command not found" errors, try incrementally adding things back to your PATH or simply run:

`$ PATH="$OLDPATH"`

* Otherwise, if performance remains the same, then it is probably not your PATH. But if the situation improved, read on to make it permanent.
* Take the `PATH` that works best for you and put it in your shell's startup file. This will typically be located at `~/.bashrc` or `~/.bash_profile`. (I have my dotfiles and have my `zshrc` at `/dotfiles/zshrc`) 
* Try to find the startup file that already has a `PATH=...` line, comment out the existing line (be sure to add an explanatory comment) and then insert a similar line with the better value
* **note** I used this solution an it really made my use of `npm` and the terminal faster

## Resources
* <a href="http://getantibody.github.io/" target="_blank">Anitbody</a>
* <a href="https://carlosbecker.com/posts/speeding-up-zsh/" target="_blank">Speeding Up ZSH</a>
* <a href="http://blog.askesis.pl/post/2017/04/how-to-debug-zsh-startup-time.html" target="_blank">Debug ZSH</a> 
* <a href="https://stackoverflow.com/questions/35104992/is-it-possible-to-see-a-log-or-history-of-previous-iterm2-sessions" target="_blank">See Log of Previous iTerm2 Sessions</a> 
* <a href="https://superuser.com/questions/444614/how-to-check-what-slows-down-my-terminal-startup" target="_blank">Check to see what is slowing down my Terminal</a> 
* <a href="https://www.devroom.io/2011/11/08/fixing-a-slow-starting-terminal-or-iterm2-on-mac-os-x/" target="_blank">Fix Slow Terminal</a> 
* <a href="https://superuser.com/questions/512859/iterm-terminal-os-x-slow-in-opening-a-shell" target="_blank">Slow Opening Terminal Fix</a> 
* <a href="https://github.com/caarlos0/dotfiles" target="_blank">Dotfiles</a> 
