The Window interface represents a window containing a DOM document; the document property points to the DOM document loaded in that window.
A window for a given document can be obtained using the document.defaultView property.
A global variable, window, representing the window in which the script is running, is exposed to JavaScript code.

Window.caches Read only
Returns the Cache Storage object associated with the current context. This object enables functionality such as storing assets for offline use, and generating custom responses to requests.

Window.clientInformation Read only
An alias for Window.navigator.

Window.closed Read only
This property indicates whether the current window is closed or not.

Window.console Read only
Returns a reference to the console object which provides access to the browser's debugging console.

Etc... 
```
window.alert("Hello DOM")
alert("Hello DOM")
```

```
var name = "Alice"
console.log(name)    // Alice
console.log(window.name)   // Alice
function add(a, b) {return a + b}
console.log(add(1, 2))   // 3
console.log(window.add(1, 2))  // 3

```

https://developer.mozilla.org/en-US/docs/Web/API/Window