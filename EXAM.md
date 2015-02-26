### 1. Get DOM elements using Javascript selectors

* Select an __IMG__ element

>I take the third image of the HTML collection:
>>document.getElementsByTagName('img')[2]

* Select all __H2__ elements

>>document.getElementsByTagName('h2')

* Select all __A__ elements that have the attribute _title_

>I take all the a elements into the array 'links'
>>var links = document.getElementsByTagName('a')

>I create an empty array 'titleLinks' to store __A__ elements with _title_
>>var titleLinks = []

>I define a function to iterate 'links' array and store __A__ elements with attribute _title_ in 'titleLinks'
>>function select_a_with_title(){    
>>var i=0;    
>>while(i < links.length){    
>>if(links[i].hasAttribute('title') === true){    
>>titleLinks.push(links[i]);    
>>};    
>>i++;   
}    
}

>I call 'select_a_with_title'
>>select_a_with_title()

>Now titleLinks stores all the __A__ elements with attribute _title_

* Select only the __IMG__ elements that are inside an __A__ element

>I select __IMG__ elements and keep the in 'imgs' variable
>>var imgs = document.getElementsByTagName('img')

>I create the 'a_imgs' empty array
>>var a_imgs = []; 

>I declare a function called 'select_imgs_in_a' to store all __IMG__ in the document with a parent __A__   
>>function select_imgs_in_a(){    
>>for(i=0;i<imgs.length;i++){    
>>if(imgs[i].parentNode.nodeName === 'A'){    
>>a_imgs.push(imgs[i]);    
>>};    
>>};    
>>};    

>I call the function 'select_imgs_in_a'
>>select_imgs_in_a();

>Now a_imgs stores all the __IMG__ elements with attribute _title_

* Select all elements with class _article_

>>document.getElementsByClassName('article')    
>This returns an empty array so there are not elements with class _article_

* Select all _article_ from the middle and right column, but not from the left column

>>var divs = document.getElementsByTagName('div');    
>>var sections = document.getElementsByTagName('section');    

>>var center_or_right_containers = [];    

>>function search_in_class(element, word){      
>>  for(var i=0; i<element.length; i++){    
>>  	if((element[i].className.search(word) === -1) === false){    
>> 		center_or_right_containers.push(element[i])    
>>  	};    
>>  };    
>>};    

>>search_in_class(sections,'right');    
>>search_in_class(sections,'center');    
>>search_in_class(divs,'aside');    

>>var center_and_right_articles = [];    

>>function take_articles(){    
>>	for(var i=0; i<center_or_right_containers.length; i++){    
>>		var all_childs = center_or_right_containers[i].getElementsByTagName("*");    
>>    for(var j=0; j<all_childs.length; j++){    
>>    	if(all_childs[j].nodeName === 'ARTICLE'){    
>>    		center_and_right_articles.push(all_childs[j]);    
>>    	};    
>>    };    
>>  };    
>>};    

>>take_articles();    

>>center_and_right_articles;          

* Select the 4th and 5th _article_ from the left column

>>left_section = document.getElementsByClassName('opening-1-left')[0];    

>>left_section.childNodes[0].childNodes[3];    
>>left_section.childNodes[0].childNodes[4];    

* Select the logo of the website

>>divs = document.getElementsByTagName('div');    

>>var logo_elements = [];    

>>function search_in_class(elements, word){    
>>for(var i=0; i<elements.length; i++){    
>>  	if((elements[i].className.search(word) === -1) === false){    
>>  		logo_elements.push(elements[i])    
>>  	};    
>>  };    
>>};    

>>search_in_class(divs, 'logo');    

>>logo_elements[1];    

* Select all __IMG__ elements whose _SRC_ attribute is a _JPG_ file

>>var imgs = document.getElementsByTagName('img');     

>>var jpg_imgs=[];    

