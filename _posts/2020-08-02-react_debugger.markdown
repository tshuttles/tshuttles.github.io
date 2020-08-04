---
layout: post
title:      "Using Redux DevTools"
date:       2020-08-02 01:24:10 -0400
permalink:  Redux_DevTools
---

# Redux DevTools
Bugs and errors while developing are inevitable. "Debugging" in layman's terms is a way of solving errors that occur while developing code. Redux DevTools is a very powerful tool that helps developers debug Redux applications easier than using any possible alternative methods. Most importantly, you can see exactly what data is in your application's store, which you will need a basic understanding before even installing this tool to use at your disposal. 

What is a store, you may ask? In simple terms, a store is the medium between your React application and your Redux root reducer. Reducers specify how the application's state changes in response to actions sent to the store. Remember, actions only describe what happened, but don't describe how the application's state changes. Different reducers can subscribe to different actions. The actions can be passed to reducers via the store. Anyways, we need to apply the store to our root “App” component using a functionality called “Provider” which is provided by the react-redux library. 

Don't forget, you must import these different libraries like "react-redux" and "redux" to make sure the functionality of Redux and its built in tools are usable in your React project in the first place, for example: 
```sh
import { createStore } from "redux";
import { Provider } from "react-redux";
```
These two imports typically go inside your 'index.js' file to create your store. 

Now after that brief introduction to Redux, in this article, we are going to learn how to install and use the Redux DevTools (Chrome browser only), which will make all your Redux dreams come true. The Redux DevTools are basically a console which you can set up in your development environment (Google Chrome) to visualize actions and state changes that take place in a redux application. Now, we will install the Redux DevTools.

## Installation 
Installation is fairly simple. Redux DevTools is integrated directly into your Chrome browser as a Chrome extension. Firstly, add the Redux DevTools extension in your extension tools inside the browser.  Once installed, you must install the Redux DevTools extension to our dev dependencies using the commands shown below: 
```sh
$ npm install — save-dev redux-devtools-extension
```
After installing the dependencies, you must import the compose functionality from Redux DevTools extension using:
```sh
import { composeWithDevTools } from ‘redux-devtools-extension’;
```
and we will create our store with the Redux DevTools add-on: 
```sh
const store = createStore(rootReducer, composeWithDevTools( ));
```
Now your index.js file should look like this: 
```
import React from "react";
import { render } from "react-dom";
import { Provider } from "react-redux";
import App from "./components/App";
import rootReducer from "./reducers";
import { createStore } from "redux";
import { composeWithDevTools } from "redux-devtools-extension";

const store = createStore(
  rootReducer,
  composeWithDevTools()
  // other store enhancers if any
);
render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById("root")
);
```

Now that your Redux store is installed and properly set up, it's time finally open up your Redux DevTools in the browser. 

## Using Redux DevTools
