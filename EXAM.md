### 1. CSS Selectors

* Select an __IMG__ element

img[src="http://img02.lavanguardia.com/2013/10/07/Sarkozy-en-una-foto-tomada-el-_54390648732_54028874191_342_130.jpg"] {}

* Select all __H2__ elements

h2{}

* Select all __A__ elements that have the attribute _title_

a[title] {}

* Select only the __IMG__ elements that are inside an __A__ element


a img {}

* Select all elements with class _lv24noticia_

.lv24noticia{}

* Select all _l24noticia_ from the middle and right column, but not from the left column

.l24noticia tr td:nth-of-type(2) ~ td{}

o

.l24noticia tr td:nth-of-type(2),.l24noticia tr td:nth-of-type(3) {} 


* Select the 4th and 5th _lv24noticia_ from the left column

.l24noticia tr td:nth-of-type(4) ~ + td + td + td + td, .l24noticia tr td:nth-of-type(4) ~ + td + td + td + td +td {}

* Select the logo of the website

.h1 a[title=La Vanguardia.com]


* Select all __IMG__ elements whose _SRC_ attribute is a _GIF_ file

img[href$ = ".gif"]{}

* Select all elements that are __NOT__ inside the three columns

.l24noticia tr td:nth-of-type(4) ~ td{}


### 2. Pick any __IMG__ and __A__ element and replace them for any other element of your choice

img[src="http://img02.lavanguardia.com/2013/10/07/Sarkozy-en-una-foto-tomada-el-_54390648732_54028874191_342_130.jpg"] = {
src="http://img01.lavanguardia.com/2012/09/04/David-Bowie-posando-para-la-po_54346300267_51351706917_600_226.jpg";
}

a[href = "http://www.lavanguardia.com/internacional/index.html"] = {href = "http://www.lavanguardia.com/deportes/mundial-2014/index.html";}

### 3. What is CSS minification?

CSS minification means removing every space, comment or any non useful character for the code execution. This is mainly done for reducing the file size.

### 4. What is CSS compression?

It means reducing the file size by algorithmic methods.

### 5. Explain the difference between position static, relative, absolute and fixed

A static position is the default positioning of html, every new element will be positioned one after another. A relative instead will also follow the natural flow but 

the position defined will be relative to the what it would be in static. Absolute positioning, otherwise, let's positining the element wherever you like from the 

viewport. Lastly, any fixed element will act as an absolute positioned element but it will be in the viewport for every new page and any element will scroll past it.

### 6. What are data URIs? When would you use them?

Data URIs are a link to an image embedded directly to the CSS file. This is useful when trying to load images because it avoids doing http requests for each image.

### 7. Using jQuery...

* Add a 10px red border around all __IMG__ elements

$(“img”).css(“border: 10px solid red”);
 
* Fade out all __IMG__ elements

$(“img”).fadeOut();

* Add a 10px red border around all __IMG__ and fade out the images after 3 seconds

function(){
	$(“img”).css(“border: 10px solid red”);
	$(“img”).delay(3000).fadeIn();
}); 
