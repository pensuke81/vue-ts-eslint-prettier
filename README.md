# vue-ts-eslint-prettier
This is my Vue + Typescript + ESLint + Prettier project settings.

## Project setup
```
vue create my-project

Vue CLI v3.9.1
? Please pick a preset: Manually select features
? Check the features needed for your project: Babel, TS, Router, Vuex, Linter
? Use class-style component syntax? No
? Use Babel alongside TypeScript (required for modern mode, auto-detected polyfills, transpiling JSX)? Yes
? Use history mode for router? (Requires proper server setup for index fallback in production) Yes
? Pick a linter / formatter config: Prettier
? Pick additional lint features: (Press <space> to select, <a> to toggle all, <i> to invert selection)Lint on save
? Where do you prefer placing config for Babel, PostCSS, ESLint, etc.? In dedicated config files
? Save this as a preset for future projects? No
```

## Turn off all ESLint rules that are conflict with Prettier
```
yarn add -D eslint-plugin-prettier
```

add `plugin:prettier/recommended` in .esilntrc.js

```javascript
extends: ["plugin:vue/essential", "@vue/prettier", "@vue/typescript", "plugin:prettier/recommended"],
```

## editorconfig setting
Add new file `.editorconfig`

```
root = true

[*]
charset = utf-8
indent_style = space
indent_size = 2
end_of_line = lf
insert_final_newline = true
trim_trailing_whitespace = true
```

## prettier setting
Add new file `.prettierrc.js`

```
module.exports = {
  tabWidth: 2,
  singleQuote: true
};
```

## .vscode setting
Add `.vscode/settings.json` file.

```json
{
  "eslint.enable": true,
  "eslint.autoFixOnSave": true,
  "editor.formatOnSave": false,
  "eslint.validate": [
    "javascript",
    {"language": "typescript", "autoFix": true },
    {"language": "vue", "autoFix": true}
  ],
}
```

ESLint plugin is below.
[ESLint - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)

## Finally, execute lint fix.

```
yarn lint
```