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


### 3. What is CSS minification?

### 4. What is CSS compression?

### 5. Explain the difference between position static, relative, absolute and fixed

### 6. What are data URIs? When would you use them?

### 7. Using jQuery...

* Add a 10px red border around all __IMG__ elements 
* Fade out all __IMG__ elements
* Add a 10px red border around all __IMG__ and fade out the images after 3 seconds
