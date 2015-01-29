### 1. Javascript selectors

* Select an __IMG__ element:  __$('IMG')__
* Select all __H2__ elements  __$$('IMG')__
* Select all __A__ elements that have the attribute  __$$('a[title]')__
* Select only the __IMG__ elements that are inside an __A__ element  __$$('IMG','a')__
* Select all elements with class __article__  __$$('.article')__
* Select all _article_ from the middle and right column, but not from the left column __$$('colB .article, .colA.right .article')__
* Select the 4th and 5th _article_ from the left column __$$('.colAB.three .colA .article:nth-child(4),.colAB.three .colA .article:nth-child(5)')__
* Select the logo of the website __http://www.elconfidencial.com/favicon.ico__
* Select all __IMG__ elements whose _SRC_ attribute is a _JPG_ file __$$('img[src$=".jpg"]')__

### 2. Apply CSS

* Change the main article title to FF0000, __right click on title, inspect element, .front .article:hover h2 a {color:#FF0000;__
* Change page background color to green __Select main html tag, change: background: green;__
* Change subtitles to lowercase __.article .subtitle {text-transform: lowercase;}__
* Hide opinion column __class = "group opinion" style="{display:none;}"__
* Make top Ad banner sticky at the bottom __class="ad" style="{bottom: 0;}__

### 3. Javascript

* Add a 10px red border around all __IMG__ elements  __$("img").css("border","solid #FF0000 10px");__
* Fade out all __IMG__ elements __$('IMG').fadeOut("fast");__
* Add a 10px red border around all __IMG__ and fade out the images after 3 seconds __$("img").css("border","solid red 10px").delay(3000).fadeOut();__


### 4. Explain the difference between position static, relative, absolute and fixed

Static is the default position value for all elements. The element is positiones normally in the page after the previous one.

Relative positions the element with respect to its sorrounding elements (“left”, “top”, “bottom” or “right” attributes) without affecting the positioning of other elements. If position attributes are not described the relative element acts as a static one.

Absolute places the element in the exact defined position. Position is set issuing “top”, “bottom”, “left” and “right” attributes. Values are relative to the previous parent element with relative (or absolute) positioning. Elements with this positioning are not affected by other elements and they do not affect other elements. 

Fixed elements are positioned relative to the browser's window itself. Fixed positioned elements stay right where are defined when the page is scrolled in the fashion of a top frame.


### 5. What are data SRCs? When would you use them?
Data-SRC is a set of the data-* attribute that have no defined meaning but can be used to include invisible data in an element, for use in scripting (or styling).

### 6. What benefits you get by using a CSS preprocessor?
Preprocessors allows additional leverage over CSS by providing additional syntax that delivers the following advantages: Nested syntax, Ability to define variables, Ability to define mixins, Mathematical functions, Operational functions (such as “lighten” and “darken”), Joining of multiple files.





