# Import and Export

```javascript
/**
 * This is how you import stuff.  In this case you're actually
 * importing two things:  React itself and just the "Component"
 * part from React.  Importing the "Component" part by itself makes it
 * so that you can do something like:
 *
 * class MyComponent extends Component ...
 *
 * instead of...
 *
 * class MyComponent extends React.Component
 *
 * Also note the comma below
 */
import react, {Component} from 'react';


/**
 * This is a "default" export.  That means when you import
 * this module you can do so without needing a specific module
 * name or brackets, e.g.
 *
 * import Header from './header';
 *
 * instead of...
 *
 * import { Header } from './header';
 */
export default class Header extends Component {

}

/**
 * This is a named export.  That means you must explicitly
 * import "Header" when importing this module, e.g.
 *
 * import { Header } from './header';
 *
 * instead of...
 *
 * import Header from './header';
 */
export const Header = React.createClass({

})

/**
 * This is another "default" export, only just with a
 * little more shorthand syntax.  It'd be functionally
 * equivalent to doing:
 *
 * const MyClass = React.createClass({ ... });
 * export default MyClass;
 */
export default React.createClass({

})
```
