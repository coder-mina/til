@ This document is a summary of [re-introduction to JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript) without paraphrasing. @

# Summary

* JavaScript (JS) is notorious for being the world's most misunderstood programming language.

* JS has no concept of input or output. It is designed to run as a scripting language in a host environment.

* JS is prototype-based language that contains no class statement, as you'd find in C++ or Java. Instead, JS uses functions as classes.

* JS types

  * Number: Numbers in JS are "double-precision 64-bit format IEEE 754 values"

  * String

  * Boolean

  * `Object`

    * Function (it is special type of Object)

      * Rest parameter syntax (to accept undefined number of arguments) 

        * ```js
          function avg(...args) {}
          ```

      * anonymous function

      * `JS functions are themselves objects`

    * Array

    * ...

  * Symbol

  * null

  * undefined

* JS variables
  * New variables in JS are declared using one of three keywords. 
    * let: declare block-level variable. It is available from the `block` it is enclosed in.
    * const: declare variable whose values are nver intended to change. It is available from the `block` it is declared in.
    * var: Variable declared with var keyword is available from the `function` it is declared in.
  * `In JS, blocks do not have scope; only functions have a scope.` (but starting from ECMAScript 2015, let and const declarations allow creating block-scoped variables)

* JS Operators

  * == performs type coercion if you give it different types. ex) 123 == '123'; // true
  * === avoids type coercion. ex) 123 === '123'; // false

* JS Objects

  * JS objects can be thought of as simple collections of name-value pairs. `name` part is a JS string, and `value` can be any JS value.

  * ```
    // two ways to create an empty object
    var obj = new Object();
    var obj = {}; // object literal syntax
    ```

  * `new` creates a brand new empty object. 

  * Functions that are designed to be called by `new` are called constructor functions.

  * Say there is object named Person. Then Person.prototype is an object shared by all instances of Person.

  * ```js
    function Person(first, last) {
      this.first = first;
      this.last = last;
    }
    Person.prototype.fullName = function() {
      return this.first + ' ' + this.last;
    };
    Person.prototype.fullNameReversed = function() {
      return this.last + ', ' + this.first;
    };
    ```

  * 