# Git

## Git Configuration
* To configure your user name to be used by Git, type the following at the prompt (include the quotation marks):
* Let's assume the user name is `John Doe` with an email of `jdoe@doe.com`

`$ git config --global user.name "John Doe"`
`$ git config --global --list`

## How can you check what your current Git configuration is?
`$ git config --global --list`

* You should see if you configured Git properly this:

```
user.name=John Doe
user.email=jdoe@doe.com
```
## GitHub decided to rename the default `master` branch to `main`
* Here's how you can manually rename the `master` branch to `main`

## Git Productivity Tips
### Quickly create a `.gitignore`
* Add this function to your machine and if you want a Mac/Node .gitignore (change values for what app you are creating)

```
// MORE CODE

# Generate .gitignore
# `$ gi node,macos >> .gitignore`
function gi() { curl -sLw "\n" https://www.gitignore.io/api/\$@ ;}

// MORE CODE
```
* And I can call it with `$ gi node, macos >> .gitignore`

## Troubleshooting

### If you accidentilly tracked `node_modules`
* You should never see `node_modules` in your git history, if you do this is how you fix it

`$ git rm -r --cached node_modules`

* But that doesn't remove `node_modules` from Git history. <a href="https://stackoverflow.com/questions/10067848/remove-folder-and-its-contents-from-git-githubs-history" target="_blank">This solution does just that</a>

### How can I remove a file with sens
