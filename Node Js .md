# Node JS
  - Javascript on the server
  - Uses Async programming (eliminates waiting and continues with next queue)
  - Runs single threaded , non-blocking, asynchronous programming which is memory efficient
  - just like import in JAVA we need to use " require('<module name>') " here.
  - while creating own module use export to make those propeties/methods available outside module file
  
  ```
  exports.myDateTime = function () {
  return Date();
};
  ```
  outside the file
  
  ```
  var temp = require('filename');
  temp.myDateTime();
  ```
- XHR request - XMLHttpRequest objects are used to interact with web server without having to do full page refresh , this is mostly used in Ajax.
- Execute funtion only on some event are callback funtions, the first parameter in any callback function is error object.
- Callbacks add nesting and complexity to ease this we have async and promise from ES6 in Javascript
- Promise is proxy for a value which will eventuallly becomes available
- Async functions use promises behind the scenes, Promise() initially starts in pending state and resolved will go to then() and rejected will go to catch()
  Async functions are combination of promises and generators
  