>>function search_in_src(word){    
>>	for(i=0;i<imgs.length;i++){    
>>		if ((imgs[i].getAttribute('src').search(word) === -1) === false){    
>>      jpg_imgs.push(imgs[i]);    
>>		};    
>>	};    
>>};     

>>search_in_src('.jpg');   
 
>>jpg_imgs;    


### 2. Apply CSS to DOM

* Change the main article title to FF0000

>>document.getElementsByClassName('art-tit')[0].childNodes[0].textContent = "FF0000";    

* Change page background color to green

>>document.getElementsByTagName('body')[0].setAttribute('style','background-color:green;');    

* Change subtitles to lowercase

>>

* Hide opinion column

>>var opinion_column = document.getElementsByClassName('opening-1-right-bottom-right')[0];    

>>opinion_column.setAttribute('style','visibility:hidden;');    


* Make top Ad banner sticky at the bottom

>>var body = document.getElementsByTagName('body')[0];    

>>body.setAttribute('style', 'position:relative;');    

>>var add_banner = document.getElementById('dfp-home-site');    

>>add_banner.setAttribute('style', 'position:absolute; bottom:-80rem'); //It should be enough with bottom:0rem; but the banner doesn't go to the right bottom.    

### 3. DOM Manipulation with Javascript

* Add a 10px red border around all __IMG__ elements
 
>>imgs = document.getElementsByTagName('img');    

>>function border_image(){    
>>  for(i=0;i<imgs.length;i++){    
>>  	imgs[i].setAttribute('style','border: 10px solid red;');    
>>  };    
>>};    

>>border_image();    

* Fade out all __IMG__ elements

>>function fadeOut(el){    
>>el.style.opacity = 1;    

>>  (function fade() {    
>>    if ((el.style.opacity -= .1) < 0) {    
>>      el.style.display = "none";    
>>    } else {    
>>      requestAnimationFrame(fade);    
>>    }     
>>  })();     
>>};     

>>imgs = document.getElementsByTagName('img');     

>>function fade_elements_array(){     
>>  for(i=0;i<imgs.length;i++){     
>>  	fadeOut(imgs[i]);     
>>  };     
>>};     

>>fade_elements_array();     

* Add a 10px red border around all __IMG__ and fade out the images after 3 seconds

>I am using jQuery in this excercise because I do not find the way to fade out  after 3 seconds in pure javaScript and I prefered to do it in jQuery and not to leave the excercise empty.        
>>function border_image(element){    
>>  for(i=0;i<element.length;i++){    
>>  	element[i].setAttribute('style','border: 10px solid red;');     
>>  };     
>>};     

>>$(document).ready(function(){    
>>	border_image($('img'));     
>>  $('img').fadeTo(3000,0);     
>>});     

### 4. Answer the following points

* Justify the chosen method used to hide opinion column

>I prefer to use visibility:hidden because this way I hide the element but it still occupies its space on the layout so if other elements depends on it, they keep their position too.

* Explain the difference between position static, relative, absolute and fixed

> Static is the default vale, and elements are rendered in order as the html document is loaded. Relative means the element is relative to itself, to its present position. Absolute means that the element is relative to a parent element with relative position. Static means the position is relative to the browser.

* What are data SRCs? When would you use them?

>They are attributes to specify the source file url where the element is loaded from. They are used in image tags, in script tags(if the script is in another file), in style tags (to load a css file), etc.  

* What benefits you get by using a CSS preprocessor?

>As I have worked with SASS preprocessor, I can say there are several benefits like using variables, nesting classes into other classes, using mixins to keep portions of greater code then variables and simplifying classes inheritance with selector inheritance.

* Why would you use unit testing?

I have used RSpec in Ruby on Rails apps and it is a very good way to test the code in different situations to know when it can breaks.

* How would you accelerate an element by hardware and why?

I would use transform: translateZ(0) to improve the performance when a CSS animation is loaded, for example. Today most computers, smartphones, tablets, etc, have cards or components for hardware acceleration. However, I would use methods to enable graphic acceleration only on spicific animations in order to not use excesive ram.





