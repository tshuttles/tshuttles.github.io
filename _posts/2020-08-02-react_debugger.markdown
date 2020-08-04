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
Now, Redux DevTools offers a variety of options to view state, actions and their behavior in your application. There will be two main windows inside of the inspector: the actions that are dispatched and the data. The actions (as defined by your action creators) are displayed in real time as you are navigating through your application. On each action that is displayed, there are two options, jump and skip. Jump will take your application to the state of the app at the time this action fired. Skip will cross out the action and show you your application without that action being used. 

In the other window of your inspector console contains very useful tabs: Action, State, Diff, Test. Clicking on the 'Action' tab will show the individual action type and any data it is carrying along to the reducers. The 'State' tab shows the entire state tree at the time of the action selected in the other section of the console. 'Diff' will show only what that individual action changed in the state tree. 'Test' will create a test format in some pre-provided testing frameworks; it takes your root state and provides a written test on what the end state should hold (this tab you may not use as often as the others). 

The top of the console offers two more sets of tabs. The right tab lets you flip between different instances of running apps on the page. The left set of tabs shows different modes: 
 - Inspector: the most used and is the default mode. Shows all the tools that have been discussed so far here.
 - Log Monitor shows complete state and actions, as opposed to the Inspector mode where it just shows the diffs. (Try using the slider while in this view and watch your state tree grow/shrink!)
 - Chart shows the state in a tree-like structure.

Lastly, we're left with the bottom toolbar, which has many tabs. These tabs provide more functionality for diving into your actions and state. It allows for time travel, dispatching actions, importing/exporting state, and remote control. Starting from the far left, the first three options are for creating a new console view ether to the left, right, or bottom.
 - Pause recording does not stop other actions from firing within your app, it is just stopping the recording of actions within the console. Unlike other abilities within the console it does not control the state of your running browser page.
 - Lock changes will actually freeze the running app’s other/future actions. So it takes Pause recording to the next level by locking any future state changes in your app.
 - Persist will keep the current state even when the page reloads
 - Dispatcher will ether show or hide the dispatching module. Which can be used to fire a custom action with custom data.
 - Slider will give you a smooth scroll through the actions. This will time travel through the actions that have fired and update the running app to show the current state and certain points in time. This comes packed with an auto-play, one step action arrows, and a speed interval play-through time.
 - Import and export are for importing/exporting state as JSON into the application. Which enables you to run your app off of custom state.
 - Remote creates a separate console, not connected to the browser console tools. This will run the same actions but “remotely” away from the dev-tools.


All of the tools at your disposal within the Redux DevTools (in the Chrome browser) will making your life so much easier while developing your application. Goodluck with your future projects and don't give up! 