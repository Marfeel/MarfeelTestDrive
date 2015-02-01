### 1. Get DOM elements using Javascript selectors

* Select an __IMG__ element

	document.getElementsByTagName('img')[1];

* Select all __H2__ elements

	document.getElementsByTagName('h2');
	
* Select all __A__ elements that have the attribute _title_

	var a= document.getElementsByTagName('a');
	var j= 0;
	var allTitles=[];

	for(var i=0; i<a.length; i++){
		if(a[i].hasAttribute('title')){
	  		allTitles[j]=a[i];
	  		j++;
		}
	}

	console.log(allTitles);
	
* Select only the __IMG__ elements that are inside an __A__ element

	var a = document.getElementsByTagName('a');
	var imgInsideA =[];
	var j=0;
	var img;

	for(var i=0; i<a.length; i++){
		img = a[i].getElementsByTagName('img');
		if (img.length>0){
			imgInsideA[j]= img;
			j++
		}
	}

	console.log(imgInsideA);
	
* Select all elements with class _article_

	document.getElementsByClassName('article');
	
* Select all _article_ from the middle and right column, but not from the left column
	
	var central = document.getElementsByClassName('centralblock');
	var right = document.getElementsByClassName('rightblock');
	var allArticles =[];
	var k=0;
	var arts;
	var j;

	for (var i=0; i<central.length; i++){
		arts = central[i].getElementsByClassName('article');
		for(j=0; j<arts.length; j++){
	  		allArticles[k]=arts[j];
	  		k++;
		}
	}

	for (var i=0; i<right.length; i++){
		arts = right[i].getElementsByClassName('article');
		for(j=0; j<arts.length; j++){
		  allArticles[k]=arts[j];
		  k++;
		}
	}

	console.log(allArticles);

* Select the 4th and 5th _article_ from the left column

	var fourth = document.getElementsByClassName('leftblock')[0].getElementsByClassName('article')[3];
	var fifth = document.getElementsByClassName('leftblock')[0].getElementsByClassName('article')[4];
	
	console.log(fourth);
	console.log(fifth);

* Select the logo of the website

	var logo = document.getElementsByTagName('img')[1];
	
	console.log(logo);
	
* Select all __IMG__ elements whose _SRC_ attribute is a _JPG_ file

	var x=document.getElementsByTagName('img');
	var tipus;
	var j=0;
	var allJPG=[];

	for(var i=0; i<x.length; i++){
		tipus = x[i].getAttribute('src');
		if(tipus.match(/.jpg/)){
			allJPG[j]=x[i];
			j++;
		}
	}

	console.log(allJPG);

### 2. Apply CSS to DOM

* Change the main article title to FF0000

	.front .title-box h2 a{
		color: #FF0000;
	}

* Change page background color to green

	body{
		background:#00ff00;
	}

* Change subtitles to lowercase

	.subtitle{
		text-transform: lowercase;
	}

* Hide opinion column

	.opinion{
		display:none;
	}

* Make top Ad banner sticky at the bottom

	.header-bar{
		position: fixed;
		bottom: 0;
		z-index: 1000;
	}


### 3. DOM Manipulation with Javascript

* Add a 10px red border around all __IMG__ elements 
	
	var img=document.getElementsByTagName('img');

	for(var i=0; i<img.length; i++){
		img[i].style.border="10px solid #FF0000";
	}

* Fade out all __IMG__ elements
	//this can also be done with css transforms although you asked pure JS so that's it

	var img=document.getElementsByTagName('img');

	function fadeOut(img){
		img.style.opacity = 1;

		(function fade() {
			if ((img.style.opacity -= .05) < 0) {
			img.style.display = "none";
		} else {
		requestAnimationFrame(fade);
		}
		})();
	}

	for(var i=0; i<img.length; i++){
		fadeOut(img[i]);
	}

* Add a 10px red border around all __IMG__ and fade out the images after 3 seconds

	var img=document.getElementsByTagName('img');

	for(var i=0; i<img.length; i++){
		img[i].style.border="10px solid #FF0000";
	}

	function fadeOut(img){
		img.style.opacity = 1;

		(function fade() {
			if ((img.style.opacity -= .05) < 0) {
			img.style.display = "none";
		} else {
		requestAnimationFrame(fade);
		}
		})();
	}

	function update(){
		for(var i=0; i<img.length; i++){
			fadeOut(img[i]);
		}
	}

	setTimeout(update, 3000);


### 4. Answer the following points

* Justify the chosen method used to hide opinion column

	I used display:none; because it's the easiest step and using visibility:hidden; we get a blank space in the 	website which is not optimal for UX. If we need this content to still be accessible for screen readers 
	I would use: 
	.position{
		position: absolute;
		top: -9999px;
		left: -9999px;
	}
	
* Explain the difference between position static, relative, absolute and fixed
	
	Static is de default position for any element. 
	
	Relative means that the element is relative to himself, so we can move it relatively to it's original position, 	relative is also useful to apply z-index.
	
	Absolute allows us to put the element wherever we want but location settings are relative to it's parent 		element. Absolute elements are placed outside the flow of the page and it doesn't effect other elements. We can 	also use z-index for this kind of positioning.
	
	Fixed is positioned relative to the browser window.

* What are data SRCs? When would you use them?
	
	src is used to load an element and tells you where the file is loaded from. To load an image for example.
	data-src is an attribute without a predefined meaning that can be used, for example, in JavaScript to select a
	given element.

* What benefits you get by using a CSS preprocessor?
	
	The syntaxis is nested, you can define variables and mixins, you can use mathematical and operational functions
	ad you can join multiple files. Mainly preprocessors aim to simplify CSS and add functionalities to it.

* Why would you use unit testing?

	To identify problems at an early stage and plan your coding in a better way, to make changes easily and
	identify issues rapidly, it's easy to find and undestand every unit's job and it allows you to improve the 		design without breaking it.

* How would you accelerate an element by hardware and why?

	In CSS I would do it with using the 3d space (translate3d), also using canvas elements. It's useful
	in devices that have a graphical processing unit in order to help the CPU render graphical content.



