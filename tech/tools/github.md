# GitHub
* You are trying to push a HTTPS GitHub repo and you get permission denied error

```
Username for 'https://github.com': ENTER_GITHUB_USERNAME_HERE
Password for 'https://your_github_username@github.com':
remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.
remote: Please see https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/ for more informa
tion.
fatal: Authentication failed for 'https://github.com/YOURREPO.git'
```

## Solution
* You need to generate a token
* The fastest way to do this is to install the <a href="https://cli.github.com/" target="_blank">GitHub CLI</a>
* Once installed, use this:  

`$ gh auth login`

* Then you will be asked to enter your credentials to authenticate on GitHub
* (The following questions context is different because I am currently logged into my GitHub repo)

## Close issues with commit 
Tip - you can close issues on Github using this tip:

https://github.blog/2013-01-22-closing-issues-via-commit-messages/

Now when you enter ‚ÄúFixes #33‚Äù in a commit message, issue 33
will only be closed once the commit is merged into your
default branch (usually master).

Didn‚Äôt know about this feature? You can use any of these keywords to close an issue via commit message:

close, closes, closed, fixes, fixed

ref - https://github.blog/2013-01-22-closing-issues-via-commit-messages/ 

### Generate a token on GitHub
* Use this link:

Tip: you can generate a Personal Access Token here https://github.com/settings/tokens

* When creating you need to at least give the token these scopes: 
  - repo
  - read:org
  - admin:public_key

* Then generate the token
* Copy the token
* Paste in the spot when it asks you "Paste your authentication token"

```
? What account do you want to log into? GitHub.com
? You're already logged into github.com. Do you want to re-authenticate? Yes
? What is your preferred protocol for Git operations? SSH
? Upload your SSH public key to your GitHub account? /Users/philiphowley/.ssh/id_ed25519.pub
? How would you like to authenticate GitHub CLI? Paste an authentication token
Tip: you can generate a Personal Access Token here https://github.com/settings/tokens
The minimum required scopes are 'repo', 'read:org', 'admin:public_key'.
? Paste your authentication token: ****************************************
- gh config set -h github.com git_protocol ssh
✓ Configured git protocol
✓ Uploaded the SSH key to your GitHub account: /Users/YOUR-MACHINE-USERNAME/.ssh/id_ed25519.pub
✓ Logged in as YOUR_GITHUB_USERNAME
```

* Now you will be allowed to push your code to GitHub as you have successfully authenticated
