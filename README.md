# babel-plugin-component-scss

[NPM version](https://npmjs.org/package/babel-plugin-component-scss)

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
  "plugins": [["component", options]]
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

### options

- `["component"]`: import js modularly
- `["component", { "libraryName": "component" }]`: module name
- `["component", { "styleLibraryName": "theme_package" }]`: style module name
- `["component", { "styleLibraryName": "~independent_theme_package" }]`: Import a independent theme package
- `["component", { "styleLibrary": {} }]`: Import a independent theme package with more config
  ```
  styleLibrary: {
    "name": "xxx", // same with styleLibraryName
    "base": true,  // if theme package has a base.css
    "path": "[module]/index.css",  // the style path. e.g. module Alert =>  alert/index.css
    "mixin": true  // if theme-package not found css file, then use [libraryName]'s css file
  }
  ```
- `["component", { "style": true }]`: import js and css from 'style.css'
- `["component", { "style": cssFilePath }]`: import style css from filePath
- `["component", { "libDir": "lib" }]`: lib directory
- `["component", { "root": "index" }]`: main file dir
- `["component", { "camel2Dash": false }]`: whether parse name to dash mode or not, default `true`
