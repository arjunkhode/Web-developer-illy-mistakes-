#Foolish mistakes I make as a web developer

1. I forgot to add a closing `div` tag!
	```
	You must close your div tags!
	```

1. At one time, I tried to use colon in a strange wrong way in CSS
	```
	a:
	width="100px";
	```
	That's a silly mistake indeed.
	Use the element names followed by braces. Properties are written inside these braces
	and use a colon for the attributes
	```
	a{
	width: 100px;
	}
	```

1. `<link rel="stylesheet" href="./style.css">`
	* Use ./ in the path even if it's in the same folder
	* It's href for stylesheet and not src

1. Meta tags have a name and content. The name of the meta tag is like a title for the meta property and content is the value assigned to that title.
	```
	<meta name="author" content="Arjun Khode"/>
	```

1. Let's settle the right way to write a meta for viewport once and for all
	```
	<meta name="viewport" content="width=device-width, initial-scale=1.0" />
	```

1. In JS, the data attribute can be accessed by dataset, but is it dataSet or dataset?

	Again, is it just dataset or a function call dataset()?
	```
	//It is dataset, and it is a property, not a function
	 	const btn = document.queryselector('.btn');
		console.log(btn.dataset.state);
	```

1. Are the eventListeners camel-case? Is it mousedown or mouseDown? 

	No, the eventListeners are all lowercase
	```
	document.addEventListener('mousedown',function(){...});
	``` 

1. Then again, is it setTimeout or settimeout? I am confused between the eventListener case and standard JavaScript functions case.

	```
	//It is setTimeout(); Standard javascript function names are camelCase
	const tx = setTimeout(function(){console.log("Hi, I am 5 seconds late, sorry.")},5000);
	const paragraphs = document.querySelectorAll('p');
	//Also, many a property names of standard JS structures are camelCase
	element.classList.add('newClass');
	```

1. Speaking of eventListeners, what is the 'change' event?

	The change event is fired for input, select, and textarea elements when a change to the element's value is committed by the user. Unlike the input event, the change event is not necessarily fired for each change to an element's value.

1. Do I use fat arrow function or normal function?

	```
	/*
	A normal anonymous function identifies the calling element as ’this’
	But an arrow function inherits ‘this’ from its parent.
	*/

	//If you want to create a new scope for 'this' and 
	//dive right into the created element, use a normal function.

		const elem1 = document.querySelector('.elem1');
		elem1.addEventListener('click',function(){
		console.log("I am a standard function and my this is:",this);
		//This returns 'elem1' in this example. 
		//The standard function is bounded by the parent which is document.
		
		const elem1 = document.querySelector('.elem1');
		elem1.addEventListener('click',()=>{
		console.log("I am a standard function and my this is:",this);
		//This returns 'Window' because the parent of the calling statement
		//is Window.
		});
	```
	Check out an [example](https://github.com/arjunkhode/Web-developer-silly-mistakes-/blob/master/fatarrow-vs-standard-functions.html)
	Learn more about it [Here](http://thesagittariusme.blogspot.com/2017/02/es6-arrow-functions-this.html)

1. You can't set background color of a radio button because no such exact property exists for it. You can change the appearance of a radio button but not by setting background color as we normally do for span, etc.

1. For text-overflow:ellipsis to work, width must be in px not %
	```
	white-space:nowrap;
	overflow:hidden;
	```

1. Let's resolve the issue of how to use a multiple type select input once and for all

	```
		<select name="cars[]" multiple="multiple">
		<option value="volvo">Volvo</option>
		<option value="saab">Saab</option>
		<option value="opel">Opel</option>
		<option value="audi">Audi</option>
		<!-- Note how name="cars[]" has square brackets after it-->
		</select>
		<?php
		$cars = $_POST['cars'];
		print_r ($cars);
		?>
	```

1. `.val()` is a jQuery thing and `.value` is a javaScript thing. It's primarily used to get the values of form elements such as input, select and textarea.

1. A callback function, also known as a 'higher order function' is a function that is passed to another function
1. test point
1. When to not use a semicolon?
