# Components

* Components are a big part of React as they allow us to plug in these components in multiple parts of the app. It helps to further divide the app for ease of management.

```console
import React from 'react' //we must import the React library
import {Link} from 'react-router-dom' // in this specific app we are using react-router-dom so we will use these links

import './Navbar.css' // Conventional structure should have the .css file in the same folder

const Navbar = (props) => { // name of component. Here we are expected to receive props from parent
  return (
    <div className="nav"> // using materialize
      <nav className="navbar navbar-light bg-light">
        <Link className="navbar-brand" to="/">FitSoul</Link> //We route using react-router Link 
        <form className="form-inline">
          <input className="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search" />
          <button className="btn btn-outline-secondary my-2 my-sm-0" type="submit">Search</button>
        </form>
        <Link to="/live" className="btn btn-danger">Go Live</Link>
        <Link to="/account" className="navbar-link">Account</Link>
        <Link to="" className="btn btn-outline-secondary my-2 my-sm-0" onClick={}>Login</Link>// regular functions such as onClick can be used
      </nav>
    </div>
  )
}
```

* This was a simple set up for navbar.
* We can now import the component anywhere in the app
