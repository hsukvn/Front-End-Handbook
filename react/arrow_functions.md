# arrow functions

```javascript
var foo = function(a, b) {
return a + b;
}
var foo = (a,b) => {
return a + b;
}
```

```javascript
do.something(function(a,b) {
return a + b;
})

do.something((a,b) => {
return a + b;
})

do.something((a,b) => a + b)
```

```javascript
var module = {
    age: 30,
    foo: function() {
        console.log(this.age);
    }
    foo: function() {
        setTimeout(() => {
            console.log(this.age);
        }, 100); // arrow auto bind this
    }
}
```

```javascript
[0,1,2].map(val => val++); // [1,2,3]
```
