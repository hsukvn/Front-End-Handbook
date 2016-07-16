# module


```javascript
module.exports.foo = function() {

}
```

```javascript
var myModule = require("myModule");
import myModule from "myModule";

export var foo = 3;

import { foo as foolish } from "myModule";

console.log(foolish);
```
