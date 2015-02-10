### 1. Get DOM elements using Javascript selectors

* Select an __IMG__ element
```js
document.getElementsByTagName('img')[0];
```
* Select all __H2__ elements
```js
document.getElementsByTagName('h2');
```
* Select all __A__ elements that have the attribute _title_
```js
document.querySelectorAll('a[title]');
```
* Select only the __IMG__ elements that are inside an __A__ element
```js
document.querySelectorAll('a img');
```
* Select all elements with class _article_
```js
document.getElementsByClassName('article');
```
* Select all _article_ from the middle and right column, but not from the left column
```js
document.querySelectorAll('.centralblock article');
document.querySelectorAll('.rightblock article');
```
* Select the 4th and 5th _article_ from the left column
```js
document.querySelectorAll('.leftblock article')[3];
document.querySelectorAll('.leftblock article')[4];
```
* Select the logo of the website
```js
document.getElementsByClassName('img-header-logo');
```
* Select all __IMG__ elements whose _SRC_ attribute is a _JPG_ file
```js
var src = document.querySelectorAll('img');
for(i = 0; i < src.length; i++){
  var imgSrc = src[i].src;
  var img = imgSrc.match(/.jpg/) || !null;
  console.log(img);
}
```

### 2. Apply CSS to DOM

* Change the main article title to FF0000
```css
.front .exclusive-info .title-box .title-exclusive-link {
  color: #FF0000 !important;
}
```
* Change page background color to green
```css
body {
  background-color: green;
}
```
* Change subtitles to lowercase
```css
span.subtitle{
  text-transform: lowercase;
}
```
* Hide opinion column
```css
.opinion {
  display: none;
}
```
* Make top Ad banner sticky at the bottom
```css
.front .header-bar {
  position: fixed;
  bottom: 0;
  z-index: 1000;
}
```

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



