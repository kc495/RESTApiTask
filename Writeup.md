Programming Frameworks and Languages Module - Reassessment Writeup
================================================================

 15th July 2022

Language
--------------
## Javascript
The server component was written in javascript.
Justification of javascript on the server side:
1.	Javascript supports asynchronous programming.
2.	JavaScript is a popular choice of server Language because it is often used as the language on clients. Developers are familiar with it.
## Language Features:
### Asynchronous Functions
In Asynchronous Function Multiple things can happen at the same time in an asynchronous model. Your programme continues to run after you start an action. When the action is completed, the software is notified and has access to the result (for example, the data read from Memory)

### Function Definitions (arrow function)
* Arrow Function: These factors are particularly useful for simplifying syntax and quelling code lines for a web page or web application. As they have a simple syntax, they would be used in anonymous functions in JavaScript.

```javascript
// attendees is an array of item objects -
 { id:<id>, name:<name>, notes:<notes>}
attendees = attendees.filter((i) => i.id != req.params.id)
```
### Lists
* Array Functions : An array is a data structure in JavaScript that has a list of components that each store a number of values in a single variable. The array methods are what give JavaScript arrays their strength. Array methods are built-in JavaScript functions that we can use on our arrays. The array functions are:
-sort()
- filter()
- push()
```javascript
attendees = [] 
// push
attendees.push({"id":1,'name':'demo-name','notes':'demo-notes'}) 
// filter
attendees = attendees.filter((i) => i.id !=req.params.id);
/// sort
if(Object.keys(req.body).sort().toString() != 'id,name,notes')
```

Server Framework
---------------------
## Express.js
The Framework used for the Server is Express.js The framework was found suitable for conducting the current coding as it can provide small and robust tooling options for the HTTP server. In all, it can be summarized that Express.js has the following features

## Framework Features:
### Routing
 Routing is made from the word route. It is used to determine the specific behavior of an application. It specifies how an application responds to a client request to a particular route, URI or path and a specific HTTP request method (GET, POST, etc.). It can handle different types of HTTP requests.

```javascript
// API to get attendees array
app.get('/attendees/', (req, res) => {
res.json(attendees);
})
```
###  Middleware
Middleware functions are the functions that access to the request and response object (req, res) in request-response cycle. By which when attendees provides information that information can be requested and responded accordingly.

```javascript
//The app.use() function is used to mount the specified middleware function(s) at the path which is being specified.
app.use(express.json());
var cors = require('cors')
app.use(cors())
```

### Single file prototyping
Prototypes make it simple to classify methods for all instances of a specific object. The method is applied to the prototype, so it is only stored once in memory, and yet every instance of the object has access to it.

Client Framework
----------------
## Vue.js
Vue.js framework is developed using JavaScript that is used to build and develop a user interface. The framework develops the interface on top of standard JavaScript and HTML formats and provides a declarative programming model. The framework include its ability for data binding that aids in assigning values or manipulating data of HTML attributes, assigning classes and changing style, 

## Framework Features:

### HTML Templating and Binding

* v-for: v-for is mostly used to render the items in a list, whereas it can also be used to iterate over an designated range. in the current application it has been used for the list of entrees.
```html
<li v-for="aa in attendees">
    <span>{{aa.id}}</span>
    <span>{{aa.name}}</span>
    <span>{{aa.notes}}</span>
</li>
```
* v-model:v-model develop two-way data bindings on form input, textarea, and select elements, use the v-model directive. Given the input type, it determines the best way to update the element. Here the v-model is used to determine the data which is entered in specified placeholders.
```html
<input name= "Name" placeholder= "Name" v-model= "attendee.name">
<input name= "Notes" placeholder= "Notes" v-model= "attendee.notes">
```
### Data and Methods
* Data: The data function, each instance retains an independent copy of the returned data object. To fetch and post data, most of vue.js makes use of API. It is secure as it has no impact on changes outside of its scope. so it is used in the application to secure the data.

```html
data() {
      return {
        attendee: {
            id: Math.random(),
            name: "",
            notes: "",
        },
        attendees: [],
      }
    }
```

* Methods: Methods in Vue.js are effective for integrating features to directives for tackling developments. Which can also used to define any simple piece of logic that we want to use methods.
```html
{
fetch(`${urlAPI}/attendees`, {
  method: 'GET',
})
    .then(response => response.json())
    .then(json => this.attendees = json)
   .catch(err => console.error(err))
}
```
### Devtools
Browser devtools extension for debugging Vue.js applications which allow debugg and troubleshoot more efficiently. As the Projects gets more data with bigger information then devtools extension will be widely used.

