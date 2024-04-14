# Eldøy Projects Style Guide

Style guide for Eldøy Projects developers.

### Prettier settings

We use prettier for code formatting.

Add this to your editor config (VSCode):

```
"prettier.semi": false,
"prettier.singleQuote": true,
"prettier.trailingComma": "none"
```

To make prettier auto-formatting work with VSCode, include `/* HTML */`:

```js
function component() {
  return /* HTML */`
    <p>Hello</p>
  `
}
```

### Javascript

We use vanilla Javacript, mainly ES5 with some ES6 features.

- Do not use semi-colon
- Use single quotes
- Do not use trailing comma
- Use `function() {}` instead of `() => {}`
- Use `var` instead of `let` or `const`
- Use `function` instead of `class`
- Use `require` instead of `import`
- Use `for` instead of `forEach`
- Use short variable names
- Avoid single letter variable names except as counters in loops
- Use camelCase for longer variables and function names
- Use snake_case for variables from the database

```js
// Deconstruct whenever possible
var { db } = app.config

// Add default variables to function parameters when possible
function(a = 1, b = 2) {}
```

If we need types we use JSDOC.

##### SSR and Browser Javascript

We use [template strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) for HTML.

There are 5 kinds of functions for front-end Javascript:

1. Handle functions - handles events like submits and clicks
2. Render functions - either returns HTML or renders HTML
3. Load functions - fetch data or HTML from the server
4. Init functions - set up data and prepare
5. Util functions - helper functions that are not global

Here are some examples:

```js
// Handle function
function handleButtonClick(btn) {}

// Render function
function renderList() {
  return `<ul><li>Hello</li></ul>`
}

// Load function
function loadData() {}

// Init function
function initData() {}

// Util function
function utilFindProject() {}
```

### CSS

We use SCSS for CSS using SASS variables. We don't use CSS variables.

- Avoid deep nesting
- Use `import` for splitting SCSS files
- Use VCSS as reset
