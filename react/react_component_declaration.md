# React Component Declaration

## In ES5
```javascript
import React from 'react';

const Contacts = React.createClass({
  render() {
    return (
      <div></div>
    );
  }
});

export default Contacts;
```

## In ES6
```
import React from 'react';

class Contacts extends React.Component {
  constructor() {
    super();
  }
  render() {
    return (
      <div></div>
    );
  }
}

export default Contacts;
```
