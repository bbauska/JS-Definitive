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
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
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

<!-- chapter 1 -->

Chapter 1. Introduction to JavaScript

JavaScript is the programming language of the web. The overwhelming majority of websites use JavaScript, and all modern web browsers—on desktops, tablets, and phones—include JavaScript interpreters, making JavaScript the most-deployed programming language in history. Over the last decade, Node.js has enabled JavaScript programming outside of web browsers, and the dramatic success of Node means that JavaScript is now also the most-used programming language among software developers. Whether you’re starting from scratch or are already using JavaScript professionally, this book will help you master the language.

If you are already familiar with other programming languages, it may help you to know that JavaScript is a high-level, dynamic, interpreted programming language that is well-suited to object-oriented and functional programming styles. JavaScript’s variables are untyped. Its syntax is loosely based on Java, but the languages are otherwise unrelated. JavaScript derives its first-class functions from Scheme and its prototype-based inheritance from the little-known language Self. But you do not need to know any of those languages, or be familiar with those terms, to use this book and learn JavaScript.

The name “JavaScript” is quite misleading. Except for a superficial syntactic resemblance, JavaScript is completely different from the Java programming language. And JavaScript has long since outgrown its scripting-language roots to become a ...

<!-- chapter 2 -->

Chapter 2. Lexical Structure

The lexical structure of a programming language is the set of elementary rules that specifies how you write programs in that language. It is the lowest-level syntax of a language: it specifies what variable names look like, the delimiter characters for comments, and how one program statement is separated from the next, for example. This short chapter documents the lexical structure of JavaScript. It covers:

    Case sensitivity, spaces, and line breaks

    Comments

    Literals

    Identifiers and reserved words

    Unicode

    Optional semicolons

2.1 The Text of a JavaScript Program

JavaScript is a case-sensitive language. This means that language keywords, variables, function names, and other identifiers must always be typed with a consistent capitalization of letters. The while keyword, for example, must be typed “while,” not “While” or “WHILE.” Similarly, online, Online, OnLine, and ONLINE are four distinct variable names.

JavaScript ignores spaces that appear between tokens in programs. For the most part, JavaScript also ignores line breaks (but see §2.6 for an exception). Because you can use spaces and newlines freely in your programs, you can format and indent your programs in a neat and consistent way that makes the code easy to read and understand.

In addition to the regular space character (\u0020), JavaScript also recognizes tabs, assorted ASCII control characters, and various Unicode space characters as whitespace. JavaScript recognizes newlines, ...
<!-- chapter 3 -->

Chapter 3. Types, Values, and Variables

Computer programs work by manipulating values, such as the number 3.14 or the text “Hello World.” The kinds of values that can be represented and manipulated in a programming language are known as types, and one of the most fundamental characteristics of a programming language is the set of types it supports. When a program needs to retain a value for future use, it assigns the value to (or “stores” the value in) a variable. Variables have names, and they allow use of those names in our programs to refer to values. The way that variables work is another fundamental characteristic of any programming language. This chapter explains types, values, and variables in JavaScript. It begins with an overview and some definitions.
3.1 Overview and Definitions

JavaScript types can be divided into two categories: primitive types and object types. JavaScript’s primitive types include numbers, strings of text (known as strings), and Boolean truth values (known as booleans). A significant portion of this chapter is dedicated to a detailed explanation of the numeric (§3.2) and string (§3.3) types in JavaScript. Booleans are covered in §3.4.

The special JavaScript values null and undefined are primitive values, but they are not numbers, strings, or booleans. Each value is typically considered to be the sole member of its own special type. §3.5 has more about null and undefined. ES6 adds a new special-purpose type, known as Symbol, that enables the definition ...
<!-- chapter 4 -->

Chapter 4. Expressions and Operators

