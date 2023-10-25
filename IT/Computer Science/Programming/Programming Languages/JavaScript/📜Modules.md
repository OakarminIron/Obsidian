JavaScript modules are a way of organizing and structuring JavaScript code by dividing it into separate files, each containing a specific set of functionalities. Modules help in encapsulating code, promoting reusability, and managing dependencies between different parts of an application.

In JavaScript, modules allow you to define private variables, functions, and classes that are not accessible from outside the module unless explicitly exported. Other parts of the application can then import and use the exported members.
```
// mathUtils.js
export function add(a, b) {
  return a + b;
}

export function subtract(a, b) {
  return a - b;
}

// app.js
import { add, subtract } from './mathUtils.js';

console.log(add(5, 3)); // Output: 8
console.log(subtract(5, 3)); // Output: 2

```

[[📜Modules and Environment]]
