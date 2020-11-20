# React Router

* React Router will help us navigate by creating a router dom

* You should update your index.js by adding the router.

```console
...
import {BrowserRouter as Router} from 'react-router-dom'; //Import the Router from react-router-dom
...
ReactDom.render(
  <React.StrictMode>
    <Router> // now your app will be under the Router
      <App />
    </Router>
  </React.StrictMode>,
  document.getElementById('root')
);
```
* Next we must add the following code to import the Router to the App we are using.

```console
...
import {Route, Link, Switch, Redirect} from 'react-router-dom'; // Import these router functions
...
class App extends React.Component { // not required, there are other methods
  constructor() {
    super()
    this.state = {
      str: 'Hello World'
    }
  }
  ...
}
```
