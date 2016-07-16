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
        const { history } = this.props;
        console.log(history.isActive("archives")); // 看當前 archives 是否 active
        return (
            <div>
                <h1>haha</h1>
                {this.props.children}
                <Link to="archives" activeClassName="test">archives</Link> // Active 時加 class label
                <Link to="settings"><button class="btn btn-success">settings</button></Link>
                <Link to="settings" class="btn btn-danger">settings</Link>
                <button onClick={this.navigate.bind(this)}>featured</button>
            </div>
        );
    }
}
```

```javascript
export default class Archives extends React.Component {
    const { params } = this.props; /archives/hahaha
    const { article } = params; // hahaha
    const { query } = this.props.location; // ?date=55&filter=66
    const { date, filter } = query;

    render() {
        return (
            <div>
                <h1>Archives ({this.props.params.article})</h1>
                <h4>date: {date}</h4>
            </div>
        );
    }
}
```
