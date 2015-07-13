### 1. Get DOM elements using Javascript selectors

* Select an __IMG__ element
	```
	var img = document.getElementsByTagName("IMG")[0];
	```
* Select all __H2__ elements
	```
	var h2 = document.getElementsByTagName("H2");
	```
	
* Select all __A__ elements that have the attribute _title_
	```
	var a = document.getElementsByTagName("A");
	var matchingResults = [];
	for(var i = 0; i<a.length; i++){
		 if (a[i].getAttribute('title') !== null){
			matchingResults.push(a[i]);
		}
	}
	```
* Select only the __IMG__ elements that are inside an __A__ element
 	```
 	var a = document.getElementsByTagName("A");
	var imgs = [];
	
	for(var i = 0; i<a.length; i++){
		if(a[i].getElementsByTagName("IMG").length != 0){
			imgs.push(a[i].getElementsByTagName("IMG"));
		}
	}
 	```
* Select all elements with class _article_
	```
	var articles = document.getElementsByClassName("article");
	```
* Select all _article_ from the middle and right column, but not from the left column
* Select the 4th and 5th _article_ from the left column
* Select the logo of the website
	```
	var logo = document.getElementsByClassName("header-logo-h");
	```
* Select all __IMG__ elements whose _SRC_ attribute is a _JPG_ file

### 2. Apply CSS to DOM

* Change the main article title to FF0000
	```
	var h3 = document.getElementsByClassName("fs-86");
	var title = h3[0].getElementsByTagName("A");
	title[0].style.color="#FF0000";
	```
* Change page background color to green
	```
	var h = document.getElementsByTagName('*');
	for(var i = 0; i<h.length; i++){
		h[0].style.backgroundColor="green";
	}
	```
* Change subtitles to lowercase
* Hide opinion column
* Make top Ad banner sticky at the bottom

### 3. DOM Manipulation with Javascript

* Add a 10px red border around all __IMG__ elements 
* Fade out all __IMG__ elements
* Add a 10px red border around all __IMG__ and fade out the images after 3 seconds

### 4. Answer the following points

* Justify the chosen method used to hide opinion column

* Explain the difference between position static, relative, absolute and fixed

* What are data SRCs? When would you use them?

* What benefits you get by using a CSS preprocessor?

* Why would you use unit testing?

* How would you accelerate an element by hardware and why?



