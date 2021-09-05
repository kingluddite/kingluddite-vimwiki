# Recurring Problems (and their solutions)
* You just upgrade your Mac OS and you whenever you `$ git clone` or `$ git pull` you get this unsightly error:

```
xcrun: error: invalid active developer path (/Library/Developer/CommandLineTools),
missing xcrun at: /Library/Developer/CommandLineTools/usr/bin/xcrun
```
* **Solution**
  * Install the Xcode toolkit
  * Even if you had it installed before, you might have to re-register it or update it to the latest version

`$ xcode-select --install`

* That might not work so you might need to reset it

`$ sudo xcode-select --reset`

