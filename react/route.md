# Route

```javascript
import { Router, Route, IndexRoute, hashHistory } from "react-router";
import Bootstrap from "./vendor/bootstrap-without-jquery";
const app = document.getElementById('app');

ReactDOM.render(
  <Router history={hashHistory}>
    <Route path="/" component={Layout}>
      <IndexRoute component={Featured}></IndexRoute>
      <Route path="archives(/:article)" name="archives" component
      <Route path="settings" name="settings" component={Settings}
    </Route>
  </Router>,
app);
```

```javascript
import { Link } from "react-router";

export default class Layout extends React.Component {
    navigate() {
        this.props.history.pushState(null, "/"); //保留上一頁
        this.props.history.replaceState(null, "/"); //無法回上一頁
    }

    render() {
        return (
            <div>
                <h1>haha</h1>
                {this.props.children}
                <Link to="archives">archives</Link>
                <Link to="settings"><button class="btn btn-success">settings</button></Link>
                <Link to="settings" class="btn btn-danger">settings</Link>
                <button onClick={this.navigate.bind(this)}>featured</button>
            </div>
        );
    }
}
```
