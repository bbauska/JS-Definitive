<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h1>JavaScript Definitive</h1>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This book covers the JavaScript language and the JavaScript APIs implemented by web browsers 
and by Node. I wrote it for readers with some prior programming experience who want to learn 
JavaScript and also for programmers who already use JavaScript but want to take their understanding 
to a new level and really master the language. My goal with this book is to document the JavaScript 
language comprehensively and definitively and to provide an in-depth introduction to the most 
important client-side and server-side APIs available to JavaScript programs. As a result, this is 
a long and detailed book. My hope, however, is that it will reward careful study and that the time 
you spend reading it will be easily recouped in the form of higher programming productivity.

<p>Previous editions of this book included a comprehensive reference section. I no longer feel that 
it makes sense to include that material in printed form when it is so quick and easy to find 
up-to-date reference material online. If you need to look up anything related to core or client-side 
JavaScript, I recommend you visit the MDN website. And for server-side Node APIs, I recommend you go 
directly to the source and consult the Node.js reference documentation.</p>

<h2 id="chx-1-x">Arithmetic in JavaScript</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<p>JavaScript programs work with numbers using the arithmetic operators. That the language provides. 
These include + for addition, - for subtraction, &ast; for multiplication, / for division, and % 
for modulo (remainder after division). ES2016 adds &ast;&ast; for exponentiation. Full details on 
these and other operators can be found in Chapter 4.</p>

<p>In addition to these basic arithmetic operators, JavaScript supports more complex mathematical 
operations through a set of functions and constants defined as properties of the Math object:</p>

<pre>
Math.pow(2,53) // =&gt; 9007199254740992: 2 to the power 53.
Math.round(.6) // =&gt; 1.0: round to the nearest integer.
Math.ceil(.6) // =&gt; 1.0: round up to an integer.
Math.floor(.6) // =&gt; 0.0: round down to an integer.
Math.abs(-5) // =&gt; 5: absolute value.
Math.max(x,y,z) // Return the largest argument.
Math.min(x,y,z) // Return the smallest argument.
Math.random() // Pseudo-random number x where 0 &lt;= x &lt; 1.0.
Math.PI // π: circumference of a circle / diameter.
Math.E // e: The base of the natural logarithm.
Math.sqrt(3) // =&gt; 3&ast;&ast;0.5: the square root of 3.
Math.pow(3, 1/3) // =&gt; 3&ast;&ast;(1/3): the cube root of 3.
Math.sin(0) // Trigonometry: also Math.cos, Math.atan, etc.
Math.log(10) // Natural logarithm of 10.
Math.log(100)/Math.LN10 // Base 10 logarithm of 100.
Math.log(512)/Math.LN2 // Base 2 logarithm of 512.
Math.exp(3) // Math.E cubed.
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>ES6 defines more functions on the Math object:</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
Math.cbrt(27) // =&gt; 3: cube root.
Math.hypot(3, 4) // =&gt; 5: square root of sum of squares of all arguments.
Math.log10(100) // =&gt; 2: Base-10 logarithm.
Math.log2(1024) // =&gt; 10: Base-2 logarithm.
Math.log1p(x) // Natural log of (1+x); accurate for very small x.
Math.expm1(x) // Math.exp(x)-1; the inverse of Math.log1p().
Math.sign(x) // -1, 0, or 1 for arguments &lt;, ==, or &gt; 0.
Math.imul(2,3) // =&gt; 6: optimized multiplication of 32-bit integers.
Math.clz32(0xf) // =&gt; 28: number of leading zero bits in a 32-bit integer.
Math.trunc(3.9) // =&gt; 3: convert to an integer by truncating fractional part.
Math.fround(x) // Round to nearest 32-bit float number.
Math.sinh(x) // Hyperbolic sine. Also Math.cosh(), Math.tanh().
Math.asinh(x) // Hyperbolic arcsine. Also Math.acosh(), Math.atanh().
</pre>

