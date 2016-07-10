# webpack

## Module Loader
* 自動壓縮需要的 js library
* 只有 `require` 的 js 會 load 所需要的 library，不會將 library 放在 global scope

### File Hierarchy
```
.
├── index.html
├── js
│   ├── module1.js
│   ├── module2.js
│   ├── scripts.js
│   └── scripts.min.js
├── package.json
└── webpack.config.js
```

### index.html
```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Some Page</title>
    </head>

    <body>
        <h1>My Webpack Page</h1>
        <script src="js/scripts.min.js"></script>
    </body>
</html>
```

### js/scripts.js
```javascript
require('./module1.js');
require('./module2.js');
```

### js/module1.js
```javascript
    var $ = require('jquery');
    $('h1').html("new text");
```

### js/module2.js
```javascript
    var _ = require('lodash');
    ......
```

### webpack.config.js
```javascript
var debug = process.env.NODE_ENV !== "production";
var webpack = require('webpack');

module.exports = {
    context: __dirname,
    devtool: debug ? "inline-sourcemap" : null,
    entry: "./js/scripts.js",
    output: {
        path: __dirname + "/js",
        filename: "scripts.min.js"
    },
    plugins: debug ? [] : [
        new webpack.optimize.DedupePlugin(),
        new webpack.optimize.OccurenceOrderPlugin(),
        new webpack.optimize.UglifyJsPlugin({ mangle: false, sourcemap: false }),
    ],
};
```

### How it work
1. `npm init`
2. `npm install -S webpack`
3. `npm install -S lodash jquery` (just for demo)
4. `webpack` (for dev)
5. `NODE_ENV=production webpack` (for production)


## webpack-dev-server
* 當 file 有異動會自動重新編譯並重新整理網頁
* 專門開發使用，請勿將之使用在 prodution

### Auto Refresh
1. http://localhost:8080/webpack-dev-server/index.html
2. ```webpack-dev-server --inline --hot```
