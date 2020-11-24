# Syntax and High Level Concepts of Javascript

## Types:
* Number
* String (number + string -> string | number - string -> number)
* Boolean (true | false)
* Undefined ( 'hi' - 'bye' )
* Null ( null )
* Symbol (Create a completely unique type, used usually for object properties)
```js
    var sym = Symbol()
    var sym2 = Symbol('new symbol')
```
* Object

## Variable Types
### var (always starts with a letter, $ or _ )
All instances of a given var are changed to the innermost assignment
if used, say in a function.  
```js
    var a = 5;
```
### let (ES6)
Different than var in that it creates a new scope whenever it is used say
inside a function, and the innermost assignment/modification does not 
affect the upper/outer let expression. Generally use let instead of var.
```js
    let a = 5;
```
### const
Cannot change the value of the variable once intitialized/declared. Always
best to use when making immutable variables.
If an object is a const, only the obj itself is immutable, the properties of the object are mutable unless specified otherwise.
```js
    const a = 5;
    const f = function() { do-something; }
```

## Functions
### Function Expression (Anonymous Function)
```js
    // Declaration 
    var a = function name() {}
    // Calling
    a();
```
### Function Declaration
```js
    // Declaration
    function name() {}
    // Calling
    name();
```
### Arrow Functions (ES6)
```js
    // Usually used when single return function is required
    () => ();
    const mul = (x, y) => x*y;
```
> ***Functions support closure and currying, similar to as seen in OCaml!***

## Data Structures
### Objects (Dictionary/ Property-Value Pairs)
These are somewhat like classes, with their properties and corresponding
values. Functions can be used as object values and are referred to as 
'methods'.
```js
    var obj1 = {
        ob_prop1: "Prop 1",
        ob_prop2: 2,
        ob_prop3: true,
        ob_prop4: ['p1', 'p2', 'px'],
        ob_prop5: function() { do-something }
    };

    // Accessing
    obj1.ob_prop1
    obj1.ob_prop3

    // Adding Properties
    obj1.new_prop = 'new-prop';

    // Dynamic properties
    const name = 'obj_prop1';
    const age = 'obj_prop2';
    const obj = {
        [name]: 'Jane Doe',
        [1+9]: 'prop2',
    };

    // When property === values
    const a = 'Jane Doe';
    const b = 'false';
    const c = {};
    const obj = { a, b, c};
```
### Arrays (Derivation of Object-> Properties: indices, Values: items)
```js
    var lst = ['item1', 'item2', 'item3', 'itemx'];

    // Shifts the array/left-most element is removed
    lst.shift()

    // Array acts like a stack, right-most element is removed
    lst.pop()

    // Array acts like a stack, element is appended to the end
    lst.push('new-item')

    // Join two arrays (no modificaton)
    lst0.concat(lst1)

    // Sort the array (no modificaton)
    lst.sort()

    // Get the length of the list
    lst.length()

    // Map in arrays (no need to return in single line, otherwise yes)
    const mapped = lst.map((num) => { return num-1 });

    // Filter the array (no need to return if single line)
    const filtered = lst.filter(num => num < 2 );

    // Reduce
    const reduced = lst.reduce((accumulator, num) => {
        return accumulator + num
    }, 0);
```

## Class
```js
    class ExampleClass {

        // Constructor Definiton
        constructor(field1, field2) {
            this.field1 = field1;
            this.field2 = field2;
        }

        // Class methods go below
    }

    // Extend a class
    class SmallExample extends ExampleClass {
        constructor(field1, field2) {
            super(field1, field2)
        }
    }
```

## Loops
### for
```js
    for (var i=0; i<n; i++) {
        do_something_multiple_times;
    }
```
### while 
```js
    while (counter < 10) {
        do_stuff;
        counter++
    }
```
### do-while 
```js
    do {
        do_now;
        counter++;
    } while (counter < n);
```
### forEach (ES5)
```js
    var lst = ['a', 'v', 'c', 'd'];
    lst.forEach(function(element, index) {
        do_with_element(element);
        do_with_index(index);
    })
```

## Control Flow
* if
```js  
    if (1 === 1) { do-expression } 
```
* else
```js
    if (1 === 0 ) { 
        do-expression1 
    } else { 
        do-expression1
    }
```
* else if
```js 
    if (1 === 0 ) { 
        do-expression1 
    } else if ('1' === '1') { 
        do-expression1
    }
    else {
        do-expression2
    }
```
* ternary operator
```js 
    return boolean ? doif_true : doif_false; 
```
* switch
```js 
    switch(expression) {
        case a:
            break;
        case c:
            break;
        default:
    }
```

## Comparisions:
* !== : Not Equals Comparator
* === : Is Equals Comparator
* <= | >= 
* \>
* <

## Casting
* String to Number
```js Number(str) ```

## Common Functions
### Alert (Display/Output through pop-up)
```js alert(alert_string)```
### Prompt (Input through pop-up)
```js prompt("Enter a number")```


Notes:
* ***Semi-colons:*** Not required generally, but good to add 
* ***Template Strings***
```js
const template = 'template'
`this is a ${template} string with ${default=5}'
```