This chapter documents JavaScript expressions and the operators with which many of those expressions are built. An expression is a phrase of JavaScript that can be evaluated to produce a value. A constant embedded literally in your program is a very simple kind of expression. A variable name is also a simple expression that evaluates to whatever value has been assigned to that variable. Complex expressions are built from simpler expressions. An array access expression, for example, consists of one expression that evaluates to an array followed by an open square bracket, an expression that evaluates to an integer, and a close square bracket. This new, more complex expression evaluates to the value stored at the specified index of the specified array. Similarly, a function invocation expression consists of one expression that evaluates to a function object and zero or more additional expressions that are used as the arguments to the function.

The most common way to build a complex expression out of simpler expressions is with an operator. An operator combines the values of its operands (usually two of them) in some way and evaluates to a new value. The multiplication operator * is a simple example. The expression x * y evaluates to the product of the values of the expressions x and y. For simplicity, we sometimes say that an operator returns a value rather than “evaluates to” a value.

This chapter documents all of JavaScript’s operators, and ...
<!-- chapter 5 -->

Chapter 5. Statements

Chapter 4 described expressions as JavaScript phrases. By that analogy, statements are JavaScript sentences or commands. Just as English sentences are terminated and separated from one another with periods, JavaScript statements are terminated with semicolons (§2.6). Expressions are evaluated to produce a value, but statements are executed to make something happen.

One way to “make something happen” is to evaluate an expression that has side effects. Expressions with side effects, such as assignments and function invocations, can stand alone as statements, and when used this way are known as expression statements. A similar category of statements are the declaration statements that declare new variables and define new functions.

JavaScript programs are nothing more than a sequence of statements to execute. By default, the JavaScript interpreter executes these statements one after another in the order they are written. Another way to “make something happen” is to alter this default order of execution, and JavaScript has a number of statements or control structures that do just this:

Conditionals

    Statements like if and switch that make the JavaScript interpreter execute or skip other statements depending on the value of an expression
Loops

    Statements like while and for that execute other statements repetitively
Jumps

    Statements like break, return, and throw that cause the interpreter to jump to another part of the program

The sections that follow describe ...
<!-- chapter 6 -->

Chapter 6. Objects

Objects are JavaScript’s most fundamental datatype, and you have already seen them many times in the chapters that precede this one. Because objects are so important to the JavaScript language, it is important that you understand how they work in detail, and this chapter provides that detail. It begins with a formal overview of objects, then dives into practical sections about creating objects and querying, setting, deleting, testing, and enumerating the properties of objects. These property-focused sections are followed by sections that explain how to extend, serialize, and define important methods on objects. Finally, the chapter concludes with a long section about new object literal syntax in ES6 and more recent versions of the language.
6.1 Introduction to Objects

An object is a composite value: it aggregates multiple values (primitive values or other objects) and allows you to store and retrieve those values by name. An object is an unordered collection of properties, each of which has a name and a value. Property names are usually strings (although, as we’ll see in §6.10.3, property names can also be Symbols), so we can say that objects map strings to values. This string-to-value mapping goes by various names—you are probably already familiar with the fundamental data structure under the name “hash,” “hashtable,” “dictionary,” or “associative array.” An object is more than a simple string-to-value map, however. In addition to maintaining its own set of ...
<!-- chapter 7 -->

Chapter 7. Arrays

This chapter documents arrays, a fundamental datatype in JavaScript and in most other programming languages. An array is an ordered collection of values. Each value is called an element, and each element has a numeric position in the array, known as its index. JavaScript arrays are untyped: an array element may be of any type, and different elements of the same array may be of different types. Array elements may even be objects or other arrays, which allows you to create complex data structures, such as arrays of objects and arrays of arrays. JavaScript arrays are zero-based and use 32-bit indexes: the index of the first element is 0, and the highest possible index is 4294967294 (232−2), for a maximum array size of 4,294,967,295 elements. JavaScript arrays are dynamic: they grow or shrink as needed, and there is no need to declare a fixed size for the array when you create it or to reallocate it when the size changes. JavaScript arrays may be sparse: the elements need not have contiguous indexes, and there may be gaps. Every JavaScript array has a length property. For nonsparse arrays, this property specifies the number of elements in the array. For sparse arrays, length is larger than the highest index of any element.

