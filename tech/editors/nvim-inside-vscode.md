# Nvim inside VS Code
## 
Date: Aug 13, 2021
[Resource](https://github.com/VSCodeVim/Vim/issues/3099)
Topic: Get jk key combo to enter command mode

`settings.json`

```
// MORE CODE

"vim.insertModeKeyBindings": [
        {
            "before": ["j", "k"],
            "after": ["<Esc>"]
        }
    ]
// MORE CODE
```