<table>
<table border="0">
  <tr>
    <td><b style="font-size:30px">Sequence</b></td>
    <td><b style="font-size:30px">Character represented</b></td>
  </tr>
  <tr>
    <td>\r</td>
    <td>Carriage return (\u000D)</td>
  </tr>
  <tr>
    <td>\"</td>
    <td>Double quote (\u0022)</td>
  </tr>
  <tr>
    <td>\'</td>
    <td>Apostrophe or single quote (\u0027)</td>
  </tr>
  <tr>
    <td>\\</td>
    <td>Backslash (\u005C)</td>
  </tr>
  <tr>
    <td>\xnn</td>
    <td>The Unicode character specified by the two hexadecimal digits nn</td>
  </tr>
  <tr>
    <td>\unnnn</td>
    <td>The Unicode character specified by the four hexadecimal digits nnnn</td>
  </tr>
  <tr>
    <td>\u{n}</td>
    <td>The Unicode character specified by the codepoint n, where n is one to six 
	  hexadecimal digits between 0 and 10FFFF (ES6)</td>
  </tr>
</table>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Working with Strings</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>let s = "Hello, world"; // Start with some text.</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>// Obtaining portions of a string</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
s.substring(1,4) // =&gt; "ell": the 2nd, 3rd, and 4th characters.
s.slice(1,4) // =&gt; "ell": same thing.
s.slice(-3) // =&gt; "rld": last 3 characters.
s.split(", ") // =&gt; ["Hello", "world"]: split at delimiter string.
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>// Searching a string</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
s.indexOf("l") // =&gt; 2: position of first letter l.
s.indexOf("l", 3) // =&gt; 3: position of first "l" at or after 3.
s.indexOf("zz") // =&gt; -1: s does not include the substring "zz".
s.lastIndexOf("l") // =&gt; 10: position of last letter l.
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>// Boolean searching functions in ES6 and later</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
s.startsWith("Hell") // =&gt; true: the string starts with these
s.endsWith("!") // =&gt; false: s does not end with that
s.includes("or") // =&gt; true: s includes substring "or"
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>// Creating modified versions of a string</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
s.replace("llo", "ya") // =&gt; "Heya, world".
s.toLowerCase() // =&gt; "hello, world".
s.toUpperCase() // =&gt; "HELLO, WORLD".
s.normalize() // Unicode NFC normalization: ES6.
s.normalize("NFD") // NFD normalization. Also "NFKC", "NFKD".
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>// Inspecting individual (16-bit) characters of a string</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
s.charAt(0) // =&gt; "H": the first character.
s.charAt(s.length-1) // =&gt; "d": the last character.
s.charCodeAt(0) // =&gt; 72: 16-bit number at the specified position.
s.codePointAt(0) // =&gt; 72: ES6, works for codepoints > 16 bits.
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>// String padding functions in ES2017</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
"x".padStart(3) // =&gt; " x": add spaces on the left to a length of 3.
"x".padEnd(3) // =&gt; "x ": add spaces on the right to a length of 3.
"x".padStart(3, "&ast;") // =&gt; "&ast;&ast;x": add stars on the left to a length of 3.
"x".padEnd(3, "-") // =&gt; "x--": add dashes on the right to a length of 3.
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>// Space trimming functions. trim() is ES5; others ES2019</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
" test ".trim() // =&gt; "test": remove spaces at start and end.
" test ".trimStart() // =&gt; "test ": remove spaces on left. Also trimLeft.
" test ".trimEnd() // =&gt; " test": remove spaces at right. Also trimRight.
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>// Miscellaneous string methods</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
s.concat("!") // =&gt; "Hello, world!": just use + operator instead.
"&lt;&gt;".repeat(5) // =&gt; "&lt;&gt;&lt;&gt;&lt;&gt;&lt;&gt;&lt;&gt;": concatenate n copies.
</pre>

<p>Remember that strings are immutable in JavaScript. Methods like replace() and toUpperCase() 
return new strings: they do not modify the string on which they are invoked.</p>

<p>Strings can also be treated like read-only arrays, and you can access individual characters 
(16-bit values) from a string using square brackets instead of the charAt() method:</p>

<pre>
let s = "hello, world";
s[0] // =&gt; "h".
s[s.length-1] // =&gt; "d".
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch3-3-5">3.3.5 Pattern Matching</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>JavaScript defines a datatype known as a regular expression (or RegExp) for describing and 
matching patterns in strings of text. RegExps are not one of the fundamental datatypes in JavaScript, 
but they have a literal syntax like numbers and strings do, so they sometimes seem like they are 
fundamental. The grammar of regular expression literals is complex and the API they define is 
nontrivial. They are documented in detail in §11.3. Because RegExps are powerful and commonly 
used for text processing, however, this section provides a brief overview.</p>

