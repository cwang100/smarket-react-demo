# Smarket React Demo

This project was bootstrapped with [Create React App](https://github.com/facebookincubator/create-react-app).
## Install
To serve this locally, first install [NodeJs](https://github.com/nodejs/node) and NPM
then run `npm install` under root directory.
<br>
After install finishes, run `npm start` to start this project on `localhost:3000`
<br>
To deploy to the github page branch, simply run `npm run build` under the branch you want to build.
<br>
## Plugin
To view this website, you need to install this [Chrome plugin](https://chrome.google.com/webstore/detail/allow-control-allow-origi/nlfbmbojpeacfghkpbjhddihlkkiljbi) or equivalent plugin for other browsers.
<br>
The reason behind is that this website is trying to use data provided by a different domain.
To read more about this error, please read [this page](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS).
## What it uses
This app is powered by react + redux, and styling comes from a free [bootstrap template](https://bootstrapmade.com/demo/NiceAdmin/).
Everything you see in this page are react components. 
<br>
Redux is the state manager in this app. when an event is triggered, an action will be dispatched. Reducer will take the dispatched action and change the state of app.
<br>
I used async action provided by redux-thunk to handle ajax request and get data as json from smarket api. Those data are processed and saved into state in Reducers, and using the redux api, react components can get those updated state and use states to render tables and buttons you see in the page.
## How it is designed
The api provided contains three main datasets: Events+details, Contracts, and Contract groups. Each contract can belong to many contract groups, each contract group belongs to an event, and for each sports type, there are multiple events. The left toolbar contains all the event types, and the middle container contains all the events that belong to that type. By default, the middle container shows all the popular events, and after user select view detail, the middle container will change to display detailed information of current event. Below those details, it displays the contract informations that are extracted from the conrtact group of that event. Horse-racing contracts have more information than other contracts, and the contract table will auto resize and display all of them. 
## What each folder do
public: all the static resources are placed in this folder.
src: all the dynamic javaScript are placed in this folder. 
src/actions: where the redux actions are placed.
src/reducers: where the redux reducers are placed.
src/components: where all the react components are placed. The whole app is made with the combination of those components.
App.js: the main entrance of react. This file combines all the resources in different folder together.
Index.js, registerServiceWorker.js: auto generated file. react-gh-page deploy entrance.
App.test.js: placeholder for app tests. No test is currently implemented.
