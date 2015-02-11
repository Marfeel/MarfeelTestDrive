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
```js
var img = document.getElementsByTagName('img');
for(var i = 0; i < img.length; i++){
  img[i].style.border = "10px solid red";
}
```
* Fade out all __IMG__ elements
```js
var img = document.getElementsByTagName('img');
var opacity = 1;
function fadeOut(){
  for(var i=0; i<img.length; i++){
    img[i].style.opacity = opacity;
    //console.log(img[i].style.opacity);
  }
  if(opacity > 0){
    initiate();
  }
}
function initiate(){
  opacity -= 0.2;
  setTimeout("fadeOut()", 80);
}
initiate();
```
* Add a 10px red border around all __IMG__ and fade out the images after 3 seconds
```js
var img = document.getElementsByTagName('img');
for(var i=0; i<img.length; i++){
	img[i].style.border="10px solid red";
}
var opacity = 1;
function fadeOut(){
	for(var i=0; i<img.length; i++){
		img[i].style.opacity = opacity;
		//console.log(img[i].style.opacity);
	}
	if(opacity > 0){
		initiate();
  }
}
function initiate(){
	opacity -= 0.2;
	setTimeout("fadeOut()", 80);
}
setTimeout('initiate()', 3000);
```

### 4. Answer the following points

* Justify the chosen method used to hide opinion column

> I preferred to use ```display: none``` attribute as it completly "removes" the elemente from the page, letting the adjacent element ocuppie his space. Do so, ```visibility: hidden``` can also be use. The main difference between these two is that the attribute "visibility", mantains the space of the focused element, so the adjacent elements stays on their spots. 
Can check for more info, here: 
[stackoverflow](http://stackoverflow.com/questions/3475119/css-properties-display-vs-visibility)

* Explain the difference between position static, relative, absolute and fixed

**static**

> The ```position: static``` is the default position used on all elements. The only reason you would ever set an element to ```position: static``` is to forcefully-remove some positioning that got applied to an element outside of your control. 

**relative**

> This type of positioning is probably the most confusing and misused. What it really means is "relative to itself". If you set ```position: relative``` on an element but no other positioning attributes (top, left, bottom or right), it will no effect on it's positioning at all, it will be exactly as it would be if you left it as ```position: static``` But if you DO give it some other positioning attribute, say, top: 10px;, it will shift it's position 10 pixels DOWN from where it would NORMALLY be. There are **two** other things that happen when you set ```position: relative``` on an element that you should be aware of. _One_ is that it introduces the ability to use ```z-index``` on that element, which doesn't really work with statically positioned elements. _TheOther_ thing that happens is it limits the scope of absolutely positioned child elements. Any element that is a child of the relatively positioned element can be absolutely positioned within that block. This brings up some powerful opportunities to style the document.

**absolute**

>  This is a very powerful type of positioning that allows you to literally place any page element exactly where you want it. You use the positioning attributes top, left bottom and right to set the location. Remember that these values will be relative to the next parent element with relative (or absolute) positioning. If there is no such parent, it will default all the way back up to the <html> element itself meaning it will be placed relatively to the page itself.
The most important thing to remember, about absolute positioning is that these elements are removed from the flow of elements on the page. An element with this type of positioning is not affected by other elements and it doesn't affect other elements. This is a serious thing to consider every time you use ```position: absolute```. It's overuse or improper use can limit the flexibility of your site.

**fixed**

> This type of positioning is fairly rare but certainly has its uses. A ```position: fixed``` element is positioned relative to the viewport, or the browser window itself. The viewport doesn't change when the window is scrolled, so a fixed positioned element will stay right where it is when the page is scrolled, creating an effect a bit like the old school "frames" days. It makes a cool effect, can be useful, but needs to be thoroughly tested.

> More info and a good online site to learn CSS positioning ca be found [here](http://www.barelyfitz.com/screencast/html-training/css/positioning/).

* What are data SRCs? When would you use them?

> The data-src attribute is just one of the infinite set of data-* attributes, which have no defined meaning but can be used to include invisible data in an element, for use in scripting (or styling).
More info [here](http://html5doctor.com/html5-custom-data-attributes/) and [here](http://css-tricks.com/data-uris/)
The format it uses: 
```data:[<mime type>][;charset=<charset>][;base64],<encoded data>```
```<img src="data:image/png;base64,iVBOR..." />```
> Why to use it?
This way the image in inlined in the HTML and there is no extra HTTP request to retrieve it (other than scrpting or styling).


* What benefits you get by using a CSS preprocessor?

> A preprocessor allows additional leverage over CSS by providing additional syntax that delivers the following advantages:

1. Nested syntax
2. Ability to define variables
3. Ability to define mixins
4. Mathematical functions
5. Operational functions (such as “lighten” and “darken”).
6. Loops, conditionals
7. Joining of multiple files
8. Etc.

More info [here](http://blog.blakesimpson.co.uk/read/37-less-sass-the-advantages-of-css-preprocessing-explained) and [here](http://css-tricks.com/musings-on-preprocessing/)

* Why would you use unit testing?

> Every person can give his/her opinion (more sceptic or less) and also I can write tones of lines describing the benefits and non-benefits of unit testing (TDD), unfortunately I don't got (right now) plenty of time so I will post some links that talks very well about this topic. I had founded on stackoverflow, this sentence that describes it very well, with just a few lines/words.
I may also mention that all the tests I did before, where on Ruby (RSpec).

> `Man, I just love unit tests, I've just been able to make a bunch of changes to the way something works, and then was able to confirm I hadn't broken anything by running the test over it again...`

> More info:
[here](http://soundsoftware.ac.uk/unit-testing-why-bother/)
[here](http://stackoverflow.com/questions/67299/is-unit-testing-worth-the-effort)
and
[here](http://programmers.stackexchange.com/questions/88365/do-you-use-unit-tests-at-work-what-benefits-do-you-get-from-them)

* How would you accelerate an element by hardware and why?



