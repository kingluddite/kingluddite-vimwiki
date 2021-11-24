# Git

## Patch
* This is a great way to break up commits into logical chunks
You can use git add --patch <filename> (or -p for short), and git will begin to break down your file into what it thinks are sensible "hunks" (portions of the file). It will then prompt you with this question:

Stage this hunk [y,n,q,a,d,/,j,J,g,s,e,?]?

Here is a description of each option:

y stage this hunk for the next commit
n do not stage this hunk for the next commit
q quit; do not stage this hunk or any of the remaining hunks
a stage this hunk and all later hunks in the file
d do not stage this hunk or any of the later hunks in the file
g select a hunk to go to
/ search for a hunk matching the given regex
j leave this hunk undecided, see next undecided hunk
J leave this hunk undecided, see next hunk
k leave this hunk undecided, see previous undecided hunk
K leave this hunk undecided, see previous hunk
s split the current hunk into smaller hunks
e manually edit the current hunk
You can then edit the hunk manually by replacing +/- by # (thanks veksen)
? print hunk help
If the file is not in the repository yet, you can first do git add -N <filename>. Afterwards you can go on with git add -p <filename>.

Afterwards, you can use:

git diff --staged to check that you staged the correct changes
git reset -p to unstage mistakenly added hunks
git commit -v to view your commit while you edit the commit message.
Note this is far different than the git format-patch command, whose purpose is to parse commit data into a .patch files.

Resource for Interactive Staging - https://git-scm.com/book/en/v2/Git-Tools-Interactive-Staging 
This info came from  - https://stackoverflow.com/questions/1085162/commit-only-part-of-a-file-in-git

Tip - you can close issues on Github using this tip:

https://github.blog/2013-01-22-closing-issues-via-commit-messages/

Now when you enter “Fixes #33” in a commit message, issue 33
will only be closed once the commit is merged into your
default branch (usually master).

Didn’t know about this feature? You can use any of these keywords to close an issue via commit message:

close, closes, closed, fixes, fixed
## show branches
* like this as it stays on screen so I can know their names and delete or check into them easily

`$ git show-branch`

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

## How to leave a detailed git message
* To write a git commit, start by typing `$ git commit` on your Terminal or Command Prompt which brings up a Vim interface for entering the commit message

1. Type the subject of your commit on the first line
2. Write a detailed description of what happened in the committed change
3. Press Esc and then type :wq to save and exit

## Troubleshooting

### If you accidentilly tracked `node_modules`
* You should never see `node_modules` in your git history, if you do this is how you fix it

`$ git rm -r --cached node_modules`

* But that doesn't remove `node_modules` from Git history. <a href="https://stackoverflow.com/questions/10067848/remove-folder-and-its-contents-from-git-githubs-history" target="_blank">This solution does just that</a>

### How can I remove a file with sens
