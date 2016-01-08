postcss-nth-list
=========

A work in progress postcss module for picking items from a 'varible list'.


## Installation

```shell
  npm install postcss-nth-list --save
```
## Usage
Requires [postcss-custom-properties], [postcss-css-variables] or similar to be required before this module.
```js
postcss([
    require('postcss-custom-properties'),
    require('postcss-nth-list')
])
```
See [PostCSS] docs for examples for your environment.

## Input example
```css
:root{
    --aVar: lime;
    --myList: "a-string" var(--aVar) 100,234,190 red;

    --string: nth(var(--myList), 0);
    --var: nth(var(--myList), 1);
    --rgb: nth(var(--myList), 2);
    --color: nth(var(--myList), 3);
}

body{
    background: nth(var(--myList), 3);
    color: rgb( var(--rgb) );
    border-color: var(--var);
    content: var(--string);
}

```

## Output example
```css
body{
    background: red;
    color: rgb( 100,234,190 );
    border-color: lime;
    content: "a-string";
}
```
[postcss-css-variables]:     https://github.com/MadLittleMods/postcss-css-variables
[postcss-custom-properties]: https://github.com/postcss/postcss-custom-properties
[PostCSS]:                   https://github.com/postcss/postcss