JavaScript arrays are a specialized form of JavaScript object, and array indexes are really little more than property names that happen to be integers. We’ll talk more about the specializations of arrays elsewhere in this chapter. Implementations ...
<!-- chapter 8 -->

Chapter 8. Functions

This chapter covers JavaScript functions. Functions are a fundamental building block for JavaScript programs and a common feature in almost all programming languages. You may already be familiar with the concept of a function under a name such as subroutine or procedure.

A function is a block of JavaScript code that is defined once but may be executed, or invoked, any number of times. JavaScript functions are parameterized: a function definition may include a list of identifiers, known as parameters, that work as local variables for the body of the function. Function invocations provide values, or arguments, for the function’s parameters. Functions often use their argument values to compute a return value that becomes the value of the function-invocation expression. In addition to the arguments, each invocation has another value—the invocation context—that is the value of the this keyword.

If a function is assigned to a property of an object, it is known as a method of that object. When a function is invoked on or through an object, that object is the invocation context or this value for the function. Functions designed to initialize a newly created object are called constructors. Constructors were described in §6.2 and will be covered again in Chapter 9.

In JavaScript, functions are objects, and they can be manipulated by programs. JavaScript can assign functions to variables and pass them to other functions, for example. Since functions are objects, you ...
<!-- chapter 9 -->

Chapter 9. Classes

JavaScript objects were covered in Chapter 6. That chapter treated each object as a unique set of properties, different from every other object. It is often useful, however, to define a class of objects that share certain properties. Members, or instances, of the class have their own properties to hold or define their state, but they also have methods that define their behavior. These methods are defined by the class and shared by all instances. Imagine a class named Complex that represents and performs arithmetic on complex numbers, for example. A Complex instance would have properties to hold the real and imaginary parts (the state) of the complex number. And the Complex class would define methods to perform addition and multiplication (the behavior) of those numbers.

In JavaScript, classes use prototype-based inheritance: if two objects inherit properties (generally function-valued properties, or methods) from the same prototype, then we say that those objects are instances of the same class. That, in a nutshell, is how JavaScript classes work. JavaScript prototypes and inheritance were covered in §6.2.3 and §6.3.2, and you will need to be familiar with the material in those sections to understand this chapter. This chapter covers prototypes in §9.1.

If two objects inherit from the same prototype, this typically (but not necessarily) means that they were created and initialized by the same constructor function or factory function. Constructors have been covered ...
<!-- chapter 10 -->

Chapter 10. Modules

The goal of modular programming is to allow large programs to be assembled using modules of code from disparate authors and sources and for all of that code to run correctly even in the presence of code that the various module authors did not anticipate. As a practical matter, modularity is mostly about encapsulating or hiding private implementation details and keeping the global namespace tidy so that modules cannot accidentally modify the variables, functions, and classes defined by other modules.

Until recently, JavaScript had no built-in support for modules, and programmers working on large code bases did their best to use the weak modularity available through classes, objects, and closures. Closure-based modularity, with support from code-bundling tools, led to a practical form of modularity based on a require() function, which was adopted by Node. require()-based modules are a fundamental part of the Node programming environment but were never adopted as an official part of the JavaScript language. Instead, ES6 defines modules using import and export keywords. Although import and export have been part of the language for years, they were only implemented by web browsers and Node relatively recently. And, as a practical matter, JavaScript modularity still depends on code-bundling tools.

The sections that follow cover:

    Do-it-yourself modules with classes, objects, and closures

    Node modules using require()

    ES6 modules using export, import, and import() ...
<!-- chapter 11 -->

Chapter 11. The JavaScript Standard Library

Some datatypes, such as numbers and strings (Chapter 3), objects (Chapter 6), and arrays (Chapter 7) are so fundamental to JavaScript that we can consider them to be part of the language itself. This chapter covers other important but less fundamental APIs that can be thought of as defining the “standard library” for JavaScript: these are useful classes and functions that are built in to JavaScript and available to all JavaScript programs in both web browsers and in Node.1

