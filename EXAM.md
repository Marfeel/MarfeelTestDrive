### 1. Get DOM elements using Javascript selectors

* Select an __IMG__ element

	document.getElementsByTagName('img')[1];

* Select all __H2__ elements

	document.getElementsByTagName('h2');
	
* Select all __A__ elements that have the attribute _title_

	var a= document.getElementsByTagName('a');
	var j= 0;
	var allTitles=[];

	for(var i=0; i<a.length; i++){
		if(a[i].hasAttribute('title')){
	  		allTitles[j]=a[i];
	  		j++;
		}
	}

	console.log(allTitles);
	
* Select only the __IMG__ elements that are inside an __A__ element

	var a = document.getElementsByTagName('a');
	var imgInsideA =[];
	var j=0;
	var img;

	for(var i=0; i<a.length; i++){
		img = a[i].getElementsByTagName('img');
		if (img.length>0){
			imgInsideA[j]= img;
			j++
		}
	}

	console.log(imgInsideA);
	
* Select all elements with class _article_

	document.getElementsByClassName('article');
	
* Select all _article_ from the middle and right column, but not from the left column
	
	var central = document.getElementsByClassName('centralblock');
	var right = document.getElementsByClassName('rightblock');
	var allArticles =[];
	var k=0;
	var arts;
	var j;

	for (var i=0; i<central.length; i++){
		arts = central[i].getElementsByClassName('article');
		for(j=0; j<arts.length; j++){
	  		allArticles[k]=arts[j];
	  		k++;
		}
	}

	for (var i=0; i<right.length; i++){
		arts = right[i].getElementsByClassName('article');
		for(j=0; j<arts.length; j++){
		  allArticles[k]=arts[j];
		  k++;
		}
	}

	console.log(allArticles);

* Select the 4th and 5th _article_ from the left column

	console.log(document.getElementsByClassName('leftblock')[0].getElementsByClassName('article')[3]);
	console.log(document.getElementsByClassName('leftblock')[0].getElementsByClassName('article')[4]);

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



