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
