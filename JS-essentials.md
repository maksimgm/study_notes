Javascript Essentials
===

### Intro to Javascript

Javascript is a programming language that runs in tandem CSS and HTML. It's primary function is controlling the behavior of the page. JS is refered to as a scripting language; it runs in a web browser. Additionally, it is a client-side language. The script is sent to the clients browers, unlike a server side language which is sent to a server.

Because of the popularity of JS, server side platforms such as, Node.js have been developed. 

Use whatever text editor already using. Most text editors support JS.
######Simple Javascript:

	<script>
        alert("Hello World!");
    </script>



### Basic Javascript Syntax

Each JS language should end with a semin-colon. Multiple statements can be placed on one line, but try not to do this, because it makes the script harder to read. Start yes script on a new line.

JS is case Sensitive! Additionally, it is whitespace insensitive. 

The following scripts are interpreted in the same way:
	
	alert("Hello World");
	
	alert
		("Hello World");

Add comments e.g.

	// this is a comment
	/* this is also a comment */	

###### Where to put JS

Using inline JS in your HTML is a problem when working with long HTML documents, because your code becomes fragmented. Instead, make a JS tab in your text editor, like you would with HTML or CSS. Keep the 'script' tag in HTML and add the 'src' tag to link up to your script.js tab. The script.js tab does not require a 'script' tag.

####### Location of the Script Tag
 
Place the script tag at the end of your body section. 

##### Variables

A variable is a container. You create it, name it, and apply a  value to it. Varibles can contian: letters, numbers, _, and $. Be mindful that you cannot start with a number.

###### Variable examples:

	var pizza;
	pizza = cheese;
OR
	
	var pizza = cheese;
-
	
	var almonds;		
	var cashews;
	var peanuts;
=

	var almonds, month, day;
	
###### Working with conditional code

If Statement:

	if ( condition ) {	
		// code goes here
		// ...
	}

* all condition must be true or false.

-

	if ( a === 100 ) {
		// code goes here
		// ...
		}
Check inequality using `!=`

	if ( m != 100 ) {
		// code goes here
		// ...
		}
If else statement:

	if ( m < 100 ) {
		block of code being executed if m is true
	} else {
		block of code being executed if m is false
	}
		
##### Working with Operators

**Arithmetic operators**: + - * /


Arithmetic shorthand:

	count +=25;
	
	+=	-=	*=	/=

Operator Precedence:	
	
	result = 4 + 4 * 3;
	result = 16
	
* follow the order of operations-- perenthesis, multiplication, division, addition, subtraction.

**Operators with =**

* =	*assignment*
* == *equality*
* === *strict equality*

Equality v. Strict Equality:

		var a = 10;
		var b = "10";
	
	if ( a == b ) {
		alert( "Yes, they are equal");
	}  else {
		alert( "They are not equal");
	}
	
	RESULT: Yes, they are equal.
	
		var a = 10;
		var b = "10";
	
	if ( a === b ) {
		alert( "Yes, they are equal");
	}  else {
		alert( "They are not equal");
	}	

	RESULT: No, they are not equal.

