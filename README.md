# babel-plugin-component-scss

[![NPM VERSION](https://img.shields.io/npm/v/babel-plugin-component.svg)](https://npmjs.org/package/babel-plugin-component-scss)

## Install

```shell
npm install babel-plugin-component-scss -D
or
yarn add babel-plugin-component-scss --dev
```

## Example

Converts

```javascript
import { Button } from 'element-ui'
```

to

```javascript
var button = require('element-ui/lib/button')
require('element-ui/packages/theme-chunk/button.scss')
```


## Usage

Via `.babelrc` or babel-loader.

```javascript
{
  "plugins": [["component-scss", options]]
}
```

## Multiple Module
```javascript
{
  "plugins": [xxx,
    ["component-scss", {
       "libraryName": "element-ui",
       "styleLibraryName": "theme-chalk/src",
       "ext":".scss"
     }]
  ]
}
```
