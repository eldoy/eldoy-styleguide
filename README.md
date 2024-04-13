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

### CSS

We use SCSS for CSS using SASS variables. We don't use CSS variables.

- Avoid deep nesting
- Use `import` for splitting SCSS files
- Use VCSS as reset
