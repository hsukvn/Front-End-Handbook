# super in constructor

## Is it necessary to call `super()` inside constructor?
* 當需要自己重新 override default constructor 時就必須 call

```javascript
class MyClass extends React.component {
    constructor(){
        console.log(this) //Error: 'this' is not allowed before super()
    }
}
```

* 當沒有要 override constructor 時不需要 call

```javascript
class MyClass extends React.component {
    render(){
        return <div>Hello { this.props.world }</div>;
    }
}
```

## What is the difference between calling `super()` and `super(props)`?
* 當需要在 constructor 內使用 `this.props` 才需要使用 `super(props)`

```javascript
class MyClass extends React.component{
    constructor(props){
        super(props);
        console.log(this.props); // prints out whatever is inside props

    }
}
```

* 只有在其他地方使用則使用 `super()` 即可，react 會幫你自動把 `props` 帶進 `this`

```javascript
class MyClass extends React.component{
    render(){
        // There is no need to call `super(props)` or even having a constructor
        // this.props is automatically set for you by React
        // not just in render but another where else other than the constructor
        console.log(this.props);  // it works!
    }
}
```
