## React Redux Code with MongoDB

# WHY REDUX

Understanding the **problem of state management** in React application

``meaning``

Since react is a component based framework. and passing data from one component
to another is kinda difficult task to perform. you can still use **this.state**
but for complex app you should manage state somewhere from there every component
will able to access state. as simple as that. :)


# WHAT REDUX IS ?

Redux is a state container where you can store your application state in an efficient
and convenient manner!

> React Redux application is made by five Elements

1.  Store     = create and maintain entire application state
2.  Provider  = help you to provide state to those component who want to access the store

```jsx
    <Provider store={store}>
      <App />
    </Provider>
```
3.  Actions   = help you to update state (the action go through Middleware if any)
4.  Reducers  = it will decide what to do with that action and fanally update the state of
                the application
5.  Middleware  (can be optional is certain scenarios)

in react you have smart component and dumb component you can also call it
CONTAINERS and PRESENTATIONAL COMPONENT

> smart COMPONENT

are those somehow access the application state

> dumb COMPONENT

are those who have no any relation with redux store in this compoent you cannot
get or set any state


# Set-up a small project

> Make a directory Called React-app || anything you like to name that folder

[Follow These Steps](#)

- ``mkdir reduxApp``
- ``cd reduxApp``
- ``npm init -y``
- ``atom .``


> Now install webpack

**if you never installed Webpack on your machine before than you firstly need to install Webpack
   globally by running the command**

> npm i webpack -g

**After Webpack is installed globally you can install in your project by running the command**

> npm i --save-dev webpack

> than you will install express using this command

- ``npm i --save express``

> than install some plugins

- ``npm i --save babel-core``
- ``npm i --save babel-loader``
- ``npm i --save babel-preset-es2015``
- ``npm i --save babel-preset-stage-1``
- ``npm i --save babel-preset-react``

> And finally you install redux

- ``npm i --save redux``

**Execute these cmd one by one respectvely**

- ``touch server.js``
- ``touch webpack.config.js``
- ``mkdir public``
- ``mkdir src``
- ``cd public``
- ``touch index.html``
- ``cd..``
- ``cd src``
- ``touch app.js``

> Hoff over to index.html

```html

<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <title>Hello Redux</title>
  </head>
  <body>
    <div id="app">
        
    </div>
      <script src="bundle.js"></script> 
      <h1>Hello Redux app</h1>
  </body>
</html>

```

> Hoff over to server.js file

```javaScript
"use strict"
var express = require('express');
var app = express();

var path = require('path');

// DEFINES A FOLDER FOR THE STATIC FILES 

app.use(express.static('public')); 

// DEFINES THE MAIN ENTRY POINT 

app.get('/', function(req, res){
        res.sendFile(path.resolve(__dirname, 'public', 'index.html'))
    }); 
    
app.listen(3000, function(){  
            console.log('App web-server listening on port 3000');
    });

```

> start node app by using this command

- ``node server.js``


> node configure webpack for that hoff over to :-

``webpack.config.js``

```javaScript

var path = require('path');
const webpack = require('webpack');
module.exports  = {  
    entry: './src/app.js',
    output: { 
            filename: 'bundle.js',
            path: path.resolve(__dirname, 'public')
        },
        watch: true,
        module:{
            loaders: [
                {
                    test:/\.js$/,
                    exclude:/node_modules/,
                    loader: 'babel-loader',
                    query: {
                        presets: ['react', 'es2015', 'stage-1']
                           }      
                 }
                    ]
               } 
            }

```

> final step is to move to app directory and fire this command

``webpack``
