#Foolish mistakes I make as a web developer

1. I forgot to add a closing `</div` tag!
```
<!-- You must close your div tags-->
<div class="container"> 
	<div class="stuff">
		...
	</div>
	<div class="stuff">
		...
	</div>
	<div class="stuff">
		...
	</div>
</div>
```

1. In JS, the data attribute can be accessed by dataset, but is it dataSet or dataset?
Again, is it just dataset or a function call dataset()?
```
<!--It is dataset, and it is a property, not a function-->
<button class="btn" data-state=1>State 1</button>
<script>
 	const btn = document.queryselector('.btn');
	console.log(btn.dataset.state);
</script>
```

1. Are the eventListeners camel-case? Is it mousedown or mouseDown? 
No, the eventListeners are all lowercase
```
document.addEventListener('mousedown',function(){...});
``` 

1. Then again, is it setTimeout or settimeout? I am confused between the eventListener case and standard JavaScript functions case
```
//It is setTimeout(); Standard javascript function names are camelCase
const tx = setTimeout(function(){console.log("Hi, I am 5 seconds late, sorry.")},5000);
const paragraphs = document.querySelectorAll('p');
//Also, many a property names of standard JS structures are camelCase
element.classList.add('newClass');
```

1. Speaking of eventListeners, what is the 'change' event?
The change event is fired for <input>, <select>, and <textarea> elements when a change to the element's value is committed by the user. Unlike the input event, the change event is not necessarily fired for each change to an element's value.

1. Do I use fat arrow function or normal function?
```
/*
A normal anonymous function identifies the calling element as ’this’
But an arrow function inherits ‘this’ from its parent.
*/

//If you want to create a new scope for 'this' and dive right into the created element, use a normal function.
<!DOCTYPE html>
<html>
<body>
<style>
.elem1{
	background: crimson;
	color: white;
	width:300px;
	height:200px;
}
</style>
<div class="elem1"></div>
<script>
	const elem1 = document.querySelector('.elem1');
	elem1.addEventListener('click',function(){
	console.log("I am a standard function and my this is:",this);
	// this returns 'elem1' in this example. The standard function is bounded by the parent which is document.
	});
</script>
</body>
</html>
```
Learn more about it [Here](http://thesagittariusme.blogspot.com/2017/02/es6-arrow-functions-this.html)

