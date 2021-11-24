# coc.nvim (Conquer of Completion)
## Problem with single quotes getting overwritten to doublequotes
* (note) I am autofixing my code on save
* My stylelint was changing single quotes in my css to doublequotes even though my prettier and eslint configs said single quotes, this was because I was missing this coc-settings.json

`coc-settings.json`

```
  "prettier.singleQuote": true,
```

## Stylelint with stylelintplus
* I want to have stylelint work with nvim
* You need coc-stylelint and you need coc-stylelintplus
* You add it to your `plugin-config/coc/coc-extensions.json` (you could just add it to your init.vim but I have my nvim more structured for better organized code that I can easily follow)
* You need to disable coc-css validation in `coc-settings.json`

### Config to autofix and format
`coc-settings.json`

* After adding the changes below you should see your stylelint formats and lints on save (you may have to tab a line and then save to kick this behavior into working)

```
// MORE CODE

  // coc-css
  "css.validate": false,
  "less.validate": false,
  "scss.validate": false,
  "wxss.validate": false,
  
  // stylelint
  "stylelintplus.autoFixOnFormat": true,
  "stylelintplus.autoFixOnSave": true,

// MORE CODE
```

### Resources
* <a href="https://github.com/bmatcuk/coc-stylelintplus" target="_blank">COC-stylelintplus</a>
