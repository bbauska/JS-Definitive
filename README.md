<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h1>JS Definitive JavaScript</h1>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This book covers the JavaScript language and the JavaScript APIs implemented by web browsers 
and by Node. I wrote it for readers with some prior programming experience who want to learn 
JavaScript and also for programmers who already use JavaScript but want to take their understanding 
to a new level and really master the language. My goal with this book is to document the JavaScript 
language comprehensively and definitively and to provide an in-depth introduction to the most 
important client-side and server-side APIs available to JavaScript programs. As a result, this is 
a long and detailed book. My hope, however, is that it will reward careful study and that the time 
you spend reading it will be easily recouped in the form of higher programming productivity.</p>

<p>Previous editions of this book included a comprehensive reference section. I no longer feel that 
it makes sense to include that material in printed form when it is so quick and easy to find 
up-to-date reference material online. If you need to look up anything related to core or client-side 
JavaScript, I recommend you visit the MDN website. And for server-side Node APIs, I recommend you go 
directly to the source and consult the Node.js reference documentation.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>CHAPTER 1 Introduction to JavaScript</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>JavaScript is the programming language of the web. The overwhelming majority of websites use 
JavaScript, and all modern web browsers—on desktops, tablets, and phones—include JavaScript 
interpreters, making JavaScript the most-deployed programming language in history. Over the last 
decade, Node.js has enabled JavaScript programming outside of web browsers, and the dramatic 
success of Node means that JavaScript is now also the most-used programming language among 
software developers. Whether you’re starting from scratch or are already using JavaScript 
professionally, this book will help you master the language.</p>

<p>If you are already familiar with other programming languages, it may help you to know that 
JavaScript is a high-level, dynamic, interpreted programming language that is well-suited to 
object-oriented and functional programming styles. JavaScript’s variables are untyped. Its 
syntax is loosely based on Java, but the languages are otherwise unrelated. JavaScript derives 
its first-class functions from Scheme and its prototype-based inheritance from the little-known 
language Self. But you do not need to know any of those languages, or be familiar with those 
terms, to use this book and learn JavaScript.</p>

<p>The name “JavaScript” is quite misleading. Except for a superficial syntactic resemblance, 
JavaScript is completely different from the Java programming language. And JavaScript has long 
since outgrown its scripting-language roots to become a robust and efficient general-purpose 
language suitable for serious software engineering and projects with huge codebases.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>1.1 Exploring JavaScript</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>When learning a new programming language, it’s important to try the examples in the book, then 
modify them and try them again to test your understanding of the language. To do that, you need a 
JavaScript interpreter.</p>

<p>The easiest way to try out a few lines of JavaScript is to open up the web developer tools in 
your web browser (with F12, Ctrl-Shift-I, or Command-Option-I) and select the Console tab. You can 
then type code at the prompt and see the results as you type. Browser developer tools often appear 
as panes at the bottom or right of the browser window, but you can usually detach them as separate 
windows (as pictured in Figure 1-1), which is often quite convenient.</p>

<p>Another way to try out JavaScript code is to download and install Node from https://nodejs.org. 
Once Node is installed on your system, you can simply open a Terminal window and type node to begin 
an interactive JavaScript session like this one:</p>

<pre>$ node</pre>

<p>Welcome to Node.js v12.13.0.<br>
Type ".help" for more information.</p>

<pre>
&gt; .help
.break Sometimes you get stuck, this gets you out
.clear Alias for .break
.editor Enter editor mode
.exit Exit the repl
.help Print this help message
.load Load JS from a file into the REPL session
.save Save all evaluated commands in this REPL session to a file
</pre>

<p>Press ^C to abort current expression, ^D to exit the repl</p>

<pre>
&gt; let x = 2, y = 3;
undefined
5&gt; x + y
&gt; (x === 2) && (y === 3)
true
&gt; (x &gt; 3) || (y &lt; 3)
false
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>1.2 Hello World</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>When you are ready to start experimenting with longer chunks of code, these line-by-line 
interactive environments may no longer be suitable, and you will probably prefer to write your 
code in a text editor. From there, you can copy and paste to the JavaScript console or into a Node 
session. Or you can save your code to a file (the traditional filename extension for JavaScript 
code is .js) and then run that file of JavaScript code with Node:</p>

<pre>$ node snippet.js</pre>

<p>If you use Node in a noninteractive manner like this, it won’t automatically print out the value 
of all the code you run, so you’ll have to do that yourself. You can use the function console.log() 
to display text and other JavaScript values in your terminal window or in a browser’s developer 
tools console. So, for example, if you create a hello.js file containing this line of code:</p>

<pre>console.log("Hello World!");</pre>

<p>and execute the file with node hello.js, you’ll see the message “Hello World!”
printed out.</p>

<p>If you want to see that same message printed out in the JavaScript console of a web browser, create 
a new file named hello.html, and put this text in it:</p>

<pre>&lt;script src="hello.js"&gt;&lt;/script&gt;</pre>

<p>Then load hello.html into your web browser using a file:// URL like this one:
file:///Users/username/javascript/hello.html</p>

<p>Open the developer tools window to see the greeting in the console.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>1.3 A Tour of JavaScript</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This section presents a quick introduction, through code examples, to the JavaScript
language. After this introductory chapter, we dive into JavaScript at the lowest level:
Chapter 2 explains things like JavaScript comments, semicolons, and the Unicode
character set. Chapter 3 starts to get more interesting: it explains JavaScript variables
and the values you can assign to those variables.</p>

<p>Here’s some sample code to illustrate the highlights of those two chapters:</p>

<pre>
// Anything following double slashes is an English-language comment.
// Read the comments carefully: they explain the JavaScript code.
// A variable is a symbolic name for a value.
// Variables are declared with the let keyword:
let x; // Declare a variable named x.
// Values can be assigned to variables with an = sign
x = 0; // Now the variable x has the value 0
x // => 0: A variable evaluates to its value.
// JavaScript supports several types of values
x = 1; // Numbers.
x = 0.01; // Numbers can be integers or reals.
x = "hello world"; // Strings of text in quotation marks.
x = 'JavaScript'; // Single quote marks also delimit strings.
x = true; // A Boolean value.
x = false; // The other Boolean value.
x = null; // Null is a special value that means "no value."
x = undefined; // Undefined is another special value like null.
</pre>

<p>Two other very important types that JavaScript programs can manipulate are objects and arrays. 
These are the subjects of Chapters 6 and 7, but they are so important that you’ll see them many 
times before you reach those chapters:</p>

<pre>
// JavaScript's most important datatype is the object.
// An object is a collection of name/value pairs, or a string to value map.
let book = { // Objects are enclosed in curly braces.
  topic: "JavaScript", // The property "topic" has value "JavaScript."
  edition: 7 // The property "edition" has value 7
}; // The curly brace marks the end of the object.
// Access the properties of an object with . or []:
book.topic // => "JavaScript"
book["edition"] // => 7: another way to access property values.
book.author = "Flanagan"; // Create new properties by assignment.
book.contents = {}; // {} is an empty object with no properties.
// Conditionally access properties with ?. (ES2020):
book.contents?.ch01?.sect1 // => undefined: book.contents has no ch01 property.
// JavaScript also supports arrays (numerically indexed lists) of values:
let primes = [2, 3, 5, 7]; // An array of 4 values, delimited with [ and ].
primes[0] // => 2: the first element (index 0) of the array.
primes.length // => 4: how many elements in the array.
primes[primes.length-1] // => 7: the last element of the array.
primes[4] = 9; // Add a new element by assignment.
primes[4] = 11; // Or alter an existing element by assignment.
let empty = []; // [] is an empty array with no elements.
empty.length // => 0
// Arrays and objects can hold other arrays and objects:
let points = [ // An array with 2 elements.
  {x: 0, y: 0}, // Each element is an object.
  {x: 1, y: 1}
];
let data = { // An object with 2 properties
  trial1: [[1,2], [3,4]], // The value of each property is an array.
  trial2: [[2,3], [4,5]] // The elements of the arrays are arrays.
};
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Comment Syntax in Code Examples</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>You may have noticed in the preceding code that some of the comments begin with an arrow 
(=&gt;). These show the value produced by the code before the comment and are my attempt to 
emulate an interactive JavaScript environment like a web browser console in a printed book.</p>

<p>Those // =&gt; comments also serve as an assertion, and I’ve written a tool that tests the
code and verifies that it produces the value specified in the comment. This should help, I hope, 
to reduce errors in the book.</p>

<p>There are two related styles of comment/assertion. If you see a comment of the form // a == 42, 
it means that after the code before the comment runs, the variable a will have the value 42. If 
you see a comment of the form // !, it means that the code on the line before the comment throws 
an exception (and the rest of the comment after the exclamation mark usually explains what kind 
of exception is thrown). You’ll see these comments used throughout the book.

<p>The syntax illustrated here for listing array elements within square braces or mapping object 
property names to property values inside curly braces is known as an initializer expression, and 
it is just one of the topics of Chapter 4. An expression is a phrase of JavaScript that can be 
evaluated to produce a value. For example, the use of . and [] to refer to the value of an object 
property or array element is an expression.</p>

<p>One of the most common ways to form expressions in JavaScript is to use operators:</p>

<pre>
// Operators act on values (the operands) to produce a new value.
// Arithmetic operators are some of the simplest:
3 + 2 // => 5: addition
3 - 2 // => 1: subtraction
3 * 2 // => 6: multiplication
3 / 2 // => 1.5: division
points[1].x - points[0].x // => 1: more complicated operands also work
"3" + "2" // => "32": + adds numbers, concatenates strings
// JavaScript defines some shorthand arithmetic operators
let count = 0; // Define a variable
count++; // Increment the variable
count--; // Decrement the variable
count += 2; // Add 2: same as count = count + 2;
count *= 3; // Multiply by 3: same as count = count * 3;
count // => 6: variable names are expressions, too.
// Equality and relational operators test whether two values are equal,
// unequal, less than, greater than, and so on. They evaluate to true or false.
let x = 2, y = 3; // These = signs are assignment, not equality tests
x === y // => false: equality
x !== y // => true: inequality
x < y // => true: less-than
x <= y // => true: less-than or equal
x > y // => false: greater-than
x >= y // => false: greater-than or equal
"two" === "three" // => false: the two strings are different
"two" > "three" // => true: "tw" is alphabetically greater than "th"
false === (x > y) // => true: false is equal to false
// Logical operators combine or invert boolean values
(x === 2) && (y === 3) // => true: both comparisons are true. && is AND
(x > 3) || (y < 3) // => false: neither comparison is true. || is OR
!(x === y) // => true: ! inverts a boolean value
</pre>

<p>If JavaScript expressions are like phrases, then JavaScript statements are like full sentences. 
Statements are the topic of Chapter 5. Roughly, an expression is something that computes a value 
but doesn’t do anything: it doesn’t alter the program state in any way. Statements, on the other 
hand, don’t have a value, but they do alter the state. You’ve seen variable declarations and 
assignment statements above. The other broad category of statement is control structures, such as 
conditionals and loops. You’ll see examples below, after we cover functions.</p>

<p>A function is a named and parameterized block of JavaScript code that you define once, and can 
then invoke over and over again. Functions aren’t covered formally until Chapter 8, but like objects 
and arrays, you’ll see them many times before you get to that chapter. Here are some simple examples:</p>

