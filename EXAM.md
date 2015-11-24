### 1. Get DOM elements using Javascript selectors

* Select an __IMG__ element
document.querySelector('img');

* Select all __H2__ elements
document.querySelectorAll('h2');

* Select all __A__ elements that have the attribute _title_
document.querySelectorAll('a[title]');

* Select only the __IMG__ elements that are inside an __A__ element
document.querySelectorAll('a img');

* Select all elements with class _article_
document.querySelectorAll('.article');

* Select all _article_ from the middle and right column, but not from the left column
// Didn't understand this quite good, because the middle column is with right class, but right column doesn't have articles

* Select the 4th and 5th _article_ from the left column
document.querySelectorAll('[class$="1-left"] article:nth-child(n+4):nth-child(-n+5)');

* Select the logo of the website
document.querySelector('.header-logo-h a');

* Select all __IMG__ elements whose _SRC_ attribute is a _JPG_ file
document.querySelectorAll('img[src*=".jpg"]');

### 2. Apply CSS to DOM

* Change the main article title to FF0000
document.querySelector('.art-info-complete h3 a').style.color = "#FF0000";

* Change page background color to green
document.querySelector('body').style.background = "green";

* Change subtitles to lowercase
var subtitles = document.querySelectorAll('h4[subtitle]');
for(var i = 0; i < subtitles.length; i = i + 1)
{
    subtitles[i].style.textTransform = 'lowercase';
}

* Hide opinion column
document.querySelector('.opinion').style.display = 'none';

* Make top Ad banner sticky at the bottom
var css = 'position:fixed;bottom:0px;'
var banner = document.querySelector('.hide-ad').style.cssText = css;

### 3. DOM Manipulation with Javascript

* Add a 10px red border around all __IMG__ elements 
var img = document.querySelectorAll('img');
for(var i = 0; i < img.length; i = i + 1)
{
    img[i].style.border = 'solid 10px red';
}

* Fade out all __IMG__ elements
var img = document.querySelectorAll('img');
for(var i = 0; i < img.length; i = i + 1)
{
    img[i].style.cssText = 'transition: opacity 500ms;opacity: 0;';
}

* Add a 10px red border around all __IMG__ and fade out the images after 3 seconds
var img = document.querySelectorAll('img');

for(var i = 0; i < img.length; i = i + 1)
{
    img[i].style.border = 'solid 10px red';
}

setTimeout(function(){
	for(var i = 0; i < img.length; i = i + 1)
	{
	    img[i].style.cssText = 'transition: opacity 1000ms;opacity: 0;';
	}
}, 3000);

### 4. Answer the following points

* Justify the chosen method used to hide opinion column
It requires the least amount of code and it works as good as every other method.

* Explain the difference between position static, relative, absolute and fixed

* What are data SRCs? When would you use them?

* What benefits you get by using a CSS preprocessor?

* Why would you use unit testing?

* How would you accelerate an element by hardware and why?



