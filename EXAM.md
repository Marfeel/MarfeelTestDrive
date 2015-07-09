### 1. Get DOM elements using Javascript selectors
* Select an __IMG__ element
	document.querySelector("img");

* Select all __H2__ elements
	document.getElementsByTagName("h2");

* Select all __A__ elements that have the attribute _title_
	document.querySelectorAll("a[title]");

* Select only the __IMG__ elements that are inside an __A__ element
	document.querySelectorAll("a img");

* Select all elements with class _article_
	document.getElementsByTagName("article")

* Select all _article_ from the middle and right column, but not from the left column
	document.querySelectorAll(".opening-1-right-bottom article");

* Select the 4th and 5th _article_ from the left column
	document.querySelector(".opening-1-left article:nth-child(4)");
	document.querySelector(".opening-1-left article:nth-child(5)");

* Select the logo of the website
	document.querySelector(".header-fixed-logo-link");

* Select all __IMG__ elements whose _SRC_ attribute is a _JPG_ file
	document.querySelector('img[src$=".jpg"]');

### 2. Apply CSS to DOM
* Change the main article title to FF0000
	document.querySelector(".art-tit a").style.color = "#FF0000";

* Change page background color to green
	document.body.style.backgroundColor = "green"

* Change subtitles to lowercase
	var subtitles = document.getElementsByClassName("news-pin-link")
	for (i = 0; i < subtitles.length; i++) {
		subtitles[i].textContent.toLowerCase();
	}

* Hide opinion column
	document.getElementsByClassName("f141")[0].style.display = "none"

* Make top Ad banner sticky at the bottom
	document.getElementsByClassName("header-home")[0].style.position = "fixed";
	document.getElementsByClassName("header-home")[0].style.bottom = "0px";

### 3. DOM Manipulation with Javascript
* Add a 10px red border around all __IMG__ elements
	var images =  document.getElementsByTagName("img");
	for (i = 0; i < images.length; i++) {
		images[i].style.border = "10px solid red"; 
	}

* Fade out all __IMG__ elements
	function fadeOutImages() {
		var images =  document.getElementsByTagName("img");
		for (i = 0; i < images.length; i++) {
			images[i].style.opacity = images[i].style.opacity - 10; 
		}
		setTimeout(fadeOutImages, 100);
	}
	fadeOutImages();

* Add a 10px red border around all __IMG__ and fade out the images after 3 seconds
	var images =  document.getElementsByTagName("img");
	for (i = 0; i < images.length; i++) {
		images[i].style.border = "10px solid red";
	}
	function fadeOutImages() {
		for (i = 0; i < images.length; i++) {
			images[i].style.opacity = images[i].style.opacity - 10; 
		}
		setTimeout(fadeOutImages, 100);
	}
	setTimeout(fadeOutImages,3000);

### 4. Answer the following points

* Justify the chosen method used to hide opinion column
	It doesn't matter if we change the properties display, opacity or visibility because it doesn't affect the position of the other elements.
* Explain the difference between position static, relative, absolute and fixed
	Static ignores top, left, right and bottom declarations.
	Relatives applies the propierties top, left, right and bottom from its original place, where the element was generated.
	Absolute causes the element to be positioned to its first positioned ancestor element, and if no relative ancestor is found, to the body of the page.
	Fixed makes the element to be positioned relative to the browser window, causing the element to accompany the user as he scrolls.
* What are data SRCs? When would you use them?
	Data SRCS are just one of the infinite set of HTML data attributes, which have no defined meaning but can be used to include invisible data in an element. They can be used for scripting.
* What benefits you get by using a CSS preprocessor?
	We get CCS nested syntax, the ability to define variables and including files.
* Why would you use unit testing?
	Assume the project is large and it needs to be split into multiple files, a CSS preprocessor allows us to include/import those files.

	Anyway I never had to use one thanks to the CSS3 features, I'm lucky to have avoided earlier versions of HTML and CSS. :)
* How would you accelerate an element by hardware and why?
	Using a modern browser and to run CSS3 animations and transitions smoothly.		