<pre>
// Functions are parameterized blocks of JavaScript code that we can invoke.
function plus1(x) { // Define a function named "plus1" with parameter "x"
return x + 1; // Return a value one larger than the value passed in
} // Functions are enclosed in curly braces
plus1(y) // => 4: y is 3, so this invocation returns 3+1
let square = function(x) { // Functions are values and can be assigned to vars
return x * x; // Compute the function's value
}; // Semicolon marks the end of the assignment.
square(plus1(y)) // => 16: invoke two functions in one expression
</pre>

<p>In ES6 and later, there is a shorthand syntax for defining functions. This concise syntax uses 
=&gt; to separate the argument list from the function body, so functions defined this way are known 
as arrow functions. Arrow functions are most commonly used when you want to pass an unnamed function 
as an argument to another function. The preceding code looks like this when rewritten to use arrow 
functions:</p>

<pre>
const plus1 = x => x + 1; // The input x maps to the output x + 1
const square = x => x * x; // The input x maps to the output x * x
plus1(y) // => 4: function invocation is the same
square(plus1(y)) // => 16
</pre>

<p>When we use functions with objects, we get methods:</p>

<pre>
// When functions are assigned to the properties of an object, we call
// them "methods." All JavaScript objects (including arrays) have methods:
let a = []; // Create an empty array
a.push(1,2,3); // The push() method adds elements to an array
a.reverse(); // Another method: reverse the order of elements
// We can define our own methods, too. The "this" keyword refers to the object
// on which the method is defined: in this case, the points array from earlier.
points.dist = function() { // Define a method to compute distance between points
let p1 = this[0]; // First element of array we're invoked on
let p2 = this[1]; // Second element of the "this" object
let a = p2.x-p1.x; // Difference in x coordinates
let b = p2.y-p1.y; // Difference in y coordinates
return Math.sqrt(a*a + // The Pythagorean theorem
b*b); // Math.sqrt() computes the square root
};
points.dist() // => Math.sqrt(2): distance between our 2 points
</pre>

<p>Now, as promised, here are some functions whose bodies demonstrate common JavaScript control 
structure statements:</p>

<pre>
// JavaScript statements include conditionals and loops using the syntax
// of C, C++, Java, and other languages.
function abs(x) { // A function to compute the absolute value.
if (x >= 0) { // The if statement...
return x; // executes this code if the comparison is true.
} // This is the end of the if clause.
else { // The optional else clause executes its code if
return -x; // the comparison is false.
} // Curly braces optional when 1 statement per clause.
} // Note return statements nested inside if/else.
abs(-10) === abs(10) // => true
function sum(array) { // Compute the sum of the elements of an array
let sum = 0; // Start with an initial sum of 0.
for(let x of array) { // Loop over array, assigning each element to x.
sum += x; // Add the element value to the sum.
} // This is the end of the loop.
} return sum; // Return the sum.
sum(primes) // => 28: sum of the first 5 primes 2+3+5+7+11
function factorial(n) { // A function to compute factorials
let product = 1; // Start with a product of 1
while(n > 1) { // Repeat statements in {} while expr in () is true
product *= n; // Shortcut for product = product * n;
n--; // Shortcut for n = n - 1
} // End of loop
return product; // Return the product
factorial(4) // => 24: 1*4*3*2
function factorial2(n) { // Another version using a different loop
let i, product = 1; // Start with 1
for(i=2; i <= n; i++) // Automatically increment i from 2 up to n
product *= i; // Do this each time. {} not needed for 1-line loops
} return product; // Return the factorial
factorial2(5) // => 120: 1*2*3*4*5
</pre>

<p>JavaScript supports an object-oriented programming style, but it is significantly different than 
“classical” object-oriented programming languages. Chapter 9 covers object-oriented programming in 
JavaScript in detail, with lots of examples. Here is a very simple example that demonstrates how to 
define a JavaScript class to represent 2D geometric points. Objects that are instances of this class 
have a single method, named distance(), that computes the distance of the point from the origin:</p>

<pre>
class Point { // By convention, class names are capitalized.
  constructor(x, y) { // Constructor function to initialize new instances.
    this.x = x; // This keyword is the new object being initialized.
    this.y = y; // Store function arguments as object properties.
  } // No return is necessary in constructor functions.
  distance() { // Method to compute distance from origin to point.
    return Math.sqrt( // Return the square root of x² + y².
      this.x * this.x + // this refers to the Point object on which
      this.y * this.y // the distance method is invoked.
    );
  }
}
// Use the Point() constructor function with "new" to create Point objects
let p = new Point(1, 1); // The geometric point (1,1).
// Now use a method of the Point object p
p.distance() // => Math.SQRT2
</pre>

<p>This introductory tour of JavaScript’s fundamental syntax and capabilities ends here,
but the book continues with self-contained chapters that cover additional features of
the language:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>1.4 Example: Character Frequency Histograms</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This chapter concludes with a short but nontrivial JavaScript program. Example 1-1 is a Node 
program that reads text from standard input, computes a character frequency histogram from that 
text, and then prints out the histogram. You could invoke the program like this to analyze the 
character frequency of its own source code:</p>

<pre>
$ node charfreq.js < charfreq.js
T: ########### 11.22%
E: ########## 10.15%
R: ####### 6.68%
S: ###### 6.44%
A: ###### 6.16%
N: ###### 5.81%
O: ##### 5.45%
I: ##### 4.54%
H: #### 4.07%
C: ### 3.36%
L: ### 3.20%
U: ### 3.08%
/: ### 2.88%
</pre>

<p>This example uses a number of advanced JavaScript features and is intended to demonstrate what 
real-world JavaScript programs can look like. You should not expect to understand all of the code 
yet, but be assured that all of it will be explained in the chapters that follow.</p>

<p><i>Example 1-1. Computing character frequency histograms with JavaScript</i></p>

<pre>
/**
* This Node program reads text from standard input, computes the frequency
* of each letter in that text, and displays a histogram of the most
* frequently used characters. It requires Node 12 or higher to run.
*
* In a Unix-type environment you can invoke the program like this:
* node charfreq.js < corpus.txt
*/
// This class extends Map so that the get() method returns the specified
// value instead of null when the key is not in the map
class DefaultMap extends Map {
  constructor(defaultValue) {
    super(); // Invoke superclass constructor
    this.defaultValue = defaultValue; // Remember the default value
  }
  get(key) {
    if (this.has(key)) { // If the key is already in the map
      return super.get(key); // return its value from superclass.
    }
    else {
      return this.defaultValue; // Otherwise return the default value
    }
  }
}
// This class computes and displays letter frequency histograms
class Histogram {
  constructor() {
    this.letterCounts = new DefaultMap(0); // Map from letters to counts
    this.totalLetters = 0; // How many letters in all
  }
  // This function updates the histogram with the letters of text.
  add(text) {
    // Remove whitespace from the text, and convert to upper case
    text = text.replace(/\s/g, "").toUpperCase();
    // Now loop through the characters of the text
    for(let character of text) {
      let count = this.letterCounts.get(character); // Get old count
      this.letterCounts.set(character, count+1); // Increment it
      this.totalLetters++;
    }
  }
  // Convert the histogram to a string that displays an ASCII graphic
  toString() {
    // Convert the Map to an array of [key,value] arrays
    let entries = [...this.letterCounts];
    // Sort the array by count, then alphabetically
    entries.sort((a,b) => { // A function to define sort order.
      if (a[1] === b[1]) { // If the counts are the same
        return a[0] < b[0] ? -1 : 1; // sort alphabetically.
      } else { // If the counts differ
        return b[1] - a[1]; // sort by largest count.
      }
    });
    // Convert the counts to percentages
    for(let entry of entries) {
      entry[1] = entry[1] / this.totalLetters*100;
    }
    // Drop any entries less than 1%
    entries = entries.filter(entry => entry[1] >= 1);
    // Now convert each entry to a line of text
    let lines = entries.map (
      ([l,n]) => `${l}: ${"#".repeat(Math.round(n))} ${n.toFixed(2)}%`
    );
    // And return the concatenated lines, separated by newline characters.
    return lines.join("\n");
  }
}
// This async (Promise-returning) function creates a Histogram object,
// asynchronously reads chunks of text from standard input, and adds those chunks to
// the histogram. When it reaches the end of the stream, it returns this histogram
async function histogramFromStdin() {
  process.stdin.setEncoding("utf-8"); // Read Unicode strings, not bytes
  let histogram = new Histogram();
  for await (let chunk of process.stdin) {
    histogram.add(chunk);
  }
  return histogram;
}
// This one final line of code is the main body of the program.
// It makes a Histogram object from standard input, then prints the histogram.
histogramFromStdin().then(histogram => { console.log(histogram.toString()); });
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>1.5 Summary</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This book explains JavaScript from the bottom up. This means that we start with low-level details 
like comments, identifiers, variables, and types; then build to expressions, statements, objects, and 
functions; and then cover high-level language abstractions like classes and modules. I take the word 
definitive in the title of this book seriously, and the coming chapters explain the language at a level 
of detail that may feel off-putting at first. True mastery of JavaScript requires an understanding of 
the details, however, and I hope that you will make time to read this book cover to cover. But please 
don’t feel that you need to do that on your first reading. If you find yourself feeling bogged down in 
a section, simply skip to the next. You can come back and master the details once you have a working 
knowledge of the language as a whole.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>Chapter 2: Lexical Structure</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The lexical structure of a programming language is the set of elementary rules that specifies 
how you write programs in that language. It is the lowest-level syntax of a language: it specifies 
what variable names look like, the delimiter characters for comments, and how one program statement 
is separated from the next, for example. This short chapter documents the lexical structure of 
JavaScript. It covers: • Case sensitivity, spaces, and line breaks.</p>
<ul>
  <li>• Comments</li>
  <li>• Literals</li>
  <li>• Identifiers and reserved words</li>
  <li>• Unicode</li>
  <li>• Optional semicolons</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>2.1 The Text of a JavaScript Program</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>JavaScript is a case-sensitive language. This means that language keywords, variables,
function names, and other identifiers must always be typed with a consistent capitalization 
of letters. The while keyword, for example, must be typed “while,” not “While”
or “WHILE.” Similarly, online, Online, OnLine, and ONLINE are four distinct variable
names.</p>

<p>JavaScript ignores spaces that appear between tokens in programs. For the most part,
JavaScript also ignores line breaks (but see §2.6 for an exception). Because you can
use spaces and newlines freely in your programs, you can format and indent your
programs in a neat and consistent way that makes the code easy to read and understand.</p>

<p>In addition to the regular space character (\u0020), JavaScript also recognizes tabs,
assorted ASCII control characters, and various Unicode space characters as white‐
space. JavaScript recognizes newlines, carriage returns, and a carriage return/line feed
sequence as line terminators.</p>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>2.2 Comments</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>JavaScript supports two styles of comments. Any text between a // and the end of a
line is treated as a comment and is ignored by JavaScript. Any text between the characters 
/* and */ is also treated as a comment; these comments may span multiple
lines but may not be nested. The following lines of code are all legal JavaScript
comments:</p>

<pre>
// This is a single-line comment.
/* This is also a comment */ // and here is another comment.
/*
* This is a multi-line comment. The extra * characters at the start of
* each line are not a required part of the syntax; they just look cool!
*/
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>2.3 Literals</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>A literal is a data value that appears directly in a program. The following are all literals:</p>

<pre>
12 // The number twelve
1.2 // The number one point two
"hello world" // A string of text
'Hi' // Another string
true // A Boolean value
false // The other Boolean value
null // Absence of an object
</pre>

<p>Complete details on numeric and string literals appear in Chapter 3.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>2.4 Identifiers and Reserved Words</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>An identifier is simply a name. In JavaScript, identifiers are used to name constants,
variables, properties, functions, and classes and to provide labels for certain loops in
JavaScript code. A JavaScript identifier must begin with a letter, an underscore (_), or
a dollar sign ($). Subsequent characters can be letters, digits, underscores, or dollar
signs. (Digits are not allowed as the first character so that JavaScript can easily distin‐
guish identifiers from numbers.) These are all legal identifiers:</p>

<pre>
i
my_variable_name
v13
_dummy
$str
</pre>

<p>Like any language, JavaScript reserves certain identifiers for use by the language itself.
These “reserved words” cannot be used as regular identifiers. They are listed in the
next section.</p>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>2.4.1 Reserved Words</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The following words are part of the JavaScript language. Many of these (such as if,
while, and for) are reserved keywords that must not be used as the names of constants, 
variables, functions, or classes (though they can all be used as the names of
properties within an object). Others (such as from, of, get, and set) are used in limited 
contexts with no syntactic ambiguity and are perfectly legal as identifiers. Still
other keywords (such as let) can’t be fully reserved in order to retain backward compatibility 
with older programs, and so there are complex rules that govern when they
can be used as identifiers and when they cannot. (let can be used as a variable name
if declared with var outside of a class, for example, but not if declared inside a class or
with const.) The simplest course is to avoid using any of these words as identifiers,
except for from, set, and target, which are safe to use and are already in common
use.</p>

<dl>
  <dt>as const export get null target void</dt>
  <dt>async continue extends if of this while</dt>
  <dt>await debugger false import return throw with</dt>
  <dt>break default finally in set true yield</dt>
  <dt>case delete for instanceof static try</dt>
  <dt>catch do from let super typeof</dt>
  <dt>class else function new switch var</dt>
</dl>

<p>JavaScript also reserves or restricts the use of certain keywords that are not currently
used by the language but that might be used in future versions:
enum implements interface package private protected public
For historical reasons, arguments and eval are not allowed as identifiers in certain
circumstances and are best avoided entirely.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>2.5 Unicode</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>JavaScript programs are written using the Unicode character set, and you can use any
Unicode characters in strings and comments. For portability and ease of editing, it is
common to use only ASCII letters and digits in identifiers. But this is a programming
convention only, and the language allows Unicode letters, digits, and ideographs (but
not emojis) in identifiers. This means that programmers can use mathematical symbols 
and words from non-English languages as constants and variables:</p>

<pre>
const π = 3.14;
const sí = true;
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>2.5.1 Unicode Escape Sequences</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Some computer hardware and software cannot display, input, or correctly process the full set 
of Unicode characters. To support programmers and systems using older technology, JavaScript 
defines escape sequences that allow us to write Unicode characters using only ASCII characters. 
These Unicode escapes begin with the characters \u and are either followed by exactly four 
hexadecimal digits (using uppercase or lowercase letters A–F) or by one to six hexadecimal 
digits enclosed within curly braces. These Unicode escapes may appear in JavaScript string 
literals, regular expression literals, and identifiers (but not in language keywords). The 
Unicode escape for the character “é,” for example, is \u00E9; here are three different ways 
to write a variable name that includes this character:</p>

<pre>
let café = 1; // Define a variable using a Unicode character
caf\u00e9 // => 1; access the variable using an escape sequence
caf\u{E9} // => 1; another form of the same escape sequence
</pre>

<p>Early versions of JavaScript only supported the four-digit escape sequence. The version with 
curly braces was introduced in ES6 to better support Unicode codepoints that require more than 
16 bits, such as emoji:</p>

<pre>console.log("\u{1F600}"); // Prints a smiley face emoji</pre>

<p>Unicode escapes may also appear in comments, but since comments are ignored, they
are simply treated as ASCII characters in that context and not interpreted as Unicode.</p>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>2.5.2 Unicode Normalization</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>If you use non-ASCII characters in your JavaScript programs, you must be aware that
Unicode allows more than one way of encoding the same character. The string “é,” for
example, can be encoded as the single Unicode character \u00E9 or as a regular
ASCII “e” followed by the acute accent combining mark \u0301. These two encodings
typically look exactly the same when displayed by a text editor, but they have different
binary encodings, meaning that they are considered different by JavaScript, which
can lead to very confusing programs:</p>

<pre>
const café = 1; // This constant is named "caf\u{e9}"
const café = 2; // This constant is different: "cafe\u{301}"
café // => 1: this constant has one value
café // => 2: this indistinguishable constant has a different value
18
|
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>2.6 Optional Semicolons</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Like many programming languages, JavaScript uses the semicolon (;) to separate
statements (see Chapter 5) from one another. This is important for making the mean‐
ing of your code clear: without a separator, the end of one statement might appear to
be the beginning of the next, or vice versa. In JavaScript, you can usually omit the
semicolon between two statements if those statements are written on separate lines.
(You can also omit a semicolon at the end of a program or if the next token in the
program is a closing curly brace: }.) Many JavaScript programmers (and the code in
this book) use semicolons to explicitly mark the ends of statements, even where they
are not required. Another style is to omit semicolons whenever possible, using them
only in the few situations that require them. Whichever style you choose, there are a
few details you should understand about optional semicolons in JavaScript.</p>

