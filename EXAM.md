### 1. CSS Selectors

* Select an __IMG__ element

img.formato224x130 {
	...
}
* Select all __H2__ elements

h2{
	...
}
* Select all __A__ elements that have the attribute _title_

a[title]{
	...
}

* Select only the __IMG__ elements that are inside an __A__ element

a img{
	...
}

* Select all elements with class _lv24noticia_

.lv24noticia{
	...
}

* Select all _l24noticia_ from the middle and right column, but not from the left column

.colB .l24noticia, .colA.right .l24noticia{
	...
}

* Select the 4th and 5th _lv24noticia_ from the left column

.colAB.three .colA .l24noticia:nth-child(4),.colAB.three .colA .l24noticia:nth-child(5){
	...
}

* Select the logo of the website

.header .h1{
	...
}

* Select all __IMG__ elements whose _SRC_ attribute is a _GIF_ file

img[src$=".gif] {
	...
}

* Select all elements that are __NOT__ inside the three columns

* :not(.block){
	...	
}


### 2. Pick any __IMG__ and __A__ element and replace them for any other element of your choice

img.formato224x130 {
	visibility: hidden;
}
img.formato224x130:before{
	visibility:visible
	content: 'TEXTEXTEXT';
}
a {
	visibility: hidden;
}
a:before{
	visibility:visible
	content: 'This is new content, replacing existing content';
}


### 3. What is CSS minification?

a minified CSS is a css where have been removed all white spaces, and duplicate code has been re-organizated, in order to reduce server consumption. I normally use http://cssminifier.com

### 4. What is CSS compression?

CSS compression means deleting all spaces in our styling code, in order to reduce its weights, but, unlike minification, there is no reorganization of our code (there are no deletions of duplicate code)

### 5. Explain the difference between position static, relative, absolute and fixed

- static 
Static is the default position value. The element flows normally in the page 

- relative
Relative position alows moving the element without affecting the position or behaviour of the other elements with the “left”, “top”, “bottom” or “right” attributes. If you don’t use that attributes, a relative positioned element actue like a static one.

- absolute
The page flow don’t take this element into account when organize all the elements position. Our element will be positioned in the top:0 and left:0 of his first relative positioned parent. You can (like in relative ones) change its absolute position with “top”, “bottom”, “left” or “right” attributes.

- fixed
When an element has “position:fixed”, it means that this element will be fixed in that position in the screen. The coordenates of its position, are set like in an absolute box, taking in count his first relatived positioned parent.
If an element is fixed, it will be at the same position although the user makes scroll or moves the window.



### 6. What are data URIs? When would you use them?

### 7. Using jQuery...

* Add a 10px red border around all __IMG__ elements 
* Fade out all __IMG__ elements
* Add a 10px red border around all __IMG__ and fade out the images after 3 seconds
