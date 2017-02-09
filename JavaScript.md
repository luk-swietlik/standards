#JavaScript

![js-standard-code-style](http://d21ii91i3y6o6h.cloudfront.net/gallery_images/from_proof/2236/large/1413860642/javascript.png)


## Rules

* **Indentation:** 
  - 1 tab (4 spaces long) || 4 spaces || 2 spaces
  - turn on display of whitespace in the editor
  - set this indentation as default for the editor
  
  eslint: [`indent`](http://eslint.org/docs/rules/indent)
  
* **Strings**
  - use single quotes for strings
  
  eslint: [`quotes`](http://eslint.org/docs/rules/quotes)
  
  ```js
  document.getElementById('string');
  ```

* **Variables**
  - define variables at the beginning of scope
  - remove unused variables from code
  
  eslint: [`no-unused-vars`](http://eslint.org/docs/rules/no-unused-vars)
  
  - Avoid modifying `const` declarations

  eslint: [`no-const-assign`](http://eslint.org/docs/rules/no-const-assign)

  ```js
  const score = 100;
  score = 125;        // ✗ avoid
  ```
  
* **Spacing**
  - Avoid multiple spaces
  - Add a space after keywords
  
  eslint: [`keyword-spacing`](http://eslint.org/docs/rules/keyword-spacing)

  ```js
  if (condition)  // ✓ ok
  if(condition)   // ✗ avoid
  ```
  
  - Add a space before a function declaration's parentheses
  
  eslint: [`space-before-function-paren`](http://eslint.org/docs/rules/space-before-function-paren)

  ```js
  var bar = function () { // ✓ ok
  var bar = function() {  // ✗ avoid
  
  bar () // ✓ ok
  bar()  // ✗ avoid
  ```
  
  - [ or ]
  
  - No space between function identifiers and their invocations

  eslint: [`func-call-spacing`](http://eslint.org/docs/rules/func-call-spacing)

  ```js
  console.log ('hello'); // ✗ avoid
  console.log('hello');  // ✓ ok
  ```
  
  - Infix operators must be spaced
  
  eslint: [`space-infix-ops`](http://eslint.org/docs/rules/space-infix-ops)

  ```js
  var x = 2 + 5  // ✓ ok
  var x=2+5      // ✗ avoid
  ```
  
  - Commas should have a space after them
  
  eslint: [`comma-spacing`](http://eslint.org/docs/rules/comma-spacing)

  ```js
  var list = [1, 2, 3, 4] // ✓ ok
  var list = [1,2,3,4]    // ✗ avoid
  function (p1, p2)  // ✓ ok
  function (p1,p2)   // ✗ avoid
  ```
  
  - add space between colon and value in key value pairs
  
    eslint: [`key-spacing`](http://eslint.org/docs/rules/key-spacing)

  ```js
  var obj = { 'key' : 'value' }    // ✗ avoid
  var obj = { 'key' :'value' }     // ✗ avoid
  var obj = { 'key':'value' }      // ✗ avoid
  var obj = { 'key': 'value' }     // ✓ ok
  ```

* **Commas & dots**

  - Trailing commas not allowed.

  eslint: [`comma-dangle`](http://eslint.org/docs/rules/comma-dangle)

  ```js
    var obj = {
      message: 'hello',   // ✗ avoid
    }
  ```
  
  - Commas must be placed at the end of the current line.

  eslint: [`comma-style`](http://eslint.org/docs/rules/comma-style)

  ```js
    var obj = {
      foo: 'foo'
      ,bar: 'bar'   // ✗ avoid
    }

    var obj = {
      foo: 'foo',
      bar: 'bar'   // ✓ ok
    }
  ```
 
  - avoid put comma after last array/object item
  
   ```js
    [1,2,3,]     // ✗ avoid
    { 'k': 1, }  // ✗ avoid
  ```
  
  -Dot should be on the same line as property

  eslint: [`dot-location`](http://eslint.org/docs/rules/dot-location)

  ```js
    console.
      log('hello')  // ✗ avoid

    console
      .log('hello') // ✓ ok
  ```

* **Curly braces**
  - Always use curly braces for statements and loops
  - Always start curly brace with the same line
  - Keep else statements on the same line as their curly braces
  
  eslint: [`curly`](http://eslint.org/docs/rules/curly)
  eslint: [`brace-style`](http://eslint.org/docs/rules/brace-style)

  ```js
  // ✓ ok
  if (condition) {
    // ...
  } else {
    // ...
  }
  ```

  ```js
  // ✗ avoid
  if (condition) 
  {
    // ...
  }
  else
    // ...
  ```
  
* **Blocks**
  - Allow or disallow single line blocks (?)
  - Add spaces inside single line blocks
  
  eslint: [`block-spacing`](http://eslint.org/docs/rules/block-spacing)

  ```js
    function foo () {return true}    // ✗ avoid
    function foo () { return true }  // ✓ ok
  ```
  
* **Comparison**
  - Always use `===` instead of `==`
  
  eslint: [`eqeqeq`](http://eslint.org/docs/rules/eqeqeq)

  ```js
  if (name === 'John')   // ✓ ok
  if (name == 'John')    // ✗ avoid
  ```
  
* **Globals**
  Always prefix browser globals with `window`
  Exceptions are: `document`, `console` and `navigator`.

  eslint: [`no-undef`](http://eslint.org/docs/rules/no-undef)

  ```js
  window.alert('abc')   // ✓ ok
  ```
  
* **Linebreaks**
  - Multiple blank lines not allowed

  eslint: [`no-multiple-empty-lines`](http://eslint.org/docs/rules/no-multiple-empty-lines)

  ```js
  // ✓ ok
  var value = 'hello world';
  value = 'world hello';
  ```

  ```js
  // ✗ avoid
  var value = 'hello world';
  
  
  value = 'world hello';
  ```
  
* **Ternary operator**
  - No ternary operators when simpler alternatives exist

  eslint: [`no-unneeded-ternary`](http://eslint.org/docs/rules/no-unneeded-ternary)

  ```js
  let score = val ? val : 0     // ✗ avoid
  let score = val || 0          // ✓ ok
  ```
  
* **Assignments** ??
  - Avoid or wrap conditional/return assignments ??
  eslint: [`no-cond-assign`](http://eslint.org/docs/rules/no-cond-assign)

 * **Naming**
   - use one variable declaration for initialized variables per scope
   
    ```js
  // ✗ ok
  var f = foo () {
    vsr a1,
        a2,
        a3;
  }
  ```

  - use camelcase when naming variables and functions.

  eslint: [`camelcase`](http://eslint.org/docs/rules/camelcase)

  ```js
    my_function () { }    // ✗ avoid
    myFunction () { }     // ✓ ok

    var my_var = 'hello'           // ✗ avoid
    var myVar = 'hello'            // ✓ ok
  ```
  
  - Constructor names must begin with a capital letter, const with uppercase, jQuery objects with &

* **Literals and constructors**
  
  - Usually use literals instead of constructors
    
  eslint: [`no-array-constructor`](http://eslint.org/docs/rules/no-array-constructor)

  ```js
  var nums = new Array(1, 2, 3)   // ✗ avoid
  var nums = [1, 2, 3]            // ✓ ok
  ```
  
* **callee & caller**
  - Avoid using `arguments.callee` and `arguments.caller`.**

  eslint: [`no-caller`](http://eslint.org/docs/rules/no-caller)

  ```js
  function foo (n) {
    if (n <= 0) {
      return;
    }
    arguments.callee(n - 1);   // ✗ avoid
  }

  function foo (n) {
    if (n <= 0) {
      return;
    }
    foo(n - 1);   // ✓ ok
  }
  ```
  
* **Debug & log**
  - No debug & log statements
  
  eslint: [`no-debugger`](http://eslint.org/docs/rules/no-debugger)

  ```js
    debugger;       // ✗ avoid
    console.log();  // ✗ avoid
  ```
  
* **No `delete` operator on variables.**

  eslint: [`no-delete-var`](http://eslint.org/docs/rules/no-delete-var)

  ```js
  var name
  delete name     // ✗ avoid
  ```
  
* **Duplicates**
  - avoid duplicate names, arguments, keys etc.
  
* **Eval**
  - Avoid using `eval()`

  eslint: [`no-eval`](http://eslint.org/docs/rules/no-eval)

  ```js
  eval( "var result = user." + propName ) // ✗ avoid
  ```
  
* **Native objects**
  - Usually avoid extending native objects

  eslint: [`no-extend-native`](http://eslint.org/docs/rules/no-extend-native)

  ```js
  Object.prototype.age = 21     // ✗ avoid
  ```
  
* **Parentheses**
  - Avoid unnecessary parentheses
  
* **Floating decimals**
  - watch out for floating-point numbers

* **Functions**
  - avoid Function Declaration, use Function Expression instead
  
  ```js
  var foo = function ()  // ✓ ok
  function foo ()        // ✗ avoid
  ```
  
* **Globals & shadowed**
  - avoid declaring global variables; declare only own namespace and then put everything inside of it
  - always use var, let, const
  - Restricted names should not be shadowed

  eslint: [`no-shadow-restricted-names`](http://eslint.org/docs/rules/no-shadow-restricted-names)

  ```js
  let undefined = 'value'     // ✗ avoid
  ```
  
 * **No unreachable code after `return`, `throw`, `continue`, `break`, `yield` statements.**

  eslint: [`no-unreachable`](http://eslint.org/docs/rules/no-unreachable)

  ```js
  function doSomething () {
    return true
    console.log('never called')     // ✗ avoid
  }
  ```

* **No flow control statements in `finally` blocks.**

  eslint: [`no-unsafe-finally`](http://eslint.org/docs/rules/no-unsafe-finally)

  ```js
  try {
    // ...
  } catch (e) {
    // ...
  } finally {
    return 42     // ✗ avoid
  }
  ```
  
* **No using `with` statements.**

  eslint: [`no-with`](http://eslint.org/docs/rules/no-with)

  ```js
  with (val) {...}    // ✗ avoid
  ```
  
* **write object properties in new lines**

* **Semicolon's must have a space after and no space before.**

  eslint: [`semi-spacing`](http://eslint.org/docs/rules/semi-spacing)

  ```js
  for (let i = 0 ;i < items.length ;i++) {...}    // ✗ avoid
  for (let i = 0; i < items.length; i++) {...}    // ✓ ok
  ```

* **Must have a space before blocks.**

  eslint: [`space-before-blocks`](http://eslint.org/docs/rules/space-before-blocks)

  ```js
  if (admin){...}     // ✗ avoid
  if (admin) {...}    // ✓ ok
  ```

* **No spaces inside parens.**

  eslint: [`space-in-parens`](http://eslint.org/docs/rules/space-in-parens)

  ```js
  getName( name )     // ✗ avoid
  getName(name)       // ✓ ok
  ```

* **Unary operators must have a space after.**

  eslint: [`space-unary-ops`](http://eslint.org/docs/rules/space-unary-ops)

  ```js
  typeof!admin        // ✗ avoid
  typof !admin        // ✓ ok
  ```

* **Use spaces inside comments.**

  eslint: [`spaced-comment`](http://eslint.org/docs/rules/spaced-comment)

  ```js
  //comment           // ✗ avoid
  // comment          // ✓ ok
  ```

* **No spacing in template strings.**

  eslint: [`template-curly-spacing`](http://eslint.org/docs/rules/template-curly-spacing)

  ```js
  const message = `Hello, ${ name }`    // ✗ avoid
  const message = `Hello, ${name}`      // ✓ ok
  ```

* **Use `isNaN()` when checking for `NaN`.**

  eslint: [`use-isnan`](http://eslint.org/docs/rules/use-isnan)

  ```js
  if (price === NaN) { }      // ✗ avoid
  if (isNaN(price)) { }       // ✓ ok
  ```
  
* **Always handle the error callback (eg. for ajax)**
  
* Never start a line with `(`, `[`, or `` ` ``. This is the only gotcha with omitting semicolons, and standard protects you from this potential issue.

  eslint: [`no-unexpected-multiline`](http://eslint.org/docs/rules/no-unexpected-multiline)

  ```js
  // ✓ ok
  ;(function () {
    window.alert('ok')
  }())

  // ✗ avoid
  (function () {
    window.alert('ok')
  }())
  ```

  ```js
  // ✓ ok
  ;[1, 2, 3].forEach(bar)

  // ✗ avoid
  [1, 2, 3].forEach(bar)
  ```

  ```js
  // ✓ ok
  ;`hello`.indexOf('o')

  // ✗ avoid
  `hello`.indexOf('o')
  ```

  Note: If you're often writing code like this, you may be trying to be too clever.

  Clever short-hands are discouraged, in favor of clear and readable expressions, whenever
  possible.

  Instead of this:

  ```js
  ;[1, 2, 3].forEach(bar)
  ```

  This is much preferred:

  ```js
  var nums = [1, 2, 3]
  nums.forEach(bar)
  ```
  