<p>Text between a pair of slashes constitutes a regular expression literal. The second slash in the 
pair can also be followed by one or more letters, which modify the meaning of the pattern. For 
example:</p>

<pre>
/^HTML/; // Match the letters H T M L at the start of a string.
/[1-9][0-9]&ast;/; // Match a nonzero digit, followed by any # of digits.
/\bjavascript\b/i; // Match "javascript" as a word, case-insensitive.
</pre>

<p>RegExp objects define a number of useful methods, and strings also have methods that accept 
RegExp arguments. For example:</p>

<pre>
let text = "testing: 1, 2, 3"; // Sample text.
let pattern = /\d+/g; // Matches all instances of one or more digits.
pattern.test(text) // =&gt; true: a match exists.
text.search(pattern) // =&gt; 9: position of first match.
text.match(pattern) // =&gt; ["1", "2", "3"]: array of all matches.
text.replace(pattern, "#") // =&gt; "testing: #, #, #".
text.split(/\D+/) // =&gt; ["","1","2","3"]: split on nondigits.
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch3-6">3.6 Symbols</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Symbols were introduced in ES6 to serve as non-string property names. To understand Symbols, 
you need to know that JavaScript’s fundamental Object type is an unordered collection of properties, 
where each property has a name and a value. Property names are typically (and until ES6, were 
exclusively) strings. But in ES6 and later, Symbols can also serve this purpose:</p>

<pre>
let strname = "string name"; // A string to use as a property name.
let symname = Symbol("propname"); // A Symbol to use as a property name.
typeof strname // =&gt; "string": strname is a string.
typeof symname // =&gt; "symbol": symname is a symbol.
let o = {}; // Create a new object.
o[strname] = 1; // Define a property with a string name.
o[symname] = 2; // Define a property with a Symbol name.
o[strname] // =&gt; 1: access the string-named property.
o[symname] // =&gt; 2: access the symbol-named property.
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch3-9">3.9 Type Conversions</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>JavaScript is very flexible about the types of values it requires. We’ve seen this for booleans: 
when JavaScript expects a boolean value, you may supply a value of any type, and JavaScript will 
convert it as needed. Some values (“truthy” values) convert to true and others (“falsy” values) 
convert to false. The same is true for other types: if JavaScript wants a string, it will convert 
whatever value you give it to a string. If JavaScript wants a number, it will try to convert the 
value you give it to a number (or to NaN if it cannot perform a meaningful conversion).</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Some examples:</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
10 + " objects" // =&gt; "10 objects": Number 10 converts to a string.
"7" * "4" // =&gt; 28: both strings convert to numbers.
let n = 1 - "x"; // n == NaN; string "x" can't convert to a number.
n + " objects" // =&gt; "NaN objects": NaN converts to string "NaN".
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Conversions and Equality</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
null == undefined // =&gt; true: These two values are treated as equal.
"0" == 0 // =&gt; true: String converts to a number before comparing.
0 == false // =&gt; true: Boolean converts to number before comparing.
"0" == false // =&gt; true: Both operands convert to 0 before comparing!
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch3-10-1">3.10.1 Declarations with let and const</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>In modern JavaScript (ES6 and later), variables are declared with the let keyword, like this:</p>

<pre>
let i;
let sum;
</pre>

<p>You can also declare multiple variables in a single let statement:</p>

<pre>
let i, sum;
</pre>

<p>It is a good programming practice to assign an initial value to your variables when you declare 
them, when this is possible:</p>

<pre>
let message = "hello";
let i = 0, j = 0, k = 0;
let x = 2, y = x&ast;x; // Initializers can use previously declared variables.
</pre>

<p>If you don’t specify an initial value for a variable with the let statement, the variable is 
declared, but its value is undefined until your code assigns a value to it.</p>

<p>To declare a constant instead of a variable, use const instead of let. const works just like 
let except that you must initialize the constant when you declare it:</p>

<pre>
const H0 = 74; // Hubble constant (km/s/Mpc).
const C = 299792.458; // Speed of light in a vacuum (km/s).
const AU = 1.496E8; // Astronomical Unit: distance to the sun (km).
</pre>

<p>Here are simple destructuring assignments using arrays of values:</p>

