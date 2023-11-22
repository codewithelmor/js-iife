# Immediately Invoked Function Expression

An **`IIFE`** is a design pattern in JavaScript where a function is defined and executed immediately after its creation. It is typically used to **`create a new scope for variables`** and to **`avoid polluting the global scope`**.

Here's a simple example:

```javascript
(function() {
  // code here
})();
```

This function is defined and immediately invoked. The primary benefits of using IIFE include:

1. **`Encapsulation`**: IIFE helps in encapsulating variables within the function, preventing them from polluting the global scope. This is important to avoid naming conflicts and unintended variable reassignments.

```javascript
(function() {
  var x = 10;
  // code here
})();

// x is not accessible here
```

2. **`Avoiding Global Scope Pollution`**: In JavaScript, variables declared without the **`var`**, **`let`**, or **`const`** keywords are automatically assigned to the global scope. IIFE helps in preventing unintentional global variable declarations.

```javascript
// Without IIFE
var x = 5;

// With IIFE
(function() {
  var x = 10;
  // code here
})();
```

3. **`Data Privacy`**: By encapsulating variables within the function, you can create a level of data privacy. The variables inside the IIFE are not accessible from the outside.

```javascript
var counter = (function() {
  var count = 0;

  return {
    increment: function() {
      count++;
    },
    getCount: function() {
      return count;
    }
  };
})();

counter.increment();
console.log(counter.getCount()); // Outputs 1
// count is not directly accessible
```

IIFE is a useful pattern in many scenarios, especially when you want to execute code immediately without leaving a lasting impact on the global scope or when you want to create a private scope for variables.
