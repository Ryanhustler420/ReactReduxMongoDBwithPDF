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
