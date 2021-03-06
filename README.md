# redux-middleware
Experiments with React Redux Middleware, from Udemy Advanced React course

47 - Middleware Overview 3:26  

* Install ReduxSimpleStarter
* npm install --save react-router
* Redux with Middleware flowchart
* React -> Action Creator -> Action -> Middleware -> Reducers -> State -> React

48 - App Building Plan 3:50  

* Chart out app plan from Component diagram
* Ajax list of users, show a badge/card for each with name/company and email button
* Build app with dummy data -> Replace dummy data with ajax -> Middleware to fetch data


49 - Users Reducer 4:14  
* create new reducers/users.js file
* create new actions/types.js file for FETCH_USERS
* edit users.js with switch for action and state
* reducers/index.js import users.js

50 - Static Users Action Creator 2:15  

* purpose: retrun a default list of users (hardcoded)
* edit action/index.js
* add default user list

51 - Rendering a List of Users 7:32  

* new component - user_list.js
* edit user_list - this will be a redux container, import connect
* renderUser helper method, map over it in render
* import action creators and wire up as props
* in UserList import * as actions & use componentWillMount

52 - CSS Cleanup 4:20  

53 - Pains Without Middleware 7:15  

* install axios
* update actions/index.js
* check why screen goes blank (with debugger)
* needs promise

54 - Middleware Stack 4:43  
* removed debugger
* Chart of Middleware stack: action -> Middleware #1 (don't care, NEXT) -> Middleware #2 -> Middleware #3 -> Reducers
*

55 - Middleware Internals 7:55

* create middlewares dir.
* make src\middlewares\async.js
* edit src/index.js

56 - Handling Unrelated Actions 5:17  

* Diagram - Does action contain promise? if No, send to NEXT -> Reducers... if Yes, sit until resolved -> resolved, create new action and go through middleware again with full payload/

* edit async with if - for console log if we have a promise

57 - Handling Promises 8:05  

* Make sure the actions promise resolves
* if it resolves use dispatch to go through middleware stack again (but with promise.response, which will then skip the promise section)


58 - Middleware Review 6:50

* Output payload to console (5.58)
* Change action.payload in Users reducer to action.payload.data
