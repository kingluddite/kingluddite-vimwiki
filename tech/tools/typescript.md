# Typescript
## Typescript Environment Setup
`$ npm i -g typescript ts-node`

* If you don't want to install typescript globally on your computer and just install it locally for your project:

1. Install typescript as a dev dependency `$ npm i -D typescript`
2. Generate your TypeScript config file:

`$ ./node_modules/.bin/tsc --init`

## Check if the compiler is successfully installed
`tsc --help`

| binding     | action                          |
|-------------|---------------------------------|
| `<C-space>` | autocompletion                  |
| `[g`        | previous error (aka diagnostic) |
| `g]`        | next error (aka diagnostic)     |
| `gd`        | coc-definition                 |
| `gy`        | type definition                 |
| `gi`        | implementation                  |
| `gr`        | references                      |
 
* `gr` shows you all the places that variable/object is referenced
    * navigate up and down with `j` and `k`
    * Press `<CR>` to move to that instance
* `:!ts-node index.ts` - print out execution
* `<Shift-K>` - hover over function and it will show you function signature with documentation 
   * And will also work for 3rd party libraries you have 
* `<leader>rn` - rename instances,functions in buffer (not across files) 
* `<leader>f` - code formatting (I have format on save)
* `<leader>ac` - gives you a list of codeactions with numbers for you to choose from 
  * If you want to ignore an eslint rule, use this and choose which to ignore or show documentation!
* `<leader>qf` - will select the first code action (use this for missing imports)
* `if` - inside function (`cif` - will change in function)
* `af` - inside function (`caf` - will remove functions)
* `zc` - fold close
* `zo` - fold open
* `<space-a>` - shows you all diagnostic errors (navigate with `j` and `k` and `<CR>` to select)
* `<space-e>` - shows all coc extensions 
* `<space-c>` - shows all commands you can execute
* `<space-o>` - shows all symbols in current document (variable names and functions)
* `<space-s>` - fuzzy search symbols in your workspace
* Will give you autocompletion for JSDocs

## Resources
* <a href="https://thoughtbot.com/blog/modern-typescript-and-react-development-in-vim" target="_blank">Modern TypeScript and React Development in Vim (5 star!)</a>
* <a href="https://www.youtube.com/watch?v=ewORMuLm2z4" target="_blank">Setting up Neovim for TypeScript - Part 1</a>
