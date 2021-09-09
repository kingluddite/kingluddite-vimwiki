# Dotfiles
* I want to manage tmux, vim/nvim, alacritty all from one dotfile

## Think?
* Is there a better way then symlinks?

There is a better solution for managing dotfiles without using symlinks or any other tool, just a git repo initialized with --bare.

A bare repository is special in a way that they omit working directory, so you can create your repo anywhere and set the --work-tree=$HOME then you don't need to do any work to maintain it.

## Use git to save and commit dotfiles

```
$ config status
$ config add .vimrc
$ config commit -m "Add vimrc"
$ config add .bashrc
$ config commit -m "Add bashrc"
$ config push
```

## Resources
* <a href="https://www.atlassian.com/git/tutorials/dotfiles" target="_blank">The best way to store your dotfiles: A bare Git repository</a> (I used this and it shows you how to set up new computers with these dotfiles)
* <a href="https://github.com/kalkayan/dotfiles" target="_blank">dotfiles repo</a>
* <a href="https://stackoverflow.com/questions/46534290/symlink-dotfiles" target="_blank">symlink dotfiles</a>
* <a href="https://engineering.kalkayan.io/posts/setting-up-a-development-machine-part-3/" target="_blank">Dotfiles Management</a>
* <a href="https://news.ycombinator.com/item?id=27134249" target="_blank">A way to manage Dotfiles</a>
