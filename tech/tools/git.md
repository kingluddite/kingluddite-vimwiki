# Git

eval $(ssh-agent)
ssh-add ~/.ssh/id_rsa_work
* i have to ssh-add each time for a directory
`$ ssh -T git@github.com-work`

## can't log in with password
Message "Support for password authentication was removed. Please use a personal access token instead."

* So go to settings > developer settings > generate new token (i did classic for now as the other is in beta)
* Save the token and use that to log in, if you forget it, and don't save it you'll need to keep generating new one's. i didn't add an expiration date but it is recommended
* now you should be able to clone the repo

## Multiple SSH keys

### lots of issues with this
* my config seems to default to mypersonalgit even with
in `~/.ssh/config

```
Host *
  AddKeysToAgent yes
  IdentityFile ~/.ssh/id_ed25519

# work github account: work 
Host github.com-work
    HostName github.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/id_rsa_work
```

* I think it is that wildcard that just makes it for everything
* but if I comment it out and then run this

```
# Default github account: kingluddite
# Host *
#   AddKeysToAgent yes
#   IdentityFile ~/.ssh/id_ed25519
```

* and run `$ eval $(ssh-agent)` followed by

 `$ ssh -T git@github.com-work` i get my log in 

* so if i do this to my config TODO!!!

## Which github user are you logged into?
ssh -T git@github.com (for personal)
ssh -T git@github.com-work (for work)
if you get a welcome all is good and you can add commit and push pull

one ssh is very straighforward and the github link is all you need

https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

Generate Second SSH Key

ssh-keygen -t rsa -f ".ssh/id_rsa_work" -C "example@work.tech"

Register New Key with SSH Agent
Next, add the SSH key to the SSH agent. The SSH agent manages your SSH key and remembers your passphrase, so you don’t have to reenter it each you use your SSH key. First, ensure the SSH agent is running using the eval command, then use the ssh-add command and specify the file name created in the previous step (~/.ssh/id_rsa_work).

eval $(ssh-agent)
ssh-add ~/.ssh/id_rsa_work

Add SSH Key to Second GitHub Account

https://jeffbrown.tech/multiple-github-accounts-ssh/
https://stackoverflow.com/questions/3225862/multiple-github-accounts-ssh-config

Create an SSH Config File
With both sets of SSH keys created and added to different GitHub accounts, how does Git know when the correct credentials? The answer is an SSH config file. The SSH config file sets configuration rules that specify when to use each account. You set the credentials based on the domain name.

touch ~/.ssh/config

Create profiles that specify when to use each identity or SSH key in the config file. The profiles should include:

Host: The host name from the Git URL used to clone the repo.
HostName: The real host name used to log in to. Since this tutorial uses GitHub, the host name here will be GitHub.com.
User: User ID, which will be git.
IdentityFile: Path to the SSH public key file to use for authentication.

but if you need multiple github users on your local computer there's a few more steps involved

this link helps - https://stackoverflow.com/questions/3225862/multiple-github-accounts-ssh-config

your work profile won't work without adding it using

ssh-add ~/.ssh/work_rsa

~/.ssh/config (this is a file)
Default github account: personal
Host *
  AddKeysToAgent yes
  IdentityFile ~/.ssh/id_ed25519

# 2u work github account: work
Host github.com-work
    HostName github.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/id_rsa_work

### don't forget this part when cloning repos!!!
The real fun beings when cloning repositories. Using the example config file above, you use the same repository URL if you are cloning a repository from your work GitHub. 

git@github.com:mypersonal/example.git

However, to clone a repository using the personal profile from the config file, you need to change the hostname in the clone URL to match the hostname in the config file. 

git@github.com-work:mywork/other-repo-example.git

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

### I want to use git checkout -- . but a file is not removed
* Try:

`$ git clean -fd`

Use of Git Clean command is as follows: 
```
$ git clean -n: to dry run.
$ git clean -f: forcefully file deletion.
$ git clean -f -x: delete .gitignore files
$ git clean -f -d: delete the untracked directories.
```

* [resource](https://www.geeksforgeeks.org/git-clean/#:~:text=The%20Git%20Clean%20command%20is,is%20very%20helpful%20to%20them.)
### If you accidentilly tracked `node_modules`
* You should never see `node_modules` in your git history, if you do this is how you fix it

`$ git rm -r --cached node_modules`

* But that doesn't remove `node_modules` from Git history. <a href="https://stackoverflow.com/questions/10067848/remove-folder-and-its-contents-from-git-githubs-history" target="_blank">This solution does just that</a>

## How do I discard unstaged changes in Git?
* **note** `git restore` was introduced in 2019
* You can now discard unstaged changes in one tracked file with:

`$ git restore <file>`

* And in all tracked files in the current directory (recursively) with:

`$ git restore .`

* If you run the latter from the root of the repository, it will discard unstaged changes in all tracked files in the project
* git restore was introduced in July 2019 and released in version 2.23 as part of a split of the git checkout command into git restore for files and git switch for branches
* git checkout still behaves as it used to
* As with `$ git checkout -- .`, this only discards changes in tracked files - But if you want to discard all unstaged changes, including untracked files, you could run, an additional `$ git clean -df`
