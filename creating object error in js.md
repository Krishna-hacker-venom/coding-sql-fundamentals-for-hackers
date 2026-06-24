# JavaScript Object Creation Error

You’re trying to mix a statement (`console.log`) inside an object literal, which isn’t valid JavaScript syntax.  
Objects can only contain **key-value pairs** (properties) or **methods** (functions).

---

## ❌ Incorrect Example

```js
// creating a js object
const user = {
    name : "krishna",
    age : 22,
    isdev : false,
    console.log("hello world!!"); // ❌ this is wrong
}
// Object
const user = {
  name: 'Alice',
  age: 25,
  func greet() { // ❌ do not use 'func'
    console.log(`Hi, I'm ${this.name}`);
  }
};

// Object
const user = {
  name: 'Alice',
  age: 25,
  greet() {
    console.log(`Hi, I'm ${this.name}`);
  }
};

// Calling the method
user.greet(); // Output: Hi, I'm Alice

