#JavaScript

![js-standard-code-style](http://d21ii91i3y6o6h.cloudfront.net/gallery_images/from_proof/2236/large/1413860642/javascript.png)

  ```diff
- TODO:
- prepare correct rules based on https://github.com/feross/standard/blob/master/RULES.md , http://standardjs.com/
```

## Code Standard Rules

* **Indentation** 
  - 1 indentation = 4 spaces [eslint: [`indent`](http://eslint.org/docs/rules/indent)]
  - Turn on display of whitespace in the editor
  - Set this indentation as default for the editor
  - Disallow all tabs [eslint: [`no-tabs`](http://eslint.org/docs/rules/no-tabs)]
  
* **Strings**
  - Use single quotes for strings [eslint: [`quotes`](http://eslint.org/docs/rules/quotes)]
  
  ```js
  document.getElementById('string');
  txt = 'lorem "quote" ipsum';
  ```

  - From ES6 allow backtick strings to avoid escaping single or double quotes
  - Disallow unnecessary escape usage [eslint: [`no-useless-escape`](http://eslint.org/docs/rules/no-useless-escape)]

* **Variables**
  - Define variables at the beginning of scope
  - Remove unused variables from code [eslint: [`no-unused-vars`](http://eslint.org/docs/rules/no-unused-vars)]
  - Avoid modifying `const` declarations [eslint: [`no-const-assign`](http://eslint.org/docs/rules/no-const-assign)]

  ```js
  const score = 100;
  score = 125;         // ✗ avoid
  ```

  - Disallow Early Use (especially important `let` & `const` to avoid 'temporal dead zone') [eslint: [`no-use-before-define`](http://eslint.org/docs/rules/no-use-before-define)]

  ```diff
  + ✓ ok
  ```
  ```js
  var a;
  a = 10;
  alert(a);

  {
      let c;
      c = 10;
      alert(c);
  }
  ```
  
  ```diff
  - ✗ avoid
  ```
  ```js
  alert(a);
  var a = 10;

  {
      alert(c);
      let c = 10;
  }
  ```

* **Naming**
   - Use one variable declaration for initialized variables per scope
   
  ```js
  // ✓ ok
  f = foo () {
    var a1,
        a2,
        a3;
  }
  ```
  ```js
  // ✗ avoid
  f = foo () {
    var a1;
    var a2;
    var a3;
  }
  ```

  - Use camelcase when naming variables and functions. [eslint: [`camelcase`](http://eslint.org/docs/rules/camelcase)]

  ```js
  myFunction () { }    // ✓ ok
  my_function () { }   // ✗ avoid

  var myVar = 'hello'    // ✓ ok
  var my_var = 'hello'   // ✗ avoid
  ```
  
  - Constructor names must begin with a capital letter, const with uppercase, jQuery objects with &

* **Spacing**
  - Avoid multiple spaces
  - Add a space after keywords [eslint: [`keyword-spacing`](http://eslint.org/docs/rules/keyword-spacing)]

  ```js
  if (condition)   // ✓ ok
  if(condition)    // ✗ avoid

  else {   // ✓ ok
  else{	   // ✗ avoid
  ```
  
  - Don't add a space before a function declaration's parentheses [eslint: [`space-before-function-paren`](http://eslint.org/docs/rules/space-before-function-paren)]

  ```js
  var bar = function() {    // ✓ ok
  var bar = function () {   // ✗ avoid
  ```
  
  - No space between function identifiers and their invocations [eslint: [`func-call-spacing`](http://eslint.org/docs/rules/func-call-spacing)]

  ```js
  console.log('hello');    // ✓ ok
  console.log ('hello');   // ✗ avoid
  ```
  
  - Disallow whitespace before properties [eslint: [`no-whitespace-before-property`](http://eslint.org/docs/rules/no-whitespace-before-property)]

  ```js
  foo[bar];   // ✓ ok
  foo.bar;    // ✓ ok
  foo [bar];   // ✗ avoid
  foo .bar;    // ✗ avoid
  ```

  - Infix operators must be spaced [eslint: [`space-infix-ops`](http://eslint.org/docs/rules/space-infix-ops)]

  ```js
  var x = 2 + 5;  // ✓ ok
  var x=2+5;      // ✗ avoid
  ```
  
  - Commas should have a space after them [eslint: [`comma-spacing`](http://eslint.org/docs/rules/comma-spacing)]

  ```js
  var list = [1, 2, 3, 4]   // ✓ ok
  var list = [1,2,3,4]      // ✗ avoid
  function (p1, p2)   // ✓ ok
  function (p1,p2)    // ✗ avoid
  ```
  
  - Add space between colon and value in key value pairs [eslint: [`key-spacing`](http://eslint.org/docs/rules/key-spacing)]

  ```js
  var obj = { 'key': 'value' }    // ✓ ok
  var obj = { 'key' : 'value' }   // ✗ avoid
  var obj = { 'key' :'value' }    // ✗ avoid
  var obj = { 'key':'value' }     // ✗ avoid
  ```

  - Semicolon's must have a space after and no space before [eslint: [`semi-spacing`](http://eslint.org/docs/rules/semi-spacing)]

  ```js
  for (let i = 0; i < items.length; i++) {...}   // ✓ ok
  for (let i = 0 ;i < items.length ;i++) {...}   // ✗ avoid
  ```

  - Must have a space before blocks [eslint: [`space-before-blocks`](http://eslint.org/docs/rules/space-before-blocks)]

  ```js
  if (admin) {...}    // ✓ ok
  if (admin){...}     // ✗ avoid
  ```

  - No spaces inside parens [eslint: [`space-in-parens`](http://eslint.org/docs/rules/space-in-parens)]

  ```js
  getName(name)       // ✓ ok
  getName( name )     // ✗ avoid
  ```

  - Unary operators must have a space after [eslint: [`space-unary-ops`](http://eslint.org/docs/rules/space-unary-ops)]

  ```js
  typof !admin        // ✓ ok
  typeof!admin        // ✗ avoid
  ```

  - Use at least one spaces inside comments (from the beginning and the end) [eslint: [`spaced-comment`](http://eslint.org/docs/rules/spaced-comment)]
  - Always use block comments

  ```js
  /* comment */   // ✓ ok
  /*comment*/     // ✗ avoid
  // comment      // ✗ avoid
  //comment       // ✗ avoid
  ```

  - No spacing in template strings [eslint: [`template-curly-spacing`](http://eslint.org/docs/rules/template-curly-spacing)]
  - Disallow template literal placeholder syntax in regular strings [eslint: [`no-template-curly-in-string`](http://eslint.org/docs/rules/no-template-curly-in-string)]

  ```js
  const message = `Hello, ${name}`     // ✓ ok
  const message = `Hello, ${ name }`   // ✗ avoid
  const message = 'Hello, ${name}'     // ✗ avoid
  ```

* **Commas & dots**

  - Trailing commas not allowed. [eslint: [`comma-dangle`](http://eslint.org/docs/rules/comma-dangle)]

  ```js
  obj = { 'k': 1 }   // ✓ ok
  obj = { 'k': 1, }  // ✗ avoid
  arr = [1,2,3]      // ✓ ok
  arr = [1,2,3,]     // ✗ avoid
  ```
  
  - Commas must be placed at the end of the current line. [eslint: [`comma-style`](http://eslint.org/docs/rules/comma-style)]

  ```js
    var obj = {
      foo: 'foo',
      bar: 'bar'   // ✓ ok
    }

    var obj = {
      foo: 'foo'
      ,bar: 'bar'   // ✗ avoid
    }
  ```
  
  -Dot should be on the same line as property [eslint: [`dot-location`](http://eslint.org/docs/rules/dot-location)]

  ```js
    console
      .log('hello') // ✓ ok

    console.
      log('hello')  // ✗ avoid
  ```

* **Curly braces**
  - Always use curly braces for statements and loops
  - Don't start curly brace from new line
  - Keep else statements on the same line as their curly braces
  
  [eslint: [`curly`](http://eslint.org/docs/rules/curly), [`brace-style`](http://eslint.org/docs/rules/brace-style)]

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
  
* **Blocks** (?)
  - Allow or disallow single line blocks (?)
  - Add spaces inside single line blocks [eslint: [`block-spacing`](http://eslint.org/docs/rules/block-spacing)]

  ```js
  function foo () { return true }  // ✓ ok
  function foo () {return true}    // ✗ avoid
  ```
  
* **Comparison**
  - Always use `===` instead of `==` [eslint: [`eqeqeq`](http://eslint.org/docs/rules/eqeqeq)]

  ```js
  if (name === 'John')   // ✓ ok
  if (name == 'John')    // ✗ avoid
  ```
  
* **Globals, nativs & shadowed**
  - Always prefix browser globals with `window`. Exceptions are: `document`, `console` and `navigator`. [eslint: [`no-undef`](http://eslint.org/docs/rules/no-undef)]

  ```js
  window.alert('abc')   // ✓ ok
  ```
  
  - Avoid declaring global variables; declare only own namespace and then put everything inside of it
  - Always use var, let, const
  - Disallow assignment to native objects or read-only global variables [eslint: [`no-global-assign`](http://eslint.org/docs/rules/no-global-assign)]
  - Restricted names should not be shadowed [eslint: [`no-shadow-restricted-names`](http://eslint.org/docs/rules/no-shadow-restricted-names)]

  ```js
  var undefined = 'value'   // ✗ avoid
  ```

* **Linebreaks**
  - Enforce placing object properties on separate lines [eslint: [`object-property-newline`](http://eslint.org/docs/rules/object-property-newline)]

  ```js
  // ✓ ok
  var obj = {
    foo: 'foo',
    bar: 'bar',
    baz: 'baz'
  };

  var obj = { foo: 'foo', bar: 'bar', baz: 'baz' };   // ✗ avoid
  ```

  - Multiple blank lines not allowed [eslint: [`no-multiple-empty-lines`](http://eslint.org/docs/rules/no-multiple-empty-lines)]

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

  - Never start a line with `(`, `[`, or `` ` ``. This is the only gotcha with omitting semicolons, and standard protects you from this potential issue. [eslint: [`no-unexpected-multiline`](http://eslint.org/docs/rules/no-unexpected-multiline)]

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
  ;[1, 2, 3].forEach(bar)   // ✓ ok
  [1, 2, 3].forEach(bar)    // ✗ avoid
  ```

  ```js
  ;`hello`.indexOf('o')   // ✓ ok
  `hello`.indexOf('o')    // ✗ avoid
  ```

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
  
* **Operators**
  - No ternary operators when simpler alternatives exist [eslint: [`no-unneeded-ternary`](http://eslint.org/docs/rules/no-unneeded-ternary)]

  ```js
  var score = val || 0        // ✓ ok
  var score = val ? val : 0   // ✗ avoid
  ```

  - Disallow mixes of different operators [eslint: [`no-mixed-operators`](http://eslint.org/docs/rules/no-mixed-operators)]

  ```js
  var foo = (a && b < 0) || c > 0 || d + 1 === 0;   // ✓ ok
  var foo = a && (b < 0 || c > 0 || d + 1 === 0);   // ✓ ok
  var foo = a && b < 0 || c > 0 || d + 1 === 0;     // ✗ avoid

  var foo = a + (b * c);   // ✓ ok
  var foo = (a + b) * c;   // ✓ ok
  var foo = a + b * c;     // ✗ avoid

  var foo = a || b || c;   // ✓ ok
  var foo = a && b && c;   // ✓ ok
  ```
  
* **Assignments**
  - Avoid conditional & `return` assignments [eslint: [`no-cond-assign`](http://eslint.org/docs/rules/no-cond-assign)]

  ```js
  if ((someVar = someNode) !== null)   // ✗ avoid
  ```

* **Literals and constructors**
  
  - Usually use literals instead of constructors [eslint: [`no-array-constructor`](http://eslint.org/docs/rules/no-array-constructor)]

  ```js
  var nums = [1, 2, 3]            // ✓ ok
  var nums = new Array(1, 2, 3)   // ✗ avoid
  ```
  
* **Callee & caller**
  - Avoid using `arguments.callee` and `arguments.caller` [eslint: [`no-caller`](http://eslint.org/docs/rules/no-caller)]

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
  - No debug & log statements [eslint: [`no-debugger`](http://eslint.org/docs/rules/no-debugger)]

  ```js
    debugger;        // ✗ avoid
    console.log();   // ✗ avoid
  ```
  
* **No `delete` operator on variables.** [eslint: [`no-delete-var`](http://eslint.org/docs/rules/no-delete-var)]

  ```js
  var name
  delete name   // ✗ avoid
  ```
  
* **Duplicates**
  - avoid duplicate names, arguments, keys etc.
  
* **Eval**
  - Avoid using `eval()`

  eslint: [`no-eval`](http://eslint.org/docs/rules/no-eval)

  ```js
  eval( 'var result = user.' + propName )   // ✗ avoid
  ```
  
* **Native objects**
  - Usually avoid extending native objects

  eslint: [`no-extend-native`](http://eslint.org/docs/rules/no-extend-native)

  ```js
  Object.prototype.age = 21   // ✗ avoid
  ```
  
* **Parentheses**
  - Avoid unnecessary parentheses
  
* **Numbers**
  - Watch out for floating-point numbers
  - Always use radix for `paresInt()`

  ```js
  parseInt('111', 10);
  ```

  - Use `isNaN()` when checking for `NaN` [eslint: [`use-isnan`](http://eslint.org/docs/rules/use-isnan)]

  ```js
  if (price === NaN) { }   // ✗ avoid
  if (isNaN(price)) { }    // ✓ ok
  ```

* **Functions**
  - Avoid Function Declaration, use Function Expression instead.
  
  ```js
  var foo = function ()   // ✓ ok
  function foo ()         // ✗ avoid
  ```

  - Disallow redundant `return` statements [eslint: [`no-useless-return`](http://eslint.org/docs/rules/no-useless-return)]
    A `return;` statement with nothing after it is redundant, and has no effect on the runtime behavior of a function. This can be confusing, so it's better to disallow these redundant statements.

 * **Unreachable code**
   - No unreachable code after `return`, `throw`, `continue`, `break`, `yield` statements [eslint: [`no-unreachable`](http://eslint.org/docs/rules/no-unreachable)]

  ```js
  function doSomething () {
    return true
    console.log('never called')   // ✗ avoid
  }
  ```

* **flow control**
  - No flow control statements in `finally` blocks [eslint: [`no-unsafe-finally`](http://eslint.org/docs/rules/no-unsafe-finally)]

  ```js
  try {
    // ...
  } catch (e) {
    // ...
  } finally {
    return 42   // ✗ avoid
  }
  ```
  
* **`with` statements**
  - No using `with` statements [eslint: [`no-with`](http://eslint.org/docs/rules/no-with)]

  ```js
  with (val) {...}   // ✗ avoid
  ```
  
* **Always handle the error callback (eg. for ajax)**
  
* **`typeof`**
  - Enforce comparing `typeof` expressions against valid strings ('undefined', 'object', 'boolean', 'number', 'string', 'function', 'symbol') [eslint: [`valid-typeof`](http://eslint.org/docs/rules/valid-typeof)]

  ```js
  typeof foo === 'undefined'   // ✓ ok
  typeof foo === typeof bar    // ✓ ok
  typeof foo == 'undefined'    // ✗ avoid
  typeof foo == 'someString'   // ✗ avoid
  ```

* Disallow renaming import, export, and destructured assignments to the same name [eslint: [`no-useless-rename`](http://eslint.org/docs/rules/no-useless-rename)]
* Enforce spacing between rest and spread operators and their expressions [eslint: [`rest-spread-spacing`](http://eslint.org/docs/rules/rest-spread-spacing)]
* Disallow unnecessary computed property keys on objects [eslint: [`no-useless-computed-key`](http://eslint.org/docs/rules/no-useless-computed-key)]