<pre>
let [x,y] = [1,2]; // Same as let x=1, y=2.
[x,y] = [x+1,y+1]; // Same as x = x + 1, y = y + 1.
[x,y] = [y,x]; // Swap the value of the two variables.
[x,y] // => [3,2]: the incremented and swapped value.
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch4-4">4.4 Property Access Expressions</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>A property access expression evaluates to the value of an object property or an array element. 
JavaScript defines two syntaxes for property access:</p>

<pre>
expression . identifier
expression [ expression ]
</pre>

<p>The first style of property access is an expression followed by a period and an identifier. The 
expression specifies the object, and the identifier specifies the name of the desired property. The 
second style of property access follows the first expression (the object or array) with another 
expression in square brackets. This second expression specifies the name of the desired property 
or the index of the desired array element.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Here are some concrete examples:</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
let o = {x: 1, y: {z: 3}}; // An example object.
let a = [o, 4, [5, 6]]; // An example array that contains the object.
o.x // =&gt; 1: property x of expression o.
o.y.z // =&gt; 3: property z of expression o.y.
o["x"] // =&gt; 1: property x of object o.
a[1] // =&gt; 4: element at index 1 of expression a.
a[2]["1"] // =&gt; 6: element at index 1 of expression a[2].
a[0].x // =&gt; 1: property x of expression a[0].
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Here are some examples:</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
1 + 2 // =&gt; 3: addition.
"1" + "2" // =&gt; "12": concatenation.
"1" + 2 // =&gt; "12": concatenation after number-to-string.
1 + {} // =&gt; "1[object Object]": concatenation after object-to-string.
true + true // =&gt; 2: addition after boolean-to-number.
2 + null // =&gt; 2: addition after null converts to 0.
2 + undefined // =&gt; NaN: addition after undefined converts to NaN.
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch4-8-1">4.8.1 The + Operator</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The binary + operator adds numeric operands or concatenates string operands:</p>

<pre>
1 + 2 // =&gt; 3.
"hello" + " " + "there" // =&gt; "hello there".
"1" + "2" // =&gt; "12".
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>For example:</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
1 + 2 + " blind mice" // =&gt; "3 blind mice".
1 + (2 + " blind mice") // =&gt; "12 blind mice".
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>The =, ==, and === operators</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>JavaScript supports =, ==, and === operators. Be sure you understand the differences between 
these assignment, equality, and strict equality operators, and be careful to use the correct one 
when coding! Although it is tempting to read all three operators as “equals,” it may help to 
reduce confusion if you read “gets” or “is assigned” for =, “is equal to” for ==, and “is 
strictly equal to” for ===.</p>

<p>The == operator is a legacy feature of JavaScript and is widely considered to be a source of 
bugs. You should almost always use === instead of ==, and !== instead of !=.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Strict equality</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The strict equality operator === evaluates its operands, then compares the two values as follows, 
performing no type conversion:</p>

<ul>
  <li>If the two values have different types, they are not equal.</li>
  <li>If both values are null or both values are undefined, they are equal.</li>
  <li>If both values are the boolean value true or both are the boolean value false, they are equal.</li>
  <li>If one or both values is NaN, they are not equal. (This is surprising, but the NaN value is 
    never equal to any other value, including itself! To check whether a value x is NaN, use x 
	!== x, or the global isNaN() function.)</li>
  <li>If both values are numbers and have the same value, they are equal. If one value is 0 and the 
    other is -0, they are also equal.</li>
  <li>If both values are strings and contain exactly the same 16-bit values (see the side‐bar in §3.3) 
    in the same positions, they are equal. If the strings differ in length or content, they are not 
	equal. Two strings may have the same meaning and the same visual appearance, but still be encoded 
	using different sequences of 16-bit values. JavaScript performs no Unicode normalization, and a 
	pair of strings like this is not considered equal to the === or == operators.</li>
  <li>If both values refer to the same object, array, or function, they are equal. If they refer to 
    different objects, they are not equal, even if both objects have identical properties.</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Equality with type conversion</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Remember that JavaScript strings are sequences of 16-bit integer values, and that string comparison 
is just a numerical comparison of the values in the two strings. The numerical encoding order defined 
by Unicode may not match the traditional collation order used in any particular language or locale. 
Note in particular that string comparison is case-sensitive, and all capital ASCII letters are “less 
than” all lowercase ASCII letters. This rule can cause confusing results if you do not expect it. For 
example, according to the &lt; operator, the string “Zoo” comes before the string “aardvark”.</p>

