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

### CSS

We use SCSS for CSS using SASS variables. We don't use CSS variables.

- Avoid deep nesting
- Use `import` for splitting SCSS files
- Use VCSS as reset

### Javascript

We use vanilla Javacript, mainly ES5 with some ES6 features.

- Do not use semi-colon
- Use single quotes
- Do not use trailing comma
- Use `function() {}` instead of `() => {}`, except for built in JS array functions like `map` and `filter`
- Use `var` instead of `let` or `const`
- Use UPPERCASE for constants. These should never be reassigned.
- Use `function` instead of `class`
- Use `require` instead of `import`
- Use the full file name with extension with require for local files: `require('/lib/file.js')
- Use `for` instead of `forEach`
- Use short variable names
- Avoid single letter variable names except as counters in loops
- Use camelCase for longer variables and function names
- Use snake_case for variables from the database
- Comments should start with capital letters: `// Comment` not `// comment`

```js
// Deconstruct whenever possible
var { db } = app.config

// Add default variables to function parameters when possible
function(a = 1, b = 2) {}
```

If we need types we use JSDoc or just Markdown files with response examples.

#### SSR and Browser Javascript

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

#### Writing tests

We usually use `spekk` for testing if we are doing test driven development. Any APIs, converters or complicated structures should have a test suite.

```js
// Use 'result' for tester variable name if possible
var result = await matcher(value)
```

Write small test cases, prefer splitting into one file for each function. Move function up to libraries to lessen test burden.

Use `time` prefix for timestamp variables, like this: `timeInit`, `timeStart`, `timeEnd`

#### JS Utility libraries

Functionality that are often used will be candidates for inclusion into one of the following libaries:

- [Waveorb](https://github.com/eldoy/waveorb) - The Waveorb web development framework
- [furu](https://github.com/eldoy/furu) - The NodeJS web server library
- [extras](https://github.com/eldoy/extras) - NodeJS utility functions and regexps
- [HAKA](https://github.com/eldoy/haka) - DOM manipulation functions
- [d8a](https://github.com/eldoy/d8a) - Validation functions for data
- [dugg](https://github.com/eldoy/dugg) - NodeJS upload, download and image manipulation functions
- [Waveorb Validations](https://github.com/eldoy/waveorb-validations) - Validations to extend the built in `d8a` validations
- [Waveorb Util](https://github.com/eldoy/waveorb-util) - Front-end and isomorphic utility functions
- [Waveorb Client](https://github.com/eldoy/waveorb-client) - HTTP client for the browser and back-end scripts
- [Waveorb Components](https://github.com/eldoy/waveorb-components) - Web components for use in Waveorb applications
- [Waveorb Snippets](https://github.com/eldoy/waveorb-snippets) - Editor snippets for faster development
- [Waveorb Templates](https://github.com/eldoy/waveorb-templates) - Full application templates for `waveorb create`
- [Waveorb Form](https://github.com/eldoy/waveorb-form) - Form functions for generating forms
- [Waveorb Server](https://github.com/eldoy/waveorb-form) - Waveorb server installation script
- [Waveorb Mailer](https://github.com/eldoy/waveorb-mailer) - Send emails with Waveorb

... and a few more that are dependencies of the libraries above.

Always look for opportunities to push functionality up the stack. We want to save time.
