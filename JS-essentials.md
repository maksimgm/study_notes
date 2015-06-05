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
* All condition must be true or false.

JS's way of checking equality is the `===`. e.g.

	if ( a === 100) {
		// code goes here
		// ...
		}

### Types and Objects



### Understanding and Working the Document Object Model



### Working with Events 




###
###
###
###