<p>Consider the following code. Since the two statements appear on separate lines, the first 
semicolon could be omitted:</p>

<pre>
a = 3;
b = 4;
</pre>

<p>Written as follows, however, the first semicolon is required:</p>

<pre>a = 3; b = 4;</pre>

<p>Note that JavaScript does not treat every line break as a semicolon: it usually treats
line breaks as semicolons only if it can’t parse the code without adding an implicit
semicolon. More formally (and with three exceptions described a bit later), JavaScript
treats a line break as a semicolon if the next nonspace character cannot be interpreted
as a continuation of the current statement. Consider the following code:</p>

<pre>
let a
a
=
3
console.log(a)
</pre>

<p>JavaScript interprets this code like this:</p>

<pre>let a; a = 3; console.log(a);</pre>

<p>JavaScript does treat the first line break as a semicolon because it cannot parse the
code let a a without a semicolon. The second a could stand alone as the statement
a;, but JavaScript does not treat the second line break as a semicolon because it can
continue parsing the longer statement a = 3;.</p>

<p>These statement termination rules lead to some surprising cases. This code looks like
two separate statements separated with a newline:</p>

<pre>
let y = x + f
(a+b).toString()
</pre>

<p>But the parentheses on the second line of code can be interpreted as a function invocation of f 
from the first line, and JavaScript interprets the code like this:</p>

<pre>let y = x + f(a+b).toString();</pre>

<p>More likely than not, this is not the interpretation intended by the author of the code.
In order to work as two separate statements, an explicit semicolon is required in this
case.</p>

