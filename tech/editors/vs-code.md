# VS Code

## Settings I like
* Toggle Mini Map as screen realestate is important
* `code .` (add to path)
* Add prettier extension
* add format on save
* Prettier: Single Quote (check)
* Change tab size to `2`
* Hide side bar (search for 'activity bar') and uncheck `Workbench > Activity Bar: Visible`
* code > keyboard shortcuts > format document (shift + option + F) (i just use autoformat on save)
* set default formatter to Prettier

## Theme ideas
* Theme Solarized light (too bright)

## Plugins
* [ES 7 React/Redux/GraphQL/React-Native snippets](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets)
## Issues
Date: Aug 12, 2021
Topic: Typescript not autoclosing braces
[Resource]():
Solution:

`settings.json`

```js
  "editor.autoClosingBrackets": "always",
  "[typescript]": {
    "editor.autoClosingBrackets": "always"
  },
```
***
Date: Aug 13, 2021
[Resource](https://code.visualstudio.com/docs/languages/typescript)
Topic: .tsx files not auto closing braces

`settings.json`

```js
  "[typescriptreact]": {
    "editor.autoClosingBrackets": "always"
  },
```
***

