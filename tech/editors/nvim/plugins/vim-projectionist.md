# vim-projectionist
Projectionist provides granular project configuration using "projections"

[docs](https://vimawesome.com/plugin/vim-projectionist)

## Install 
* Place this in your `.vimrc`
* Then run the following in Vim 
  
  ```
  :source %
  :PlugInstall
  ```
  
## Example JSON configuration
`.projections.json`

```
{
  "src/main.js": { "type": "main" },
  "src/data/models/*/model.js": { "type": "model" },
  "src/data/models/*/adapter.js": { "type": "adapter" },
  "src/data/models/*/serializer.js": { "type": "serializer" }
}
```

![IMG - here is the app structure](https://i.imgur.com/R1CTfe5.png)

## Navigation Command variations 
* Navigation commands allow you to open files by thinking about their naming semantics, rather than thinking about their location. This is super helpful in a codebase with a lot of files with similar names that fall into different categories
* Remember to use `<Tab>` key to fill out your navigation quickly
* When using tab completion you can use the `<Ctrl-d>` to reveal a list of possible completions so you would type `:Emodel <Ctrl-d>`

| key binding | action                                         |
|-------------|------------------------------------------------|
| `:Etype`    | Opens the specified type in the current window |
| `:Stype`    | Opens the specified type in a horizontal split |
| `:Vtype`    | Opens the specified type in a vertical split   |
| `:Ttype`    | Opens the specified type in a new tabpage      |


