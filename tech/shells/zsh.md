# The ZSH shell
ZSH, also called the Z shell, is an extended version of the Bourne Shell (sh), with some new features, and support for plugins and themes. Since it is based on the same shell as Bash, ZSH has many of the same features, and switching over is a relatively simple.

Here's my sale's pitch to switch to ZSH. This is what the plain Terminal looks like:

![IMG Terminal](https://i.imgur.com/OTyA3zw.png)

And this is what your Zsh can look like:

![IMG Zsh](https://i.imgur.com/IiHCOfe.png)

## Too Long; Didn't Read (TL;DR)
* If you want to switch to ZSH and get your terminal looking sexy and have a walk through of setting up everything you need to start just watch this <a href="http://commandlinepoweruser.com/" target="_blank">Wes Bos Command Line Tutorial video</a>

## ZSH has many features
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
      
## Install ZSH with homebrew (macOS) 
`$ brew install zsh`

* <a href="https://www.howtogeek.com/258518/how-to-use-zsh-or-another-shell-in-windows-10/" target="_blank">How to use ZSH (or another Shell) in Windows 10</a>

* You can also use `Oh-My-Zsh` which is the most popular plugin framework for ZSH, and it comes with many built-in plugins and themes as well. There are also a couple of other plugin frameworks, including Antigen, which is a full package manager for ZSH, but Oh-My-Zsh has loads of plugins built right in.
* There is an amazing free course to get you all set up with ZSH, iTerm2, oh-my-zsh, a great theme and a lot of other amazing things like `Z`, autosuggest, syntax highlighting. <a href="https://commandlinepoweruser.com/" target="_blank">Here is that video</a>

## Update ZSH 
* You will periodically be asked to update but you can update anytime with:

`$ omz update`

## Refresh ZSH
* Whenever you make changes to your `.zshrc` file you will not see those changes take effect until your `source` that file like this:

`$ source ~/.zshrc`

## Speed up ZSH - It might be your $PATH
* My terminal was slow and this sped it up

### super slow node npm commands
* Check if you have a lot of items in your PATH - This a common symptom of that scenario
* In your terminal, run:

`$ echo "$PATH"`

* If the output has more than 8 or 9 colons in it, or if there are big directories like the root directory / in there, then this very well may be the culprit.
* As a basis for comparison, my carefully crafted PATH on macOS is:

`/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin`

And if I run `$ which npm`, the output is:

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
http://getantibody.github.io/
https://carlosbecker.com/posts/speeding-up-zsh/
http://blog.askesis.pl/post/2017/04/how-to-debug-zsh-startup-time.html
https://stackoverflow.com/questions/35104992/is-it-possible-to-see-a-log-or-history-of-previous-iterm2-sessions
https://superuser.com/questions/444614/how-to-check-what-slows-down-my-terminal-startup
https://www.devroom.io/2011/11/08/fixing-a-slow-starting-terminal-or-iterm2-on-mac-os-x/
https://superuser.com/questions/512859/iterm-terminal-os-x-slow-in-opening-a-shell
https://github.com/caarlos0/dotfiles

## Keyboard commands
| key binding            | action                                            | notes |
|------------------------|---------------------------------------------------|-------|
| `$ ctrl + u`           | clears line                                       |       |
| `$ take [FOLDER_NAME]` | create new folder and change into it at same time |       |
| `$ cd - `              | go to previous directory                          |       |

## Command Line Control
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

## If you can't find zsh
* You may get this error from time to time
* Just reinstall zsh and it should fix it

`$ brew reinstall zsh`

## Truncate the shell
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

## Install Z
# Download to latest to home dir
wget https://raw.githubusercontent.com/rupa/z/master/z.sh -O ~/z.sh

# Configure Z
* Add to `.zshrc`
`$ echo . /path/to/z.sh >> ~/.zshrc`

* If you were not using zsh you would just add this to your bash shell config file

`$ echo . /path/to/z.sh >> ~/.bashrc`

**recommended** [Wes Bos Command Line Video Tutorial ](https://www.youtube.com/watch?v=qbNn5zJLZU0&index=10&list=PLu8EoSxDXHP7tXPJp5ZmUpuT7sFvrswzf)
* Pros

Make directory and takes you inside it!

```
$ take
```

### Powerline fonts

* Add powerline fonts
[fonts](https://github.com/powerline/fonts/blob/master/Inconsolata/Inconsolata%20for%20Powerline.otf)



## Oh-my-zsh
* [Read more about oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)
* <a href="https://www.youtube.com/watch?v=Tz4kScOIOW0" target="_blank">Watch video on installing Oh-My-Zsh</a>

Great people got together to make working with zsh great.

Install ZSH first

`$ sudo apt-get install zsh`

### Install oh-my-zsh

```
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

### How to see hidden files on macOS
* When working with zsh you will <a href="http://ianlunn.co.uk/articles/quickly-showhide-hidden-files-mac-os-x-mavericks/" target="_blank">want to see hidden files on macOs</a> hidden files
  - Or just type this in the terminal:
  
```
$ defaults write com.apple.finder AppleShowAllFiles YES
```

1. Press return
2. Relaunch finder (_hover over finder icon on dashboard and hold down option key, this will let you relaunch finder - You can also just choose from dropdown)
3. Now when you open up a directory with hidden files you will see hidden files like `.zshrc` and `.oh-my-zsh`

### Choose a theme
* There are <a href="https://wiki.github.com/robbyrussell/oh-my-zsh/themes" target="_blank">lots of themes to choose from</a>
* Wes Bos using the <a href="https://github.com/wesbos/Cobalt2-iterm" target="_blank">Cobalt theme</a>

### ~/.zshrc
* This is your profile config file for `zsh`. The `bash` shell has the `.bash_profile` file. `zsh` has the `.zshrc` file.
* It is located in the user directory (`~/.zshrc`)
* Open that file in your text editor and change the `ZSH_THEME`.

```
ZSH_THEME="agnoster"
```
* <a href="https://github.com/kingluddite/dotfiles/blob/master/zshrc" target="_blank">Here is a link to my current .zshrc file</a>

### Add useful plugins to ZSH
* <a href="https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md" target="_blank">ZSH Syntax Highlighting</a>

#### Install ZSH Syntax Highlighting

`$ git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting`

#### Add to plugin list inside your `.zshrc`
`.zshrc`

* **note** Make sure to refresh your `.zshrc` after making the following change
```
// MORE CODE

plugins=( [plugins...] zsh-syntax-highlighting)`

// MORE CODE
```

#### Install Auto Suggest
`$ git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions` 

* **note** The autosuggestions font may be hard to see after adding installing it if so adjust it accordingly inside the terminal you are using's configuration (iTerm or Alacritty)
* The font may be hard to see on autosuggest so go into iTerm2 (if you are using that terminal) and adjust it accordingly

##### Add to plugin list in `.zshrc`
```
// MORE CODE

plugins=(zsh-autosuggestions)`

// MORE CODE
```
* **note** Make sure to refresh your `.zshrc` after making the following change

#### Add alias-tips
* If you are using aliases and have a hard time remember your aliases this is the plugin for you, after you type the long version of a command, if you have an alias for that command it will let you know what it is

##### Installing alias-tips using oh-my-zsh
* <a href="https://github.com/djui/alias-tips" target="_blank">Here are the docs for alias-tips</a> 
* Go to your custom plugins folder with: 

`$ cd ${ZSH_CUSTOM1:-$ZSH/custom}/plugins`

* Clone the alias-tips folder to your plugins folder:

`$ git clone https://github.com/djui/alias-tips.git`

* Open your .zshrc and append `alias-tips` to the existing plugins:

```
// MORE CODE

plugins=(... alias-tips)
 
// MORE CODE
```

* `$ source .zshrc` (to refresh your changes)

## Start HERE
## ag
Z is great when you’re moving to a specific directory, but what if you want to find a certain file or line of code? That’s where the silver searcher comes in. The silver search, aka ag, is great. It is an improvement over the many tools there are for searching on the command line. The biggest thing is that it is SUPER FAST. There are a lot of technical things in does in the background to get that speed, but the thing you should know is that it is fast.

You can easily search your entire codebase for a certain function call, or for a file you can’t remember where it was, anything you want. To put it in perspective, I just searched the entire WordPress codebase for wp_insert_post(), and it returned all the results in less than 1/10 of a second. And this is on a four year old machine. Pretty good.

To install `ag`, simply do `$ brew install the_silver_searcher`, and you’re all good to go.

## Install Z
* Tracks your most used directories, based on **frecency**
* [link to z](https://github.com/rupa/z)
  - install with:
    + Download `z.sh` file
    + Copy the `raw` code and save to $HOME directory
    + Save as `z.sh`
    + [watch video of installing z.sh](https://www.youtube.com/watch?v=qbNn5zJLZU0)
    + Open `~/.zshrc` and add this after your alias'
    
    ```
    # include Z
    . ~/z.sh
    ```

    + Works with a small DB so the more the use it the more it **learns**

## Start .zshrc in your `experiments` folder
`.zshrc`

```
# Start in experiments
cd ~/Documents/dev/experiments
```

### What is my Path?
If you ever need to find out the full path, just type `$ pwd`.

**What's my current theme in `zsh`?**

Open your `.zshrc` file

```bash
ZSH_THEME="cobalt2"
```

### Where are my Zsh themes located?

Open up that theme by going to your themes folder

```bash
$ cd ~/.oh-my-zsh/themes/
```

I'm using the `cobalt2` theme so I opened that theme up and commented out the existing code _(comments are made using #)_

## Keyboard shortcuts
Task | Keyboard shortcut
|--- | ---
| Clear line | `ctrl` + `u`
| Go back to previous directory | type dash `-`
| Autocomplete Folder/File (find stuff in folder and move between them) | press the `tab`
| links inside terminal | `cmd` + click
| search through history | `ctrl` + `r`
| clears screen but still has history | `cmd` + `r`

### Learn with Videos
[Wes Bos Intro](https://www.youtube.com/watch?v=IVgo5msaTlo)




###3 plugins overview
[link](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins-Overview)

## Troubleshooting

### You may run into problems with themes

[this link may help](https://github.com/robbyrussell/oh-my-zsh/issues/4182)

### Some problems after installing oh-my-zsh. 

Wordmove was was working great but after installing `zsh` and changing the `~/.zshrc` config and alias I could not get wordmove to work. I got ruby errors saying I did not have permissions. I then used `$ sudo gem install wordmove` and that would not let me install it because I didn't have a ruby 2.0.0 or greater. I did have it install but it did not work. I tried messing with the `.zshrc` PATH config and that didn't work. I got GEM_PATH GEM_HOME errors says they weren't properly defined? I couldn't get brew installed on `vagrant ssh`. I tried to install the linux flavor of brew no luck. It was 2 hours of pain but I finally just uninstall ruby and then reinstalled `rvm 2.2.2`. I checked the version and then installed wordmove and all was well.

**VERY IMPORTANT TIP**: don't install wordmove on osx. Install it on linux box. Following this tip will save you problems because the paths of wordmove are absolute paths based on the linux box.
[link for rvm install](https://rvm.io/rvm/install)

### Problems with ruby version
The error: keeps kicking back to default install of ruby 1.9
**My Solution:** _(I'll walk you through how the error happened and how I fixed it)_

When I tried to use Wordmove
```
$ wordmove
```

`zsh` says `command not found`
![command not found](https://i.imgur.com/hSVc130.png)

```
$ gem list
```

I use the abovi and I see wordmove is a local install

I get these errors:

```
Ignoring executable-hooks-1.3.2 because its extensions are not built.
and
Ignoring gem-wrappers-1.2.7 because its extensions are not built.
```

I run these two lines to fix them:

```
gem pristine executable-hooks --version 1.3.2
gem pristine gem-wrappers --version 1.2.7
```

But it still doesn't find `wordmove` command

I try to install wordmove again

```
$ gem install wordmove
```

But get this error:

`wordmove requires Ruby versio ~> 2.0.`

I type: 
```
$ ruby --version
```

And I see I'm only using the default install of ruby 1.9.3p484

I then show my list of rvms with

```
$ rvm list
```

And see I have `ruby-2.2.1` and `ruby-2.2.2` installed

Looks like `2.2.1` is current

I switch to `2.2.2` with

```
$ rvm use ruby-2.2.2
```

Success! it now understands `wordmove`

Whew!

## Add Oh My ZSH to Vagrant

Are you using Vagrant and VVV? If so, you can create your own `.zshrc` file inside your Vagrant box.

Here's how you install your `zsh` shell inside your vagrant box.

```
# Add zsh shell.
$ sudo apt-get install zsh

$ wget --no-check-certificate https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh

$ sudo chsh -s /bin/zsh vagrant
zsh
```

As n nice addition, make it so that your terminals don't look too similar on your different boxes.

You should visually be able to know that you are on your local computer or on a remote box. I also like to know, when I'm developing locally, when I am in vagrant ssh and when I'm not. If you use zsh on all your different server environments, you can visually know where you are at all times. This is huge for preventing unwanted mistakes from happening.

```
# Change the oh my zsh default theme.
sed -i 's/ZSH_THEME="robbyrussell"/ZSH_THEME="dieter"/g' ~/.zshrc
```

### Need Xcode aggreement?

To bring up xcode aggreement:

```
$ sudo xcrun css
```

## Switching between `bash` and `zsh`

I like `ZSH` but I also like `BASH` as I've been using it so long and like the solarized and settings I set for it.

To easily switch to bash from zsh (make zsh your defaut profile). You can have a `.bash_profile` and a `.zshrc` file with all your aliases then to switch to bash

```
exec bash -l
```

That will log you in. If you **don't** do that you will have to refresh your `.bash_profile` with the following terminal command:

```
$ source ~/.bash_profile
```

