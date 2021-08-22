# Troubleshooting Python and Homebrew
* This is an issue many might not have but it took me two days to solve so I am going to document steps I took to solve it (the order and notes are not great but at a high level I did all of the following and finally got rid of the annoying errors in nvim - the irony of ironies is this is all caused by python and I don't use python)

## How did the problem start?
* I upgraded homebrew and when i opened nvim I was greated with an error saying that host python could not be found
* I then used `:checkhealth` and saw that there were issues with finding Python 2  and Python 3
* It looks like there was a change on how to find python versions if you use `$ pyenv init` you'll get this:

```
# (The below instructions are intended for common
# shell setups. See the README for more guidance
# if they don't apply and/or don't work for you.)

# Add pyenv executable to PATH and
# enable shims by adding the following
# to ~/.profile and ~/.zprofile:

export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init --path)"

# Load pyenv into the shell by adding
# the following to ~/.zshrc:

eval "$(pyenv init -)"

# Make sure to restart your entire logon session
# for changes to profile files to take effect.
```

So I updated my `.zshrc` file with this info: 

![IMG warnings I was getting](https://i.imgur.com/Bpajvqa.png) 

* The order of my PATH needed to be altered with the main items coming first before the others
* Here are my changes to `.zshrc`

```
# Update 2021 - eval "$(pyenv init -)" no longer sets path
# Use below with --path instead
if command -v pyenv 1>/dev/null 2>&1; then
  eval "$(pyenv init --path)"
fi

export PYENV_ROOT="$HOME/.pyenv"
# export PATH="$PYENV_ROOT/bin:$PATH"
export PATH="$PYENV_ROOT/shims:$PATH"
export PATH="$PATH:/opt/homebrew/opt/openjdk/bin"
if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi
```

* I also had to reinstall fzf and zsh-autosuggestions.zsh with homebrew
* I finally got the python3 to pass by making sure I had pyenv correct version installed in the right place
* `$ brew info python` gave very useful info and showed me all the requirements that needed to be installed. If there was a red X I installed that using homebrew
* macos using python2 for the system and you can't alter that but you can use pyenv to install a different version and then select that version and you can use a command to see what the current version of python is running (it will have an asterisk beside it) - you will also have to install the latest version of pynvim `/usr/local/opt/python@3.9/libexec/bin` 
* It used to be called neovim but now it is called pynvim (this is important to know)
* I had to update `pip` and `pip3` and then I also uninstalled `python neovim` using `pip3` and installed `pip pynvim`
* I also had issues with the color in Alacritty so their is an alacritty file that is for configuration but the problem was the tmux file was conflicting - this worked fine in iterm - so I tried the changes people suggested to fix this but did not get it to work 100% TODO
* In my nvim `general/setting.vim` file I had to establish two variables like: 
  
```
let g:python_host_prog = '/usr/bin/python2'
let g:python3_host_prog = '/usr/local/bin/python3'
```

* Finally I had issues with undodir in vimwiki so I just deleted the folder. I still don't understand fully had undo works in vim TODO
