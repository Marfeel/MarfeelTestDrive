### 1. Get DOM elements using Javascript selectors

* Select an __IMG__ element

>I take the third image of the HTML collection:
>>document.getElementsByTagName('img')[2]

* Select all __H2__ elements

>>document.getElementsByTagName('h2')

* Select all __A__ elements that have the attribute _title_

>I take all the a elements into the array 'links'
>>links = document.getElementsByTagName('a')

>I create an empty array 'titleLinks' to store __A__ elements with _title_
>>titleLinks = []

>I define a function to iterate 'links' array and store _A_ elements with attribute _title_ in 'titleLinks'
>>function select_a_with_title(){    
>>i=0;    
>>while(i < links.length){    
>>if(links[i].hasAttribute('title') == true){    
>>titleLinks.push(links[i]);    
>>};    
>>i++;   
}    
}

>I call 'select_a_with_title'
>>select_a_with_title()

>Now titleLinks stores all the __A__ elements with attribute _title_

* Select only the __IMG__ elements that are inside an __A__ element
* Select all elements with class _article_
* Select all _article_ from the middle and right column, but not from the left column
* Select the 4th and 5th _article_ from the left column
* Select the logo of the website
* Select all __IMG__ elements whose _SRC_ attribute is a _JPG_ file

### 2. Apply CSS to DOM

* Change the main article title to FF0000
* Change page background color to green
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