The sections of this chapter are independent of one another, and you can read them in any order. They cover:

    The Set and Map classes for representing sets of values and mappings from one set of values to another set of values.

    Array-like objects known as TypedArrays that represent arrays of binary data, along with a related class for extracting values from non-array binary data.

    Regular expressions and the RegExp class, which define textual patterns and are useful for text processing. This section also covers regular expression syntax in detail.

    The Date class for representing and manipulating dates and times.

    The Error class and its various subclasses, instances of which are thrown when errors occur in JavaScript programs.

    The JSON object, whose methods support serialization and deserialization of JavaScript data structures composed of objects, arrays, strings, numbers, and booleans.

    The Intl object and the classes it defines that can help you localize ...
<!-- chapter 12 -->

Chapter 12. Iterators and Generators

Iterable objects and their associated iterators are a feature of ES6 that we’ve seen several times throughout this book. Arrays (including TypedArrays) are iterable, as are strings and Set and Map objects. This means that the contents of these data structures can be iterated—looped over—with the for/of loop, as we saw in §5.4.4:

let sum = 0;
for(let i of [1,2,3]) { // Loop once for each of these values
    sum += i;
}
sum   // => 6

Iterators can also be used with the ... operator to expand or “spread” an iterable object into an array initializer or function invocation, as we saw in §7.1.2:

let chars = [..."abcd"]; // chars == ["a", "b", "c", "d"]
let data = [1, 2, 3, 4, 5];
Math.max(...data)        // => 5

Iterators can be used with destructuring assignment:

let purpleHaze = Uint8Array.of(255, 0, 255, 128);
let [r, g, b, a] = purpleHaze; // a == 128

When you iterate a Map object, the returned values are [key, value] pairs, which work well with destructuring assignment in a for/of loop:

let m = new Map([["one", 1], ["two", 2]]);
for(let [k,v] of m) console.log(k, v); // Logs 'one 1' and 'two 2'

If you want to iterate just the keys or just the values rather than the pairs, you can use the keys() and values() methods:

[...m]            // => [["one", 1], ["two", 2]]: default iteration
[...m.entries()]  // => [["one", 1], ["two", 2]]: entries() method is the same
[...m.keys()]     // => ["one", "two"]: keys() method iterates just map keys
[...m.values()]   // => [1, 2]: values() ...
<!-- chapter 13 -->
Chapter 13. Asynchronous JavaScript

Some computer programs, such as scientific simulations and machine learning models, are compute-bound: they run continuously, without pause, until they have computed their result. Most real-world computer programs, however, are significantly asynchronous. This means that they often have to stop computing while waiting for data to arrive or for some event to occur. JavaScript programs in a web browser are typically event-driven, meaning that they wait for the user to click or tap before they actually do anything. And JavaScript-based servers typically wait for client requests to arrive over the network before they do anything.

This kind of asynchronous programming is commonplace in JavaScript, and this chapter documents three important language features that help make it easier to work with asynchronous code. Promises, new in ES6, are objects that represent the not-yet-available result of an asynchronous operation. The keywords async and await were introduced in ES2017 and provide new syntax that simplifies asynchronous programming by allowing you to structure your Promise-based code as if it was synchronous. Finally, asynchronous iterators and the for/await loop were introduced in ES2018 and allow you to work with streams of asynchronous events using simple loops that appear synchronous.

Ironically, even though JavaScript provides these powerful features for working with asynchronous code, there are no features of the core language that are
<!-- chapter 14 -->

Chapter 14. Metaprogramming

This chapter covers a number of advanced JavaScript features that are not commonly used in day-to-day programming but that may be valuable to programmers writing reusable libraries and of interest to anyone who wants to tinker with the details about how JavaScript objects behave.

Many of the features described here can loosely be described as “metaprogramming”: if regular programming is writing code to manipulate data, then metaprogramming is writing code to manipulate other code. In a dynamic language like JavaScript, the lines between programming and metaprogramming are blurry—even the simple ability to iterate over the properties of an object with a for/in loop might be considered “meta” by programmers accustomed to more static languages.