<p>In general, if a statement begins with (, [, /, +, or -, there is a chance that it could be
interpreted as a continuation of the statement before. Statements beginning with /, +,
and - are quite rare in practice, but statements beginning with ( and [ are not
uncommon at all, at least in some styles of JavaScript programming. Some program‐
mers like to put a defensive semicolon at the beginning of any such statement so that
it will continue to work correctly even if the statement before it is modified and a pre‐
viously terminating semicolon removed:</p>

<pre>
let x = 0 // Semicolon omitted here
;[x,x+1,x+2].forEach(console.log) // Defensive ; keeps this statement separate
</pre>

<p>There are three exceptions to the general rule that JavaScript interprets line breaks as
semicolons when it cannot parse the second line as a continuation of the statement
on the first line. The first exception involves the return, throw, yield, break, and
continue statements (see Chapter 5). These statements often stand alone, but they are
sometimes followed by an identifier or expression. If a line break appears after any of
these words (before any other tokens), JavaScript will always interpret that line break
as a semicolon. For example, if you write:</p>

<pre>
return
true;
</pre>

<p>JavaScript assumes you meant:</p>

<pre>return; true;</pre>

<p>However, you probably meant:</p>

<pre>return true;</pre>

<p>This means that you must not insert a line break between return, break, or continue
and the expression that follows the keyword. If you do insert a line break, your code
is likely to fail in a nonobvious way that is difficult to debug.</p>

<p>The second exception involves the ++ and −− operators (§4.8). These operators can be
prefix operators that appear before an expression or postfix operators that appear
after an expression. If you want to use either of these operators as postfix operators,
they must appear on the same line as the expression they apply to. The third excep‐
tion involves functions defined using concise “arrow” syntax: the => arrow itself must
appear on the same line as the parameter list.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>2.7 Summary</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This chapter has shown how JavaScript programs are written at the lowest level. The next chapter 
takes us one step higher and introduces the primitive types and values (numbers, strings, and so 
on) that serve as the basic units of computation for JavaScript programs.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>CHAPTER 3 Types, Values, and Variables</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Computer programs work by manipulating values, such as the number 3.14 or the text “Hello World.” 
The kinds of values that can be represented and manipulated in a programming language are known as 
types, and one of the most fundamental characteristics of a programming language is the set of types 
it supports. When a program needs to retain a value for future use, it assigns the value to (or 
“stores” the value in) a variable. Variables have names, and they allow use of those names in our 
programs to refer to values. The way that variables work is another fundamental characteristic of
any programming language. This chapter explains types, values, and variables in JavaScript. It 
begins with an overview and some definitions.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>3.1 Overview and Definitions</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>JavaScript types can be divided into two categories: primitive types and object types.
JavaScript’s primitive types include numbers, strings of text (known as strings), and
Boolean truth values (known as booleans). A significant portion of this chapter is
dedicated to a detailed explanation of the numeric (§3.2) and string (§3.3) types in
JavaScript. Booleans are covered in §3.4.</p>

<p>The special JavaScript values null and undefined are primitive values, but they are
not numbers, strings, or booleans. Each value is typically considered to be the sole
member of its own special type. §3.5 has more about null and undefined. ES6 adds a
new special-purpose type, known as Symbol, that enables the definition of language
extensions without harming backward compatibility. Symbols are covered briefly in
§3.6.</p>

<p>Any JavaScript value that is not a number, a string, a boolean, a symbol, null, or unde
fined is an object. An object (that is, a member of the type object) is a collection of
properties where each property has a name and a value (either a primitive value or
another object). One very special object, the global object, is covered in §3.7, but more
general and more detailed coverage of objects is in Chapter 6.</p>

<p>An ordinary JavaScript object is an unordered collection of named values. The lan‐
guage also defines a special kind of object, known as an array, that represents an
ordered collection of numbered values. The JavaScript language includes special syn‐
tax for working with arrays, and arrays have some special behavior that distinguishes
them from ordinary objects. Arrays are the subject of Chapter 7.

<p>In addition to basic objects and arrays, JavaScript defines a number of other useful
object types. A Set object represents a set of values. A Map object represents a mapping 
from keys to values. Various “typed array” types facilitate operations on arrays of
bytes and other binary data. The RegExp type represents textual patterns and enables
sophisticated matching, searching, and replacing operations on strings. The Date type
represents dates and times and supports rudimentary date arithmetic. Error and its
subtypes represent errors that can arise when executing JavaScript code. All of these
types are covered in Chapter 11.</p>

<p>JavaScript differs from more static languages in that functions and classes are not just
part of the language syntax: they are themselves values that can be manipulated by
JavaScript programs. Like any JavaScript value that is not a primitive value, functions
and classes are a specialized kind of object. They are covered in detail in Chapters 8
and 9.</p>

<p>The JavaScript interpreter performs automatic garbage collection for memory management. This means 
that a JavaScript programmer generally does not need to worry about destruction or deallocation of 
objects or other values. When a value is no longer reachable—when a program no longer has any way 
to refer to it—the interpreter knows it can never be used again and automatically reclaims the memory 
it was occupying. (JavaScript programmers do sometimes need to take care to ensure that values do not 
inadvertently remain reachable—and therefore nonreclaimable—longer than necessary.)</p>

<p>JavaScript supports an object-oriented programming style. Loosely, this means that
rather than having globally defined functions to operate on values of various types,
the types themselves define methods for working with values. To sort the elements of
an array a, for example, we don’t pass a to a sort() function. Instead, we invoke the
sort() method of a:</p>

<pre>a.sort(); // The object-oriented version of sort(a).</pre>

<p>Method definition is covered in Chapter 9. Technically, it is only JavaScript objects
that have methods. But numbers, strings, boolean, and symbol values behave as if
they have methods. In JavaScript, null and undefined are the only values that methods cannot be invoked on.</p>

<p>This is the format for numbers of type double in Java, C++, and most modern programming languages.
JavaScript’s object types are mutable and its primitive types are immutable. A value of a mutable type 
can change: a JavaScript program can change the values of object properties and array elements. Numbers, 
booleans, symbols, null, and undefined are immutable—it doesn’t even make sense to talk about changing 
the value of a number, for example. Strings can be thought of as arrays of characters, and you might 
expect them to be mutable. In JavaScript, however, strings are immutable: you can access the text at 
any index of a string, but JavaScript provides no way to alter the text of an existing string. The 
differences between mutable and immutable values are explored further in §3.8.</p>

<p>JavaScript liberally converts values from one type to another. If a program expects a string, for 
example, and you give it a number, it will automatically convert the number to a string for you. And 
if you use a non-boolean value where a boolean is expected, JavaScript will convert accordingly. The 
rules for value conversion are explained in §3.9. JavaScript’s liberal value conversion rules affect 
its definition of equality, and the == equality operator performs type conversions as described in
§3.9.1. (In practice, however, the == equality operator is deprecated in favor of the strict equality 
operator ===, which does no type conversions. See §4.9.1 for more about both operators.)</p>

<p>Constants and variables allow you to use names to refer to values in your programs. Constants are 
declared with const and variables are declared with let (or with var in older JavaScript code). 
JavaScript constants and variables are untyped: declarations do not specify what kind of values will 
be assigned. Variable declaration and assignment are covered in §3.10.</p>

<p>As you can see from this long introduction, this is a wide-ranging chapter that explains many 
fundamental details about how data is represented and manipulated in JavaScript. We’ll begin by 
diving right in to the details of JavaScript numbers and text.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>3.2 Numbers</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>JavaScript’s primary numeric type, Number, is used to represent integers and to approximate 
real numbers. JavaScript represents numbers using the 64-bit floating-point format defined by 
the IEEE 754 standard,1 which means it can represent numbers as large as ±1.7976931348623157 × 
10308 and as small as ±5 × 10−324.</p>

<p>The JavaScript number format allows you to exactly represent all integers between 
−9,007,199,254,740,992 (−253) and 9,007,199,254,740,992 (253), inclusive. If you use integer 
values larger than this, you may lose precision in the trailing digits. Note, however, that 
certain operations in JavaScript (such as array indexing and the bitwise operators described 
in Chapter 4) are performed with 32-bit integers.</p>

<p>When a number appears directly in a JavaScript program, it’s called a numeric literal. JavaScript 
supports numeric literals in several formats, as described in the following sections. Note that any 
numeric literal can be preceded by a minus sign (-) to make the number negative.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>3.2.1 Integer Literals</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>In a JavaScript program, a base-10 integer is written as a sequence of digits. For example:</p>

<pre>
30
10000000
</pre>

<p>In addition to base-10 integer literals, JavaScript recognizes hexadecimal (base-16) values. A 
hexadecimal literal begins with 0x or 0X, followed by a string of hexadecimal digits. A hexadecimal 
digit is one of the digits 0 through 9 or the letters a (or A) through f (or F), which represent 
values 10 through 15. Here are examples of hexadecimal integer literals:</p>

<pre>
0xff // => 255: (15*16 + 15)
0xBADCAFE // => 195939070
In ES6 and later, you can also express integers in binary (base 2) or octal (base 8)
using the prefixes 0b and 0o (or 0B and 0O) instead of 0x:
0b10101 // => 21: (1*16 + 0*8 + 1*4 + 0*2 + 1*1)
0o377 // => 255: (3*64 + 7*8 + 7*1)
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>3.2.2 Floating-Point Literals</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Floating-point literals can have a decimal point; they use the traditional syntax for real 
numbers. A real value is represented as the integral part of the number, followed by a decimal 
point and the fractional part of the number.</p>

<p>Floating-point literals may also be represented using exponential notation: a real number 
followed by the letter e (or E), followed by an optional plus or minus sign, followed by an 
integer exponent. This notation represents the real number multiplied by 10 to the power of 
the exponent. More succinctly, the syntax is:</p>

<pre>[digits][.digits][(E|e)[(+|-)]digits]</pre>

<p>For example:</p>

<pre>
3.14
2345.6789
.333333333333333333
6.02e23 // 6.02 × 10²³
1.4738223E-32 // 1.4738223 × 10⁻³²
Separators in Numeric Literals
You can use underscores within numeric literals to break long literals up into chunks
that are easier to read:
let billion = 1_000_000_000; // Underscore as a thousands separator.
let bytes = 0x89_AB_CD_EF; // As a bytes separator.
let bits = 0b0001_1101_0111; // As a nibble separator.
let fraction = 0.123_456_789; // Works in the fractional part, too.
</pre>

<p>At the time of this writing in early 2020, underscores in numeric literals are not yet formally 
standardized as part of JavaScript. But they are in the advanced stages of the standardization 
process and are implemented by all major browsers and by Node.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch3-2-3">3.2.3 Arithmetic in JavaScript</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>JavaScript programs work with numbers using the arithmetic operators. That the language provides. 
These include + for addition, - for subtraction, &ast; for multiplication, / for division, and % 
for modulo (remainder after division). ES2016 adds &ast;&ast; for exponentiation.</p>

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
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>ES6 defines more functions on the Math object:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
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
<h4>Working with Strings</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>let s = "Hello, world"; // Start with some text.</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>// Obtaining portions of a string</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
s.substring(1,4) // =&gt; "ell": the 2nd, 3rd, and 4th characters.
s.slice(1,4) // =&gt; "ell": same thing.
s.slice(-3) // =&gt; "rld": last 3 characters.
s.split(", ") // =&gt; ["Hello", "world"]: split at delimiter string.
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>// Searching a string</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
s.indexOf("l") // =&gt; 2: position of first letter l.
s.indexOf("l", 3) // =&gt; 3: position of first "l" at or after 3.
s.indexOf("zz") // =&gt; -1: s does not include the substring "zz".
s.lastIndexOf("l") // =&gt; 10: position of last letter l.
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>// Boolean searching functions in ES6 and later</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
s.startsWith("Hell") // =&gt; true: the string starts with these
s.endsWith("!") // =&gt; false: s does not end with that
s.includes("or") // =&gt; true: s includes substring "or"
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>// Creating modified versions of a string</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
s.replace("llo", "ya") // =&gt; "Heya, world".
s.toLowerCase() // =&gt; "hello, world".
s.toUpperCase() // =&gt; "HELLO, WORLD".
s.normalize() // Unicode NFC normalization: ES6.
s.normalize("NFD") // NFD normalization. Also "NFKC", "NFKD".
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>// Inspecting individual (16-bit) characters of a string</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
s.charAt(0) // =&gt; "H": the first character.
s.charAt(s.length-1) // =&gt; "d": the last character.
s.charCodeAt(0) // =&gt; 72: 16-bit number at the specified position.
s.codePointAt(0) // =&gt; 72: ES6, works for codepoints > 16 bits.
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>// String padding functions in ES2017</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
"x".padStart(3) // =&gt; " x": add spaces on the left to a length of 3.
"x".padEnd(3) // =&gt; "x ": add spaces on the right to a length of 3.
"x".padStart(3, "&ast;") // =&gt; "&ast;&ast;x": add stars on the left to a length of 3.
"x".padEnd(3, "-") // =&gt; "x--": add dashes on the right to a length of 3.
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>// Space trimming functions. trim() is ES5; others ES2019</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
" test ".trim() // =&gt; "test": remove spaces at start and end.
" test ".trimStart() // =&gt; "test ": remove spaces on left. Also trimLeft.
" test ".trimEnd() // =&gt; " test": remove spaces at right. Also trimRight.
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>// Miscellaneous string methods</h4>
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
<h3 id="ch3-3-5">3.3.5 Pattern Matching</h3>
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
<h3 id="ch3-6">3.6 Symbols</h3>
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
<h3 id="ch3-9">3.9 Type Conversions</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>JavaScript is very flexible about the types of values it requires. We’ve seen this for booleans: 
when JavaScript expects a boolean value, you may supply a value of any type, and JavaScript will 
convert it as needed. Some values (“truthy” values) convert to true and others (“falsy” values) 
convert to false. The same is true for other types: if JavaScript wants a string, it will convert 
whatever value you give it to a string. If JavaScript wants a number, it will try to convert the 
value you give it to a number (or to NaN if it cannot perform a meaningful conversion).</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Some examples:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
10 + " objects" // =&gt; "10 objects": Number 10 converts to a string.
"7" * "4" // =&gt; 28: both strings convert to numbers.
let n = 1 - "x"; // n == NaN; string "x" can't convert to a number.
n + " objects" // =&gt; "NaN objects": NaN converts to string "NaN".
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Conversions and Equality</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
null == undefined // =&gt; true: These two values are treated as equal.
"0" == 0 // =&gt; true: String converts to a number before comparing.
0 == false // =&gt; true: Boolean converts to number before comparing.
"0" == false // =&gt; true: Both operands convert to 0 before comparing!
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch3-10-1">3.10.1 Declarations with let and const</h3>
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
<h3 id="ch4-4">4.4 Property Access Expressions</h3>
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
<h4>Here are some concrete examples:</h4>
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
<h4>Here are some examples:</h4>
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
<h3 id="ch4-8-1">4.8.1 The + Operator</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The binary + operator adds numeric operands or concatenates string operands:</p>

<pre>
1 + 2 // =&gt; 3.
"hello" + " " + "there" // =&gt; "hello there".
"1" + "2" // =&gt; "12".
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>For example:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
1 + 2 + " blind mice" // =&gt; "3 blind mice".
1 + (2 + " blind mice") // =&gt; "12 blind mice".
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>The =, ==, and === operators</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>JavaScript supports =, ==, and === operators. Be sure you understand the differences between 
these assignment, equality, and strict equality operators, and be careful to use the correct one 
when coding! Although it is tempting to read all three operators as “equals,” it may help to 
reduce confusion if you read “gets” or “is assigned” for =, “is equal to” for ==, and “is 
strictly equal to” for ===.</p>

<p>The == operator is a legacy feature of JavaScript and is widely considered to be a source of 
bugs. You should almost always use === instead of ==, and !== instead of !=.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Strict equality</h4>
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
<h4>Equality with type conversion</h4>
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
<h3 id="ch4-9-3">4.9.3 The in Operator</h3>
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
<h3 id="ch4-9-4">4.9.4 The instanceof Operator</h3>
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
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Values returned by the typeof operator</h4>
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
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Chapter 1. Introduction to JavaScript</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
JavaScript is the programming language of the web. The overwhelming majority of websites use 
JavaScript, and all modern web browsers—on desktops, tablets, and phones—include JavaScript 
interpreters, making JavaScript the most-deployed programming language in history. Over the 
last decade, Node.js has enabled JavaScript programming outside of web browsers, and the 
dramatic success of Node means that JavaScript is now also the most-used programming language 
among software developers. Whether you’re starting from scratch or are already using JavaScript 
professionally, this book will help you master the language.

If you are already familiar with other programming languages, it may help you to know that 
JavaScript is a high-level, dynamic, interpreted programming language that is well-suited to 
object-oriented and functional programming styles. JavaScript’s variables are untyped. Its 
syntax is loosely based on Java, but the languages are otherwise unrelated. JavaScript derives 
its first-class functions from Scheme and its prototype-based inheritance from the little-known 
language Self. But you do not need to know any of those languages, or be familiar with those terms, 
to use this book and learn JavaScript.

The name “JavaScript” is quite misleading. Except for a superficial syntactic resemblance, JavaScript 
is completely different from the Java programming language. And JavaScript has long since outgrown 
its scripting-language roots to become a ...

<!-- chapter 2 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Chapter 2. Lexical Structure</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
The lexical structure of a programming language is the set of elementary rules that specifies how 
you write programs in that language. It is the lowest-level syntax of a language: it specifies 
what variable names look like, the delimiter characters for comments, and how one program statement 
is separated from the next, for example. This short chapter documents the lexical structure of 
JavaScript. It covers:

    Case sensitivity, spaces, and line breaks

    Comments

    Literals

    Identifiers and reserved words

    Unicode

    Optional semicolons

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
2.1 The Text of a JavaScript Program
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
JavaScript is a case-sensitive language. This means that language keywords, variables, function 
names, and other identifiers must always be typed with a consistent capitalization of letters. 
The while keyword, for example, must be typed “while,” not “While” or “WHILE.” Similarly, online, 
Online, OnLine, and ONLINE are four distinct variable names.

JavaScript ignores spaces that appear between tokens in programs. For the most part, JavaScript 
also ignores line breaks (but see §2.6 for an exception). Because you can use spaces and newlines 
freely in your programs, you can format and indent your programs in a neat and consistent way that 
makes the code easy to read and understand.

In addition to the regular space character (\u0020), JavaScript also recognizes tabs, assorted ASCII 
control characters, and various Unicode space characters as whitespace. JavaScript recognizes newlines, ...
<!-- chapter 3 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Chapter 3. Types, Values, and Variables
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Computer programs work by manipulating values, such as the number 3.14 or the text “Hello World.” The 
kinds of values that can be represented and manipulated in a programming language are known as types, 
and one of the most fundamental characteristics of a programming language is the set of types it 
supports. When a program needs to retain a value for future use, it assigns the value to (or “stores” 
the value in) a variable. Variables have names, and they allow use of those names in our programs to 
refer to values. The way that variables work is another fundamental characteristic of any programming 
language. This chapter explains types, values, and variables in JavaScript. It begins with an overview 
and some definitions.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
3.1 Overview and Definitions
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
JavaScript types can be divided into two categories: primitive types and object types. JavaScript’s 
primitive types include numbers, strings of text (known as strings), and Boolean truth values (known 
as booleans). A significant portion of this chapter is dedicated to a detailed explanation of the numeric 
(§3.2) and string (§3.3) types in JavaScript. Booleans are covered in §3.4.

The special JavaScript values null and undefined are primitive values, but they are not numbers, strings, 
or booleans. Each value is typically considered to be the sole member of its own special type. §3.5 has 
more about null and undefined. ES6 adds a new special-purpose type, known as Symbol, that enables the 
definition ...
<!-- chapter 4 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Chapter 4. Expressions and Operators
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
This chapter documents JavaScript expressions and the operators with which many of those expressions 
are built. An expression is a phrase of JavaScript that can be evaluated to produce a value. A 
constant embedded literally in your program is a very simple kind of expression. A variable name is 
also a simple expression that evaluates to whatever value has been assigned to that variable. Complex 
expressions are built from simpler expressions. An array access expression, for example, consists of 
one expression that evaluates to an array followed by an open square bracket, an expression that 
evaluates to an integer, and a close square bracket. This new, more complex expression evaluates to 
the value stored at the specified index of the specified array. Similarly, a function invocation 
expression consists of one expression that evaluates to a function object and zero or more additional 
expressions that are used as the arguments to the function.

The most common way to build a complex expression out of simpler expressions is with an operator. An 
operator combines the values of its operands (usually two of them) in some way and evaluates to a new 
value. The multiplication operator * is a simple example. The expression x * y evaluates to the product 
of the values of the expressions x and y. For simplicity, we sometimes say that an operator returns a 
value rather than “evaluates to” a value.

This chapter documents all of JavaScript’s operators, and ...
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>4.13 Miscellaneous Operators</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>JavaScript supports a number of other miscellaneous operators, described in the following sections.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>4.13.1 The Conditional Operator (?:)</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The conditional operator is the only ternary operator (three operands) in JavaScript and is 
sometimes actually called the ternary operator. This operator is sometimes written ?:, although 
it does not appear quite that way in code. Because this operator has three operands, the first 
goes before the ?, the second goes between the ? and the :, and the third goes after the :. 
It is used like this:</p>

<pre>x > 0 ? x : -x // The absolute value of x</pre>

<p>The operands of the conditional operator may be of any type. The first operand is
evaluated and interpreted as a boolean. If the value of the first operand is truthy, then
the second operand is evaluated, and its value is returned. Otherwise, if the first
operand is falsy, then the third operand is evaluated and its value is returned. Only
one of the second and third operands is evaluated; never both.</p>

<p>While you can achieve similar results using the if statement (§5.3.1), the ?: operator
often provides a handy shortcut. Here is a typical usage, which checks to be sure that
a variable is defined (and has a meaningful, truthy value) and uses it if so or provides
a default value if not:</p>

<pre>greeting = "hello " + (username ? username : "there");</pre>

<p>This is equivalent to, but more compact than, the following if statement:</p>

<pre>
greeting = "hello ";
if (username) {
  greeting += username;
} else {
  greeting += "there";
}
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>4.13.2 First-Defined (??)</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The first-defined operator ?? evaluates to its first defined operand: if its left operand
is not null and not undefined, it returns that value. Otherwise, it returns the value of
the right operand. Like the && and || operators, ?? is short-circuiting: it only evaluates its 
second operand if the first operand evaluates to null or undefined. If the expression a has no 
side effects, then the expression a ?? b is equivalent to:</p>

<pre>(a !== null && a !== undefined) ? a : b</pre>

<p>?? is a useful alternative to || (§4.10.2) when you want to select the first defined
operand rather than the first truthy operand. Although || is nominally a logical OR
operator, it is also used idiomatically to select the first non-falsy operand with code
like this:</p>

<pre>
// If maxWidth is truthy, use that. Otherwise, look for a value in
// the preferences object. If that is not truthy, use a hardcoded constant.
let max = maxWidth || preferences.maxWidth || 500;
</pre>

<p>The problem with this idiomatic use is that zero, the empty string, and false are all
falsy values that may be perfectly valid in some circumstances. In this code example,
if maxWidth is zero, that value will be ignored. But if we change the || operator to ??,
we end up with an expression where zero is a valid value:</p>

<pre>
// If maxWidth is defined, use that. Otherwise, look for a value in
// the preferences object. If that is not defined, use a hardcoded constant.
let max = maxWidth ?? preferences.maxWidth ?? 500;
</pre>

<p>Here are more examples showing how ?? works when the first operand is falsy. If that operand is 
falsy but defined, then ?? returns it. It is only when the first operand is “nullish” (i.e., null 
or undefined) that this operator evaluates and returns the second operand:</p>

<pre>
let options = { timeout: 0, title: "", verbose: false, n: null };
options.timeout ?? 1000 // => 0: as defined in the object
options.title ?? "Untitled" // => "": as defined in the object
options.verbose ?? true // => false: as defined in the object
options.quiet ?? false // => false: property is not defined
options.n ?? 10 // => 10: property is null
</pre>

<p>Note that the timeout, title, and verbose expressions here would have different values if we 
used || instead of ??.</p>

<p>The ?? operator is similar to the && and || operators but does not have higher precedence 
or lower precedence than they do. If you use it in an expression with either of those operators, 
you must use explicit parentheses to specify which operation you want to perform first:</p>

<pre>
(a ?? b) || c // ?? first, then ||
a ?? (b || c) // || first, then ??
a ?? b || c // SyntaxError: parentheses are required
</pre>

<p>The ?? operator is defined by ES2020, and as of early 2020, is newly supported by
current or beta versions of all major browsers. This operator is formally called the
“nullish coalescing” operator, but I avoid that term because this operator selects one
of its operands but does not “coalesce” them in any way that I can see.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>4.13.3 The typeof Operator</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>typeof is a unary operator that is placed before its single operand, which can be of
any type. Its value is a string that specifies the type of the operand. Table 4-3 specifies
the value of the typeof operator for any JavaScript value.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Table 4-3. Values returned by the typeof operator</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<table>
<table border="1">
  <tr>
    <th>x</th>
    <th>typeof x</th>
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
    <td>any number of NaN</td>
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
    <td>any nonfunctoin object</td>
    <td>"object"</td>
  </tr>
</table>

<p>You might use the typeof operator in an expression like this:</p>

<pre>
// If the value is a string, wrap it in quotes, otherwise, convert
(typeof value === "string") ? "'" + value + "'" : value.toString()
</pre>

<p>Note that typeof returns “object” if the operand value is null. If you want to distinguish null 
from objects, you’ll have to explicitly test for this special value.</p>

<p>Although JavaScript functions are a kind of object, the typeof operator considers functions to be 
sufficiently different that they have their own return value.</p>

<p>Because typeof evaluates to “object” for all object and array values other than functions, it is 
useful only to distinguish objects from other, primitive types. In order to distinguish one class of 
object from another, you must use other techniques, such as the instanceof operator (see §4.9.4), 
the class attribute (see §14.4.3), or the constructor property (see §9.2.2 and §14.3).</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>4.13.4 The delete Operator</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p><b>delete</b> is a unary operator that attempts to delete the object property or array element 
specified as its operand. Like the assignment, increment, and decrement operators, delete is 
typically used for its property deletion side effect and not for the value it returns. 
Some examples:</p>

<pre>
let o = { x: 1, y: 2}; // Start with an object
delete o.x; // Delete one of its properties
"x" in o // => false: the property does not exist anymore
let a = [1,2,3]; // Start with an array
delete a[2]; // Delete the last element of the array
2 in a // => false: array element 2 doesn't exist anymore
a.length // => 3: note that array length doesn't change, though
</pre>

<p>Note that a deleted property or array element is not merely set to the undefined value. When a 
property is deleted, the property ceases to exist. Attempting to read a nonexistent property returns 
undefined, but you can test for the actual existence of a property with the in operator (§4.9.3). 
Deleting an array element leaves a “hole” in the array and does not change the array’s length. The 
resulting array is sparse (§7.3).</p>

<p><b>delete</b> expects its operand to be an lvalue. If it is not an lvalue, the operator takes no
action and returns true. Otherwise, 
<b>delete</b> attempts to delete the specified lvalue. <b>delete</b> 
returns true if it successfully deletes the specified lvalue. Not all properties can be deleted, 
however: non-configurable properties (§14.1) are immune from deletion.</p>

<p>In <b>strict mode</b>, <b>delete</b> raises a SyntaxError if its operand is an unqualified 
identifier such as a variable, function, or function parameter: it only works when the operand 
is a property access expression. Strict mode also specifies that delete raises a TypeError if 
asked to delete any non-configurable (i.e., nondeleteable) property. Outside of strict mode, 
no exception occurs in these cases, and delete simply returns false to indicate that the operand 
could not be deleted.</p>

<p>Here are some example uses of the delete operator:</p>

<pre>
let o = {x: 1, y: 2};
delete o.x; // Delete one of the object properties; returns true.
typeof o.x; // Property does not exist; returns "undefined".
delete o.x; // Delete a nonexistent property; returns true.
delete 1; // This makes no sense, but it just returns true.
// Can't delete a variable; returns false, or SyntaxError in strict mode.
delete o;
// Undeletable property: returns false, or TypeError in strict mode.
delete Object.prototype;
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>4.13.5 The await Operator</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p><b>await</b> is a way to make asynchronous programming more natural in JavaScript. You will need 
to read Chapter 13 to understand this operator. Briefly, however, await expects a Promise object 
(representing an asynchronous computation) as its sole operand, and it makes your program behave 
as if it were waiting for the asynchronous computation to complete (but it does this without 
actually blocking, and it does not prevent other asynchronous operations from proceeding at the 
same time). The value of the await operator is the fulfillment value of the Promise object. 
Importantly, await is only legal within functions that have been declared asynchronous with the 
async keyword. Again, see Chapter 13 for full details.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>4.13.6 The void Operator</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p><b>void</b> is a unary operator that appears before its single operand, which may be of any
type. This operator is unusual and infrequently used; it evaluates its operand, then discards the 
value and returns undefined. Since the operand value is discarded, using the void operator makes 
sense only if the operand has side effects.</p>

<p>The <b>void</b> operator is so obscure that it is difficult to come up with a practical example
of its use. One case would be when you want to define a function that returns nothing but also 
uses the arrow function shortcut syntax, where the body of the function is a single expression 
that is evaluated and returned. If you are evaluating the expression solely for its side effects 
and do not want to return its value, then the simplest thing is to use curly braces around the 
function body. But, as an alternative, you could also use the <b>void</b> operator in this 
case:</p>

<pre>
let counter = 0;
const increment = () => void counter++;
increment() // => undefined
counter // => 1
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>4.13.7 The comma Operator (,)</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The comma operator is a binary operator whose operands may be of any type. It evaluates its 
left operand, evaluates its right operand, and then returns the value of the right operand. Thus, 
the following line:</p>

<pre>i=0, j=1, k=2;</pre>

<p>evaluates to 2 and is basically equivalent to:</p>

<pre>i = 0; j = 1; k = 2;</pre>

<p>The lefthand expression is always evaluated, but its value is discarded, which means that it 
only makes sense to use the comma operator when the lefthand expression has side effects. The 
only situation in which the comma operator is commonly used is with a for loop (§5.4.3) that has 
multiple loop variables:</p>

<pre>
// The first comma below is part of the syntax of the let statement
// The second comma is the comma operator: it lets us squeeze 2
// expressions (i++ and j--) into a statement (the for loop) that expects 1.
for(let i=0,j=10; i < j; i++,j--) {
  console.log(i+j);
}
</pre>

<!-- chapter 5 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Chapter 5. Statements
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Chapter 4 described expressions as JavaScript phrases. By that analogy, statements are JavaScript 
sentences or commands. Just as English sentences are terminated and separated from one another with 
periods, JavaScript statements are terminated with semicolons (§2.6). Expressions are evaluated to 
produce a value, but statements are executed to make something happen.

One way to “make something happen” is to evaluate an expression that has side effects. Expressions 
with side effects, such as assignments and function invocations, can stand alone as statements, and 
when used this way are known as expression statements. A similar category of statements are the 
declaration statements that declare new variables and define new functions.

JavaScript programs are nothing more than a sequence of statements to execute. By default, the 
JavaScript interpreter executes these statements one after another in the order they are written. 
Another way to “make something happen” is to alter this default order of execution, and JavaScript 
has a number of statements or control structures that do just this:

Conditionals

    Statements like if and switch that make the JavaScript interpreter execute or skip other 
	statements depending on the value of an expression
Loops

    Statements like while and for that execute other statements repetitively
Jumps

    Statements like break, return, and throw that cause the interpreter to jump to another part of 
	the program

The sections that follow describe ...
<!-- chapter 6 -->

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>Chapter 6. Objects</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Objects are JavaScript’s most fundamental datatype, and you have already seen them many times in 
the chapters that precede this one. Because objects are so important to the JavaScript language, 
it is important that you understand how they work in detail, and this chapter provides that detail. 
It begins with a formal overview of objects, then dives into practical sections about creating 
objects and querying, setting, deleting, testing, and enumerating the properties of objects. These 
property-focused sections are followed by sections that explain how to extend, serialize, and define 
important methods on objects. Finally, the chapter concludes with a long section about new object 
literal syntax in ES6 and more recent versions of the language.
6.1 Introduction to Objects

An object is a composite value: it aggregates multiple values (primitive values or other objects) 
and allows you to store and retrieve those values by name. An object is an unordered collection of 
properties, each of which has a name and a value. Property names are usually strings (although, as 
we’ll see in §6.10.3, property names can also be Symbols), so we can say that objects map strings 
to values. This string-to-value mapping goes by various names—you are probably already familiar 
with the fundamental data structure under the name “hash,” “hashtable,” “dictionary,” or “associative 
array.” An object is more than a simple string-to-value map, however. In addition to maintaining its 
own set of ...
<!-- chapter 7 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>Chapter 7. Arrays</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
This chapter documents arrays, a fundamental datatype in JavaScript and in most other programming 
languages. An array is an ordered collection of values. Each value is called an element, and each 
element has a numeric position in the array, known as its index. JavaScript arrays are untyped: an 
array element may be of any type, and different elements of the same array may be of different types. 
Array elements may even be objects or other arrays, which allows you to create complex data structures, 
such as arrays of objects and arrays of arrays. JavaScript arrays are zero-based and use 32-bit indexes: 
the index of the first element is 0, and the highest possible index is 4294967294 (232−2), for a maximum 
array size of 4,294,967,295 elements. JavaScript arrays are dynamic: they grow or shrink as needed, and 
there is no need to declare a fixed size for the array when you create it or to reallocate it when the 
size changes. JavaScript arrays may be sparse: the elements need not have contiguous indexes, and there 
may be gaps. Every JavaScript array has a length property. For nonsparse arrays, this property specifies 
the number of elements in the array. For sparse arrays, length is larger than the highest index of any 
element.

JavaScript arrays are a specialized form of JavaScript object, and array indexes are really little more 
than property names that happen to be integers. We’ll talk more about the specializations of arrays 
elsewhere in this chapter. Implementations ...
<!-- chapter 8 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>Chapter 8. Functions</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
This chapter covers JavaScript functions. Functions are a fundamental building block for JavaScript 
programs and a common feature in almost all programming languages. You may already be familiar with 
the concept of a function under a name such as subroutine or procedure.

A function is a block of JavaScript code that is defined once but may be executed, or invoked, any 
number of times. JavaScript functions are parameterized: a function definition may include a list of 
identifiers, known as parameters, that work as local variables for the body of the function. Function 
invocations provide values, or arguments, for the function’s parameters. Functions often use their 
argument values to compute a return value that becomes the value of the function-invocation expression. 
In addition to the arguments, each invocation has another value—the invocation context—that is the 
value of the this keyword.

If a function is assigned to a property of an object, it is known as a method of that object. When a 
function is invoked on or through an object, that object is the invocation context or this value for 
the function. Functions designed to initialize a newly created object are called constructors. 
Constructors were described in §6.2 and will be covered again in Chapter 9.

In JavaScript, functions are objects, and they can be manipulated by programs. JavaScript can assign 
functions to variables and pass them to other functions, for example. Since functions are objects, 
you ...
<!-- chapter 9 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>Chapter 9. Classes</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
JavaScript objects were covered in Chapter 6. That chapter treated each object as a unique set of properties, different from every other object. It is often useful, however, to define a class of objects that share certain properties. Members, or instances, of the class have their own properties to hold or define their state, but they also have methods that define their behavior. These methods are defined by the class and shared by all instances. Imagine a class named Complex that represents and performs arithmetic on complex numbers, for example. A Complex instance would have properties to hold the real and imaginary parts (the state) of the complex number. And the Complex class would define methods to perform addition and multiplication (the behavior) of those numbers.

In JavaScript, classes use prototype-based inheritance: if two objects inherit properties (generally function-valued properties, or methods) from the same prototype, then we say that those objects are instances of the same class. That, in a nutshell, is how JavaScript classes work. JavaScript prototypes and inheritance were covered in §6.2.3 and §6.3.2, and you will need to be familiar with the material in those sections to understand this chapter. This chapter covers prototypes in §9.1.

If two objects inherit from the same prototype, this typically (but not necessarily) means that they were created and initialized by the same constructor function or factory function. Constructors have been covered ...
<!-- chapter 10 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>Chapter 10. Modules</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
The goal of modular programming is to allow large programs to be assembled using modules of code from disparate authors and sources and for all of that code to run correctly even in the presence of code that the various module authors did not anticipate. As a practical matter, modularity is mostly about encapsulating or hiding private implementation details and keeping the global namespace tidy so that modules cannot accidentally modify the variables, functions, and classes defined by other modules.

Until recently, JavaScript had no built-in support for modules, and programmers working on large code bases did their best to use the weak modularity available through classes, objects, and closures. Closure-based modularity, with support from code-bundling tools, led to a practical form of modularity based on a require() function, which was adopted by Node. require()-based modules are a fundamental part of the Node programming environment but were never adopted as an official part of the JavaScript language. Instead, ES6 defines modules using import and export keywords. Although import and export have been part of the language for years, they were only implemented by web browsers and Node relatively recently. And, as a practical matter, JavaScript modularity still depends on code-bundling tools.

The sections that follow cover:

    Do-it-yourself modules with classes, objects, and closures

    Node modules using require()

    ES6 modules using export, import, and import() ...
<!-- chapter 11 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>Chapter 11. The JavaScript Standard Library</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
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
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>Chapter 12. Iterators and Generators</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
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
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>Chapter 13. Asynchronous JavaScript</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Some computer programs, such as scientific simulations and machine learning models, are compute-bound: they run continuously, without pause, until they have computed their result. Most real-world computer programs, however, are significantly asynchronous. This means that they often have to stop computing while waiting for data to arrive or for some event to occur. JavaScript programs in a web browser are typically event-driven, meaning that they wait for the user to click or tap before they actually do anything. And JavaScript-based servers typically wait for client requests to arrive over the network before they do anything.

This kind of asynchronous programming is commonplace in JavaScript, and this chapter documents three important language features that help make it easier to work with asynchronous code. Promises, new in ES6, are objects that represent the not-yet-available result of an asynchronous operation. The keywords async and await were introduced in ES2017 and provide new syntax that simplifies asynchronous programming by allowing you to structure your Promise-based code as if it was synchronous. Finally, asynchronous iterators and the for/await loop were introduced in ES2018 and allow you to work with streams of asynchronous events using simple loops that appear synchronous.

Ironically, even though JavaScript provides these powerful features for working with asynchronous code, there are no features of the core language that are
<!-- chapter 14 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>Chapter 14. Metaprogramming</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
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

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>14.1 Property Attributes</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
The properties of a JavaScript object have names and values, of course, but each property also has three associated attributes that specify how that ...
<!-- chapter 15 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>Chapter 15. JavaScript in Web Browsers</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The JavaScript language was created in 1994 with the express purpose of enabling dynamic behavior 
in the documents displayed by web browsers. The language has evolved significantly since then, and 
at the same time, the scope and capabilities of the web platform have grown explosively. Today, 
JavaScript programmers can think of the web as a full-featured platform for application development. 
Web browsers specialize in the display of formatted text and images, but, like native operating 
systems, browsers also provide other services, including graphics, video, audio, networking, 
storage, and threading. JavaScript is the language that enables web applications to use the 
services provided by the web platform, and this chapter demonstrates how you can use the most 
important of these services.</p>

<p>The chapter begins with the web platform’s programming model, explaining how scripts are 
embedded within HTML pages (§15.1) and how JavaScript code is triggered asynchronously by 
events (§15.2). The sections that follow this introductory material document the core JavaScript 
APIs that enable your web applications to:</p>
<ul>
  <li>Control document content (§15.3) and style (§15.4)</li>
  <li>Determine the on-screen position of document elements (§15.5)</li>
  <li>Create reusable user interface components (§15.6)</li>
  <li>Draw graphics (§15.7 and §15.8)</li>
  <li>Play and generate sounds (§15.9)</li>
  <li>Manage browser navigation and history (§15.10)</li>
  <li>Exchange data over the network (§15.11)</li>
</ul>

<p>Store data on ...</p>
<!-- chapter 16 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>Chapter 16. Server-Side JavaScript with Node</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Node is JavaScript with bindings to the underlying operating system, making it possible to write 
JavaScript programs that read and write files, execute child processes, and communicate over the 
network. This makes Node useful as a:</p>
<ul>
  <li>Modern alternative to shell scripts that does not suffer from the arcane syntax of bash 
    and other Unix shells.</li>
  <li>General-purpose programming language for running trusted programs, not subject to the security 
	constraints imposed by web browsers on untrusted code.</li>
  <li>Popular environment for writing efficient and highly concurrent web servers.</li>
</ul>
<p>The defining feature of Node is its single-threaded event-based concurrency enabled by an 
asynchronous-by-default API. If you have programmed in other languages but have not done much 
JavaScript coding, or if you’re an experienced client-side JavaScript programmer used to writing 
code for web browers, using Node will be a bit of an adjustment, as is any new programming language 
or environment. This chapter begins by explaining the Node programming model, with an emphasis on 
concurrency, Node’s API for working with streaming data, and Node’s Buffer type for working with 
binary data. These initial sections are followed by sections that highlight and demonstrate some 
of the most important Node APIs, including those for working with files, networks, processes, and 
threads.</p>

<p>One chapter is not enough to document all of Node’s APIs, but my hope is that this chapter will 
explain ...</p>

<!-- chapter 17 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch17">Chapter 17. JavaScript Tools and Extensions</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Congratulations on reaching the final chapter of this book. If you have read everything that comes 
before, you now have a detailed understanding of the JavaScript language and know how to use it in 
Node and in web browsers. This chapter is a kind of graduation present: it introduces a handful of 
important programming tools that many JavaScript programmers find useful, and also describes two 
widely used extensions to the core JavaScript language. Whether or not you choose to use these 
tools and extensions for your own projects, you are almost certain to see them used in other 
projects, so it is important to at least know what they are.</p>

<p>The tools and language extensions covered in this chapter are:</p>
<ul>
  <li>ESLint for finding potential bugs and style problems in your code.</li>
  <li>Prettier for formatting your JavaScript code in a standardized way.</li>
  <li>Jest as an all-in-one solution for writing JavaScript unit tests.</li>
  <li>npm for managing and installing the software libraries that your program depends on.</li>
  <li>Code-bundling tools—like webpack, Rollup, and Parcel—that convert your modules of JavaScript 
    code into a single bundle for use on the web.</li>
  <li>Babel for translating JavaScript code that uses brand-new language features (or that uses 
    language extensions) into JavaScript code that can run in current web browsers.</li>
  <li>The JSX language extension (used by the React framework) that allows you to describe user 
    interfaces using JavaScript expressions that look like ...</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>Chapter 5 Statements</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Chapter 4 described expressions as JavaScript phrases. By that analogy, statements are
JavaScript sentences or commands. Just as English sentences are terminated and separated from 
one another with periods, JavaScript statements are terminated with semicolons (§2.6). 
Expressions are evaluated to produce a value, but statements are executed to make something happen.</p>

<p>One way to “make something happen” is to evaluate an expression that has side
effects. Expressions with side effects, such as assignments and function invocations,
can stand alone as statements, and when used this way are known as expression state‐
ments. A similar category of statements are the declaration statements that declare
new variables and define new functions.</p>

<p>JavaScript programs are nothing more than a sequence of statements to execute. By
default, the JavaScript interpreter executes these statements one after another in the
order they are written. Another way to “make something happen” is to alter this
default order of execution, and JavaScript has a number of statements or control struc‐
tures that do just this:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Conditionals</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Statements like if and switch that make the JavaScript interpreter execute or skip other 
statements depending on the value of an expression</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Loops</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Statements like while and for that execute other statements repetitively</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Jumps</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Statements like break, return, and throw that cause the interpreter to jump to another part of 
the program</p>

<p>The sections that follow describe the various statements in JavaScript and explain their syntax. 
Table 5-1, at the end of the chapter, summarizes the syntax. A JavaScript program is simply a 
sequence of statements, separated from one another with semicolons, so once you are familiar with 
the statements of JavaScript, you can begin writing JavaScript programs.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>5.1 Expression Statements</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The simplest kinds of statements in JavaScript are expressions that have side effects. This sort 
of statement was shown in Chapter 4. Assignment statements are one major category of expression 
statements. For example:</p>

<pre>
greeting = "Hello " + name;
i *= 3;
</pre>

<p>The increment and decrement operators, ++ and --, are related to assignment statements. These have 
the side effect of changing a variable value, just as if an assignment had been performed:</p>

<pre>counter++;</pre>

<p>The delete operator has the important side effect of deleting an object property. Thus, it is almost 
always used as a statement, rather than as part of a larger expression:</p>

<pre>delete o.x;</pre>

<p>Function calls are another major category of expression statements. For example:

<pre>
console.log(debugMessage);
displaySpinner(); // A hypothetical function to display a spinner in a web app.
</pre>

<p>These function calls are expressions, but they have side effects that affect the host environment or 
program state, and they are used here as statements. If a function does not have any side effects, there 
is no sense in calling it, unless it is part of a larger expression or an assignment statement. For 
example, you wouldn’t just compute a cosine and discard the result:</p>

<pre>Math.cos(x);</pre>

<p>But you might well compute the value and assign it to a variable for future use:</p>

<pre>cx = Math.cos(x);</pre>

<p>Note that each line of code in each of these examples is terminated with a semicolon.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>5.2 Compound and Empty Statements</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Just as the comma operator (§4.13.7) combines multiple expressions into a single expression, a statement 
block combines multiple statements into a single compound statement. A statement block is simply a sequence 
of statements enclosed within curly braces. Thus, the following lines act as a single statement and can be 
used anywhere that JavaScript expects a single statement:</p>

<pre>
{
  x = Math.PI;
  cx = Math.cos(x);
  console.log("cos(π) = " + cx);
}
</pre>

<p>There are a few things to note about this statement block. First, it does not end with a semicolon. The 
primitive statements within the block end in semicolons, but the block itself does not. Second, the lines 
inside the block are indented relative to the curly braces that enclose them. This is optional, but it 
makes the code easier to read and understand.</p>

<p>Just as expressions often contain subexpressions, many JavaScript statements contain substatements. 
Formally, JavaScript syntax usually allows a single substatement. For example, the while loop syntax 
includes a single statement that serves as the body of the loop. Using a statement block, you can place 
any number of statements within this single allowed substatement.</p>

<p>A compound statement allows you to use multiple statements where JavaScript syntax expects a single 
statement. The empty statement is the opposite: it allows you to include no statements where one is 
expected. The empty statement looks like this:</p>

<pre>;</pre>

<p>The JavaScript interpreter takes no action when it executes an empty statement. The empty statement 
is occasionally useful when you want to create a loop that has an empty body. Consider the following 
for loop (for loops will be covered in §5.4.3):</p>

<pre>
// Initialize an array a
for(let i = 0; i < a.length; a[i++] = 0) ;
</pre>

<p>In this loop, all the work is done by the expression a[i++] = 0, and no loop body is necessary. 
JavaScript syntax requires a statement as a loop body, however, so an empty statement—just a bare 
semicolon—is used.</p>

<p>Note that the accidental inclusion of a semicolon after the right parenthesis of a for loop, while 
loop, or if statement can cause frustrating bugs that are difficult to detect. For example, the 
following code probably does not do what the author intended:</p>

<pre>
if ((a === 0) || (b === 0)); // Oops! This line does nothing...
o = null; // and this line is always executed.
</pre>

<p>When you intentionally use the empty statement, it is a good idea to comment your code in a way 
that makes it clear that you are doing it on purpose. For example:</p>

<pre>for(let i = 0; i < a.length; a[i++] = 0) /* empty */ ;</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>5.3 Conditionals</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Conditional statements execute or skip other statements depending on the value of a specified 
expression. These statements are the decision points of your code, and they are also sometimes 
known as “branches.” If you imagine a JavaScript interpreter following a path through your code, 
the conditional statements are the places where the code branches into two or more paths and the 
interpreter must choose which path to follow.</p>

<p>The following subsections explain JavaScript’s basic conditional, the if/else statement, and 
also cover switch, a more complicated, multiway branch statement.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>5.3.1 if</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The if statement is the fundamental control statement that allows JavaScript to make decisions, 
or, more precisely, to execute statements conditionally. This statement has two forms. The first is:</p>

<pre>
if (expression)
statement
</pre>

<p>In this form, expression is evaluated. If the resulting value is truthy, statement is executed. If 
expression is falsy, statement is not executed. (See §3.4 for a definition of truthy and falsy values.) 
For example:</p>

<pre>
if (username == null) // If username is null or undefined,
username = "John Doe"; // define it
</pre>

<p>Or similarly:</p>

<pre>
// If username is null, undefined, false, 0, "", or NaN, give it a new value
if (!username) username = "John Doe";
</pre>

<p>Note that the parentheses around the expression are a required part of the syntax for the if 
statement.</p>

<p>JavaScript syntax requires a single statement after the if keyword and parenthesized expression, 
but you can use a statement block to combine multiple statements into one. So the if statement might 
also look like this:</p>

<pre>
if (!address) {
  address = "";
  message = "Please specify a mailing address.";
}
</pre>

<p>The second form of the if statement introduces an else clause that is executed when expression is 
false. Its syntax is:</p>

<pre>
if (expression)
  statement1
else
  statement2
</pre>

<p>This form of the statement executes statement1 if expression is truthy and executes statement2 if 
expression is falsy. For example:</p>

<pre>
if (n === 1)
  console.log("You have 1 new message.");
else
  console.log(`You have ${n} new messages.`);
</pre>

<p>When you have nested if statements with else clauses, some caution is required to ensure that the 
else clause goes with the appropriate if statement. Consider the following lines:</p>

<pre>
i = j = 1;
k = 2;
if (i === j)
if (j === k)
  console.log("i equals k");
else
  console.log("i doesn't equal j"); // WRONG!!
</pre>

<p>In this example, the inner if statement forms the single statement allowed by the syntax of the 
outer if statement. Unfortunately, it is not clear (except from the hint given by the indentation) 
which if the else goes with. And in this example, the indentation is wrong, because a JavaScript 
interpreter actually interprets the previous example as:</p>

<pre>
if (i === j) {
  if (j === k)
    console.log("i equals k");
  else
    console.log("i doesn't equal j"); // OOPS!
}
</pre>

<p>The rule in JavaScript (as in most programming languages) is that by default an else clause is part 
of the nearest if statement. To make this example less ambiguous and easier to read, understand, maintain, 
and debug, you should use curly braces:</p>

<pre>
if (i === j) {
  if (j === k) {
    console.log("i equals k");
  }
} else { // What a difference the location of a curly brace makes!
  console.log("i doesn't equal j");
}
</pre>

<p>Many programmers make a habit of enclosing the bodies of if and else statements (as well as other 
compound statements, such as while loops) within curly braces, even when the body consists of only a 
single statement. Doing so consistently can prevent the sort of problem just shown, and I advise you 
to adopt this practice. In this printed book, I place a premium on keeping example code vertically 
compact, and I do not always follow my own advice on this matter.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>5.3.2 else if</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The if/else statement evaluates an expression and executes one of two pieces of code, depending 
on the outcome. But what about when you need to execute one of many pieces of code? One way to do 
this is with an else if statement. else if is not really a JavaScript statement, but simply a 
frequently used programming idiom that results when repeated if/else statements are used:</p>

<pre>
if (n === 1) {
  // Execute code block #1
  } else if (n === 2) {
  // Execute code block #2
  } else if (n === 3) {
  // Execute code block #3
  } else {
  // If all else fails, execute block #4
}
</pre>

<p>There is nothing special about this code. It is just a series of if statements, where each following 
if is part of the else clause of the previous statement. Using the else if idiom is preferable to, and 
more legible than, writing these statements out in their syntactically equivalent, fully nested form:</p>

<pre>
if (n === 1) {
  } // Execute code block #1
else {
  if (n === 2) {
    // Execute code block #2
  }
  else {
    if (n === 3) {
      // Execute code block #3
    }
    else {
      // If all else fails, execute block #4
    }
  }
}
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>5.3.3 switch</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>An if statement causes a branch in the flow of a program’s execution, and you can use the else 
if idiom to perform a multiway branch. This is not the best solution, however, when all of the 
branches depend on the value of the same expression. In this case, it is wasteful to repeatedly 
evaluate that expression in multiple if statements. The switch statement handles exactly this 
situation. The switch keyword is followed by an expression in parentheses and a block of code in 
curly braces:</p>

<pre>
switch(expression) {
  statements
}
</pre>

</p>However, the full syntax of a switch statement is more complex than this. Various locations in 
the block of code are labeled with the case keyword followed by an expression and a colon. When a 
switch executes, it computes the value of expression and then looks for a case label whose expression 
evaluates to the same value (where sameness is determined by the === operator). If it finds one, it 
starts executing the block of code at the statement labeled by the case. If it does not find a case 
with a matching value, it looks for a statement labeled default:. If there is no default: label, 
the switch statement skips the block of code altogether.</p>

<p><b>switch</b> is a confusing statement to explain; its operation becomes much clearer with an 
example. The following switch statement is equivalent to the repeated if/else statements shown in 
the previous section:</p>

<pre>
switch(n) {
  case 1: // Start here if n === 1
    // Execute code block #1.
    break; // Stop here
  case 2: // Start here if n === 2
    // Execute code block #2.
    break; // Stop here
  case 3: // Start here if n === 3
    // Execute code block #3.
    break; // Stop here
  default: // If all else fails...
    // Execute code block #4.
    break; // Stop here
}
</pre>

<p>Note the break keyword used at the end of each case in this code. The break statement, described 
later in this chapter, causes the interpreter to jump to the end (or “break out”) of the switch 
statement and continue with the statement that follows it. The case clauses in a switch statement 
specify only the starting point of the desired code; they do not specify any ending point. In the 
absence of break statements, a switch statement begins executing its block of code at the case 
label that matches the value of its expression and continues executing statements until it reaches 
the end of the block. On rare occasions, it is useful to write code like this that “falls through”
from one case label to the next, but 99% of the time you should be careful to end every case with 
a break statement. (When using switch inside a function, however, you may use a return statement 
instead of a break statement. Both serve to terminate the switch statement and prevent execution 
from falling through to the next case.)</p>

<p>Here is a more realistic example of the switch statement; it converts a value to a string in a 
way that depends on the type of the value:</p>

<pre>
function convert(x) {
  switch(typeof x) {
    case "number": // Convert the number to a hexadecimal integer
      return x.toString(16);
    case "string": // Return the string enclosed in quotes
      return '"' + x + '"';
    default: // Convert any other type in the usual way
    return String(x);
  }
}
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>5.4 Loops</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>To understand conditional statements, we imagined the JavaScript interpreter following a branching 
path through your source code. The looping statements are those that bend that path back upon itself 
to repeat portions of your code. JavaScript has five looping statements: while, do/while, for, for/of 
(and its for/await variant), and for/in. The following subsections explain each in turn. One common 
use for loops is to iterate over the elements of an array. §7.6 discusses this kind of loop in detail 
and covers special looping methods defined by the Array class.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>5.4.1 while</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Just as the if statement is JavaScript’s basic conditional, the while statement is JavaS‐
cript’s basic loop. It has the following syntax:</p>

<pre>
while (expression)
statement
</pre>

<p>To execute a while statement, the interpreter first evaluates expression. If the value of
the expression is falsy, then the interpreter skips over the statement that serves as the
loop body and moves on to the next statement in the program. If, on the other hand,
the expression is truthy, the interpreter executes the statement and repeats, jumping
back to the top of the loop and evaluating expression again. Another way to say this is
that the interpreter executes statement repeatedly while the expression is truthy. Note
that you can create an infinite loop with the syntax while(true).</p>

<p>Usually, you do not want JavaScript to perform exactly the same operation over and
over again. In almost every loop, one or more variables change with each iteration of
the loop. Since the variables change, the actions performed by executing statement
may differ each time through the loop. Furthermore, if the changing variable or vari‐
ables are involved in expression, the value of the expression may be different each
time through the loop. This is important; otherwise, an expression that starts off tru‐
thy would never change, and the loop would never end! Here is an example of a
while loop that prints the numbers from 0 to 9:</p>

<pre>
let count = 0;
while(count < 10) {
  console.log(count);
  count++;
}
</pre>

<p>As you can see, the variable count starts off at 0 and is incremented each time the
body of the loop runs. Once the loop has executed 10 times, the expression becomes
false (i.e., the variable count is no longer less than 10), the while statement finishes,
and the interpreter can move on to the next statement in the program. Many loops
have a counter variable like count. The variable names i, j, and k are commonly used
as loop counters, though you should use more descriptive names if it makes your
code easier to understand.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>5.4.2 do/while</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The <b>do/while</b> loop is like a while loop, except that the loop expression is tested at the
bottom of the loop rather than at the top. This means that the body of the loop is
always executed at least once. The syntax is:</p>

<pre>
do
statement
while (expression);
</pre>

<p>The <b>do/while</b> loop is less commonly used than its while cousin—in practice, it is
somewhat uncommon to be certain that you want a loop to execute at least once.</p>

<p>Here’s an example of a do/while loop:</p>

<pre>
function printArray(a) {
  let len = a.length, i = 0;
  if (len === 0) {
    console.log("Empty Array");
  } else {
    do {
      console.log(a[i]);
    } while(++i < len);
  }
}
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Table 5-1. JavaScript statement syntax
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<table>
  <tr>
    <th>Statement</th>
	<th>Purpose</th>
  </tr>
  <tr>
    <td>break</td>
	<td>Exit from the innermost loop or switch or from named enclosing statement</td>
  </tr>
  <tr>
    <td>case</td>
	<td>Label a statement within a switch</td>
  </tr>
  <tr>
    <td>class</td>
	<td>Declare a class</td>
  </tr>
  <tr>
    <td>const</td>
	<td>Declare and initialize one or more constants</td>
  </tr>
  <tr>
    <td>continue</td>
	<td>Begin next iteration of the innermost loop or the named loop</td>
  </tr>
  <tr>
    <td>debugger</td>
	<td>Debugger breakpoint</td>
  </tr>
  <tr>
    <td>default</td>
	<td>Label the default statement within a switch</td>
  </tr>
  <tr>
    <td>do/while</td>
	<td>An alternative to the while loop</td>
  </tr>
  <tr>
    <td>export</td>
	<td>Declare values that can be imported into other modules</td>
  </tr>
  <tr>
    <td>for</td>
	<td>An easy-to-use loop</td>
  </tr>
  <tr>
    <td>for/await</td>
	<td>Asynchronously iterate the values of anasyn iterator</td>
  </tr>
  <tr>
    <td>for/in</td>
	<td>Enumerate the property names of an object</td>
  </tr>
  <tr>
    <td>for/of</td>
	<td>Enumerate the values of an iterable object such as an array</td>
  </tr>
  <tr>
    <td>function</td>
	<td>Declare a function</td>
  </tr>
  <tr>
    <td>if/else</td>
	<td>Execute one statement or another depending on a condition</td>
  </tr>
  <tr>
    <td>import</td>
	<td>Declare names for values defined in other modules</td>
  </tr>
  <tr>
    <td>label</td>
	<td>Give statement a name for use with break and continue</td>
  </tr>
  <tr>
    <td>let</td>
	<td>Declare and initialize one or more block-scoped variables (new syntax)</td>
  </tr>
  <tr>
    <td>return</td>
	<td>Return a value from a function</td>
  </tr>
  <tr>
    <td>switch</td>
	<td>Multiway branch to case or default: labels</td>
  </tr>
  <tr>
    <td>throw</td>
	<td>Throw an exception</td>
  </tr>
  <tr>
    <td>try/catch/finally</td>
	<td>Handle exceptions and code cleanup</td>
  </tr>
  <tr>
    <td>"use strict"</td>
	<td>Apply strict mode restrictions to script or function</td>
  </tr>
  <tr>
    <td>vat</td>
	<td>Declare and initialize one or more variable (old syntax)</td>
  </tr>
  <tr>
    <td>while</td>
	<td>A basic loop construct</td>
  </tr>
  <tr>
    <td>with</td>
	<td>Extend the scope chain (deprecated and forbidden in strict mode)</td>
  </tr>
  <tr>
    <td>yield</td>
	<td>Provide a value to be iterated; only used in generator functions</td>
  </tr>
</table>