**Logical And / OR**

	if ( a == b   &&   c == d) { ...
	
	if ( a == b   ||   c == d) { ...
	
**Modules**

	var year = 2003;
	var remainder = year % 4; // remainder is 3
	
**Increment / Decrement**

	a = a +2;
	a += 2;
	a++;
	++a;
* all of the above are equal.

**Prefix / Postfix**

	var a = 3;
	alert( ++a );
		
	Value of a will change to 4. Result is 4.
	
	var a = 3;
	alert( a++ );	
	
	Value of a will be 3. Result is 3.
	
**Ternary Operator**

	condition ? true : false 
-

	var playerOne = 15;
	var playerTwo = 20;
	
	// sometime later
	var highScore;
	
	if ( playerOne > playerTwo ) {
		highScore = playerOne;
	}
	else {
		highScore = playerTwo;
	}

Alternatively, a ternary operator allows you to simplify this code. e.g.
	
	var playerOne = 15;
	var playerTwo = 20;
	
	( playerOne > playerTwo ) ? playerOne : playerTwo;
	
##### Sending Messages to the console

		var foo = 1;
		var bar = 2;
	
	if ( foo < bar ) {
		consol.log( "foo is less than bar" );
		console.log( "foo");
		console.log( "bar" );
	}
	
* As opposed to using `alert`, `console.log` will display the script in your console, instead of displaying an alert. 
	
##### Working with Loops

Loops can execute a block of code a number of times. They are handy, if you want to run the same code over and over again, but with a different value each time.

Javascript support different kinds of loops:

**while** - loops through a block of code while a specified condition is true. e.g.

		var a = 2;
		
		while	( a < 11 ) {
			console.log(a);
		}
* this is an infinite loop.

		var a = 2;
		
		while	( a < 11 ) {
			console.log(a);
			a++;
		}
* The value of `a` will increase by 1 after each loop.
				
**do/while** - also loops through a block of code while a specified condition is true.

		var a = 15;
	
		do {
			console.log (a);
			a++;	
		} while	( a < 11 );

* the main difference between *while loop* and *do/while* is, the *do/while loop* will always be executed at least once, whether it is true or false.

**for** - loops through a block of code a number of times.

	for ( var i = 2; i < 10 ; i++ ) {
		// do stuff
		// do stuff
		// do stuff
		// etc...
	}
* *for loop* consists of three elements
	* setup index e.g.
		* `var i = 2`
	* check condition e.g.
		* `i < 10`
	* increment index e.g.
		* `i++`
		
**for/in** - loops through the properties of an object.

**Break**

	for ( var i = 2; i < 300 ; i++ ) {
		// do stuff
		// do stuff
		if ( i == 100) {
			break;
		}
		 // do stuff
		}
		
		// break jumps out of loop
		
**Continue**

	for ( var i = 2; i < 300 ; i++ ) {
		// do stuff
		// do stuff
		if ( i == 100) {
			continue; // done with iteration
		}
		 // do second set of stuff
		}
		
		// continue moves us back to the top

###### Functions

A Javascript function is a block of code designed to perform a particular task. e.g.

	function createGreeting	() {
		console.log("Hello World");
		// loops, if statements, anything!
		// ...
	}
	
	// sometime later
	createGreeting ();
	
* the function name has to be one word and you may not use letters.
* if it's in a function, it won't run uless you call it.

**Where to Declare Functions**

Declare your functions before you call them. e.g.

	function myFunction () {
		//lots of code
	}
	function myOtherFunction () {
		//lots of code
		myFunction ();
		}
	
	myFunction();
	
**Functions With Parameters**

					    parameters
	function myFunction ( x,y ) {
		var myVar = x * y;
		console.log(myVar);
		// we can return values
		return myVar;
	}
	myFunction(75,12);
	myFunction(35,82);
	var myresult = myFunction(4,2);
	
**Parameter Mismatch**


	function calculateLoan ( amount, months, 				
		interest, name) {
		// lots of code
	}

	
	calculateLoan (1000, 60, 9, "Jon Smith");



#### Types and Objects

##### Working with arrays

Array is a single variable that holds multiple values. They are zero based. Additionally, they are very dynatmic, meaning they can easily be changed.

	var multipleValues= [] ;
	
	multipleValues [0] = 20;
	multipleValues [1] = 30;
	multipleValues [2] = 40;
	
	Shorthand:
	
	var multipleValues = [ 20,30,40 ];
							[0][1][2]
							
**Array Properties**

	console.log (multipleValues.length); length is 5

	* sets length

**Array Methods**

Methods are functions that belong to an object. Arrays have built in methods. e.g. `.join`, `.sort`, and `.reverse`. Arrays are objects means that we can ask them to do useful things. 

Arrays are everywhere in JS. 



##### Working with numbers

All JS numbers are 64-bit floating point numbers.

Addition v. Concatenation

	var foo = 5;
	var bar = 5;
	console.log( foo + bar ); // 10
	
	var foo = "5";
	var bar = "5";
	console.log( foo + bar ); // 55
	
	var foo = 5;
	var bar = "5";
	console.log( foo + bar ); // 55- one is a string
	
	var foo = 5;
	var bar = "b";
	console.log( foo * bar ); // NaN
	
* NaN- Not a number. This is a special meaning in JS. JS is telling you that the expression does not make sense.

**Using Math Objects**

	var x = 200.6;
	var y = Math.round(x); // 201
	
	var a = 200, var b = 10000, c = 4;
	var biggest = Math.max(a,b,c);
	var smallest = Math.min(a,b,c);
	
	Math.PI     Math.random()     .sqrt()     .log()


##### Working with strings

	var myString = "Double quotes work.";
	var myString = 'Single quotes work too.';
	var myString = 'One or the other.";

	var phrase = 'Don't mix your quotes.';
	//Wrong
	var phrase = "Don't mix your quotes.";
	//Right
	
	var phrase = "He said "that's fine," and left.";
	//Wrong
	var phrase = "He said \"that's fine,\" and left.";
	//Right. This tells JS not to close your script
	
**Properties**

Strings can be treated as objects, because they have information we can ask of them. 

	var phrase = "This is a simple phrase.";
	console.log(phrase.length); // 24

**Methods**

	var phrase = "This is a simple phrase.";
	console.log(phrase.toUpperCase() );
		// THIS IS A SIMPLE PHRASE
		
	var phrase = "This is a simple phrase.";
	var words = phrase.split (" "); e.g.
	
|Array|phrase|	
|------|-------|
|0 |This|
|1|is|
|2|a|
|3|simple|
|4|phrase.|


	var phrase = "We want a groovy keyborad.";
	var position = phrase.indexOf ("groovy"); // 10
	
	//it returns 0 if term is found at the begining
	// it returns -1 if the term is not found
	
	if ( phrase.indexOf("AAAA") == -1) {
		console/log("That word does not occur.");
	}
	
	var phrase = "Yet another phrase.";
	
	var segment = phrase.slice(6,11); //makes new string with characters between 6-11.

	// slice does not change the original string
	
String Comparision

	var string1 = "Hello";
	var string2 = "hello";
	
	//string1 != string2
	
String Reference

[JS Reference](http://developer.mozilla.org/en/JavaScript/Reference)	

##### Working with dates

	var today = new Date (); // current date and time
	
	var y2k = new Date(2000,0,1);
				// year, month, day
				
	var y2k = new Date(2000,0,1,0,0,0);
	// year, month, day, hours, minutes,seconds
	
**Get Method of the Date Object**

	var today = new Date();
	
	today.getMonth(); // returns 0-11
	today.getFullYear(); // YYYY (not zero-based)
	today.getDate(); // 1-31 day of month
	today.getDay(); // 0-6 day of the week. 0 == sunday
	today.getHours(); // 0-23
	today.getTime(); // milliseconds since 1/1/1970

**Set Method of the Date Object**

	var today = new Date();
	
	today.setMonth(5);
	today.setFullYear(2013);
	today.setDay(0);
	// etc.
	
**Comparing Dates**

	var date1 = new Date(2000,0,1);
	var date2 = new Date(2000,0,1);
	
	if ( date1 == date2 ) { ... //false!
	
	if ( date1.getTime() == date2.getTime() ) { ...
	// true!
	
##### Working with objects




### Understanding and Working the Document Object Model


