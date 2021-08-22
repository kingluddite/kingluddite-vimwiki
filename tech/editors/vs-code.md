# VS Code

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