The metaprogramming topics covered in this chapter include:

    §14.1 Controlling the enumerability, deleteability, and configurability of object properties

    §14.2 Controlling the extensibility of objects, and creating “sealed” and “frozen” objects

    §14.3 Querying and setting the prototypes of objects

    §14.4 Fine-tuning the behavior of your types with well-known Symbols

    §14.5 Creating DSLs (domain-specific languages) with template tag functions

    §14.6 Probing objects with reflect methods

    §14.7 Controlling object behavior with Proxy

14.1 Property Attributes

The properties of a JavaScript object have names and values, of course, but each property also has three associated attributes that specify how that ...
<!-- chapter 15 -->

Chapter 15. JavaScript in Web Browsers

The JavaScript language was created in 1994 with the express purpose of enabling dynamic behavior in the documents displayed by web browsers. The language has evolved significantly since then, and at the same time, the scope and capabilities of the web platform have grown explosively. Today, JavaScript programmers can think of the web as a full-featured platform for application development. Web browsers specialize in the display of formatted text and images, but, like native operating systems, browsers also provide other services, including graphics, video, audio, networking, storage, and threading. JavaScript is the language that enables web applications to use the services provided by the web platform, and this chapter demonstrates how you can use the most important of these services.

The chapter begins with the web platform’s programming model, explaining how scripts are embedded within HTML pages (§15.1) and how JavaScript code is triggered asynchronously by events (§15.2). The sections that follow this introductory material document the core JavaScript APIs that enable your web applications to:

    Control document content (§15.3) and style (§15.4)

    Determine the on-screen position of document elements (§15.5)

    Create reusable user interface components (§15.6)

    Draw graphics (§15.7 and §15.8)

    Play and generate sounds (§15.9)

    Manage browser navigation and history (§15.10)

    Exchange data over the network (§15.11)

    Store data on ...
<!-- chapter 16 -->

Chapter 16. Server-Side JavaScript with Node

Node is JavaScript with bindings to the underlying operating system, making it possible to write JavaScript programs that read and write files, execute child processes, and communicate over the network. This makes Node useful as a:

    Modern alternative to shell scripts that does not suffer from the arcane syntax of bash and other Unix shells.

    General-purpose programming language for running trusted programs, not subject to the security constraints imposed by web browsers on untrusted code.

    Popular environment for writing efficient and highly concurrent web servers.

The defining feature of Node is its single-threaded event-based concurrency enabled by an asynchronous-by-default API. If you have programmed in other languages but have not done much JavaScript coding, or if you’re an experienced client-side JavaScript programmer used to writing code for web browers, using Node will be a bit of an adjustment, as is any new programming language or environment. This chapter begins by explaining the Node programming model, with an emphasis on concurrency, Node’s API for working with streaming data, and Node’s Buffer type for working with binary data. These initial sections are followed by sections that highlight and demonstrate some of the most important Node APIs, including those for working with files, networks, processes, and threads.

One chapter is not enough to document all of Node’s APIs, but my hope is that this chapter will explain ...

<!-- chapter 17 -->

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch17">Chapter 17. JavaScript Tools and Extensions</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Congratulations on reaching the final chapter of this book. If you have read everything that comes 
before, you now have a detailed understanding of the JavaScript language and know how to use it in 
Node and in web browsers. This chapter is a kind of graduation present: it introduces a handful of 
important programming tools that many JavaScript programmers find useful, and also describes two 
widely used extensions to the core JavaScript language. Whether or not you choose to use these 
tools and extensions for your own projects, you are almost certain to see them used in other 
projects, so it is important to at least know what they are.

The tools and language extensions covered in this chapter are:

    ESLint for finding potential bugs and style problems in your code.

    Prettier for formatting your JavaScript code in a standardized way.

    Jest as an all-in-one solution for writing JavaScript unit tests.

    npm for managing and installing the software libraries that your program depends on.

    Code-bundling tools—like webpack, Rollup, and Parcel—that convert your modules of JavaScript 
	code into a single bundle for use on the web.

    Babel for translating JavaScript code that uses brand-new language features (or that uses 
	language extensions) into JavaScript code that can run in current web browsers.

    The JSX language extension (used by the React framework) that allows you to describe user 
	interfaces using JavaScript expressions that look like ...
	