<p>For a more robust string-comparison algorithm, try the <b>String.localeCompare()</b> method, which 
also takes locale-specific definitions of alphabetical order into account. For case-insensitive 
comparisons, you can convert the strings to all lower‐case or all uppercase using 
<b>String.toLowerCase()</b> or <b>String.toUpperCase()</b>. And, for a more general and better 
localized string comparison tool, use the <b>Intl.Collator</b> class described in §11.7.3.</p>

<p>Both the + operator and the comparison operators behave differently for numeric and string 
operands. + favors strings: it performs concatenation if either operand is a string. The comparison 
operators favor numbers and only perform string comparison if both operands are strings:</p>

<pre>
1 + 2 // =&gt; 3: addition.
"1" + "2" // =&gt; "12": concatenation.
"1" + 2 // =&gt; "12": 2 is converted to "2".
11 &lt; 3 // =&gt; false: numeric comparison.
"11" &lt; "3" // =&gt; true: string comparison.
"11" &lt; 3 // =&gt; false: numeric comparison, "11" converted to 11.
"one" &lt; 3 // =&gt; false: numeric comparison, "one" converted to NaN.
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch4-9-3">4.9.3 The in Operator</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The in operator expects a left-side operand that is a string, symbol, or value that can be 
converted to a string. It expects a right-side operand that is an object. It evaluates to true if 
the left-side value is the name of a property of the right-side object. For example:</p>

<pre>
let point = {x: 1, y: 1}; // Define an object.
"x" in point // =&gt; true: object has property named "x".
"z" in point // =&gt; false: object has no "z" property.
"toString" in point // =&gt; true: object inherits toString method.
let data = [7,8,9]; // An array with elements (indices) 0, 1, and 2.
"0" in data // =&gt; true: array has an element "0".
1 in data // =&gt; true: numbers are converted to strings.
3 in data // =&gt; false: no element 3.
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch4-9-4">4.9.4 The instanceof Operator</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The instanceof operator expects a left-side operand that is an object and a right-side operand 
that identifies a class of objects. The operator evaluates to true if the left-side object is an 
instance of the right-side class and evaluates to false otherwise. In JavaScript, classes of 
objects are defined by the constructor function that initializes them. Thus, the right-side 
operand of instanceof should be a function. Here are examples:</p>

<pre>
let d = new Date(); // Create a new object with the Date() constructor.
d instanceof Date // =&gt; true: d was created with Date().
d instanceof Object // =&gt; true: all objects are instances of Object.
d instanceof Number // =&gt; false: d is not a Number object.
let a = [1, 2, 3]; // Create an array with array literal syntax.
a instanceof Array // =&gt; true: a is an array.
a instanceof Object // =&gt; true: all arrays are objects.
a instanceof RegExp // =&gt; false: arrays are not regular expressions.
</pre>

<p>Note that all objects are instances of Object. instanceof considers the “superclasses” when 
deciding whether an object is an instance of a class. If the left-side operand of instanceof is not 
an object, instanceof returns false. If the righthand side is not a class of objects, it throws a 
TypeError.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch4-13-3">4.13.3 The typeof Operator</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>typeof is a unary operator that is placed before its single operand, which can be of any type. 
Its value is a string that specifies the type of the operand. Table 4-3 specifies the value of the 
typeof operator for any JavaScript value.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Values returned by the typeof operator</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<table>
<table border="0">
 <tr>
    <td><b style="font-size:30px">x</b></td>
    <td><b style="font-size:30px">typeof x</b></td>
 </tr>
 <tr>
    <td>undefined</td>
    <td>"undefined"</td>
 </tr>
 <tr>
    <td>null</td>
    <td>"object"</td>
 </tr>
 <tr>
    <td>true or false</td>
    <td>"boolean"</td>
 </tr>
 <tr>
    <td>any number or NaN</td>
    <td>"number"</td>
 </tr>
 <tr>
    <td>any BigInt</td>
    <td>"bigint"</td>
 </tr>
 <tr>
    <td>any string</td>
    <td>"string"</td>
 </tr>
 <tr>
    <td>any symbol</td>
    <td>"symbol"</td>
 </tr>
 <tr>
    <td>any function</td>
    <td>"function"</td>
 </tr>
 <tr>
    <td>any nonfunction object</td>
    <td>"object"</td>
 </tr>
</table>
