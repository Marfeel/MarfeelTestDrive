### 1. Get DOM elements using Javascript selectors

All of the answers of this section are ad-hoc for the design of [El Confidencial](www.elconfidencial.com). They are not portable at all.

Just for future reference, I'm using [this design](https://web.archive.org/web/20150713011433/http://www.elconfidencial.com/) of the site, since it looks like they change designs every other day.

* Select an __IMG__ element

One-line selection of a random __IMG__ element:

    document.images[Math.floor((Math.random()*document.images.length))];
 
A little more optimal:

    var imgs = document.images;
    var imgLength = imgs.length;
    if (imgLength > 0){
        imgs[Math.floor(Math.random()*imgLength)]
    }
    else {
        console.log("Not enough img elements to choose from.")
    }
    
If we just don't care about what image we get, and we assume there will always be at least one image:

    document.images[0];


* Select all __H2__ elements

This looks quite like the previous exercise (if we understand that the previously used ```document.images``` is a shorthand for ```document.getElementsByTagName("img")```):

    document.getElementsByTagName("h2");
    

* Select all __A__ elements that have the attribute _title_

Just like the previous exercises, but applying a filter to the array.

Note that the ```[].slice.call()``` crap is to convert from HTMLCollection to Array, which has the ```filter()``` method.


    [].slice.call(document.links).filter(function(a){return a.hasAttribute("title")});

Since one-liners are cool but confusing, a little more verbose explanation:

    var links = document.links;
    var arrayedLinks = Array.prototype.slice.call(links);
    
    function hasTitle (element) {
        return element.hasAttribute("title")
    }
    
    var filteredLinks = arrayedLinks.filter(hasTitle);
    
    filteredLinks;

* Select only the __IMG__ elements that are inside an __A__ element

We get all the links in the document, and then iterate through them to get any descendant __IMG__, which are in turn pushed to a collector array.

    var arrayedLinks = Array.prototype.slice.call(document.links);
    var imagesInsideLinks = [];
    
    function collectImages (element) {
        var images = element.getElementsByTagName("img");
        if (images.length > 0){
            Array.prototype.push.apply(imagesInsideLinks, images)
        }
    }
    
    arrayedLinks.forEach(collectImages);
    
    imagesInsideLinks;
    
* Select all elements with class _article_

As simple as getting tags, but changing the function to ```getElementsByClassName()```.

    document.getElementsByClassName("article");
    
    
However, I don't know if it's a trick question, or an involuntary trick question, but the webpage of [El Confidencial](www.elconfidencial.com) no longer uses the outdated ```<div class="article">``` but the more semantic and recommended tag of ```<article>```, so the query for ```document.getElementsByClassName("article");``` returns an empty collection. To get all the articles, we should use:

    document.getElementsByTagName("article");

* Select all _article_ from the middle and right column, but not from the left column

Again, one of the challenges of this question is not so much the js itself (I would get something like the central and right columns looking for ```class="centralblock"``` and ```class="rightblock"```, then looking for ```class="article"``` within it's children), but actually knowing the design you are asking about. The design they have nowadays doesn't really have 3 columns, so it's kind of hard to answer this question.

But I'm a resourceful person, so going to [The Way Back Machine](https://archive.org/web/) I looked for some old design resembling 3 columns (like [this randomly chosen one](https://web.archive.org/web/20150208124132/http://www.elconfidencial.com/)), and answered the question on that design.

    var centrals = Array.prototype.slice.call(document.getElementsByClassName("centralblock"));
    var rights = Array.prototype.slice.call(document.getElementsByClassName("rightblock"));
    
    var unitedChildren = centrals.concat(rights); // All the relevant children without filtering.
    var nonLeftArticles = [];
     
    function collectArticles (element) {
        var articles = element.getElementsByClassName("article");
        if (articles.length > 0){
           Array.prototype.push.apply(nonLeftArticles, articles);
        }
    }
    unitedChildren.forEach(collectArticles);
    
    nonLeftArticles;

Note that this will only work on the old design I've chosen (or similar ones using classes like ```centralblock```, ```rightblock``` and ```article```). And even on this old design, they use a weird mix of ```<div class="article">``` and ```<article>``` which makes it hard to define the problem. I've made the choice to use the class name ```article``` (so it's different from the previous exercise and it looks like I know a little more).

* Select the 4th and 5th _article_ from the left column

The current design for [El Confidencial](www.elconfidencial.com) does not have a central or right column, but it maintains a legacy "left column" (called a _very semantic_ ```opening-1-left```... Why use something like "left-block" or "left-column"?) that still has articles, so I can solve this exercise in the current design.

Today they use ```div="group"``` plus ```div="section"```, but inside it all we can find the articles, so it's just a matter of accessing the 4th and 5th elements of that collection.

    var articles = document.getElementsByClassName("opening-1-left")[0].getElementsByTagName("article")
    
    console.log(articles[3]);
    console.log(articles[4]);
    
There is only a single element with class ```opening-1-left```, so I don't feel guilty at all at using a non-iterative way of accessing it with ```document.getElementsByClassName("opening-1-left")[0]```. After all, it's an ad-hoc solution specifically developed for this design.

* Select the logo of the website

By "logo of the website" I don't know if you mean the static logo on the top, or the fixed logo that gets displayed when you scroll. So I'll do it for both.

This are just ad-hoc solutions, so I've chosen the most simple way of selecting them: going to the site source and see what ```id```/```class``` they have chosen.

In this case, they have chosen the classes ```header-logo``` and ```header-fixed-logo``` for the static and fixed logos, respectively. So to select them, we just have to search for this classes:

    console.log(document.getElementsByClassName("header-logo")[0]);
    console.log(document.getElementsByClassName("header-fixed-logo")[0]);
 
 As a sidenote, me being the designer of this site, I would have probably chosen to use _id_ instead of _class_ , since this logos are unique in the site and it's faster to work with _id_ than _class_ , so at the end of the day, it would render faster (or at least, that's the theory. You'll never know with current engines, they work a little by magic, and the only way of truly knowing is to experiment. However, experimentation is outside the scope of this sidenote).
 
* Select all __IMG__ elements whose _SRC_ attribute is a _JPG_ file

Although using regex is probably a sub-optimal (performance-wise) way of doing this, I think the logic behind it's quite clear to understand. And this is an exam, so it's not a bad idea to show my usage of regex (and the fact that I actually know what regular expressions are, you'll be surprised by the amount of people who don't know them).

As previously, I believe that the easiest way of doing this is by using the ```filter()``` method, since the definition of the exercise is "filter the __IMG__ by its _SRC_ attribute". However, we find again that the ```filter()``` method is only found in arrays, so we have to cast the HTMLCollection to an Array.

    var images = [].slice.call(document.images);
    var jpgCheck = /\.jpg($|\?)/i; // Matches any string ended in .jpg (case insensitive). Accepts additional parameters, like "[...].jpg?mtime=[...]", which looks quite common in this site.
    
    function hasJpgSource (element){
        return jpgCheck.test(element.src)
    }
    
    var jpgImages = images.filter(hasJpgSource);
    jpgImages;
    
I like this way of writing code because it's quite self-explanatory: " _we filter the images checking if they have a jpg source_ " = ```images.filter(hasJpgSource)```.


### 2. Apply CSS to DOM

By "Apply CSS to DOM" I assume we are talking applying it with JS (since the position is _JS ninja_), and not superseding it with another stylesheet called later.

Since this section is mostly modifying the styles of the elements, I'll mostly use the ```element.style``` property.

* Change the main article header to FF0000

The main article is surrounded by tons of nested divs, but the one with the most semantic class to select would be ```special-top```. Then inside this ```div``` we find the headers, and the _jumbo_ header is not an ```h1``` as we could have guessed, but an ```h3``` (and the subheaders just under it, are ```h2```...). There are other ```h3``` inside ```special-top```, so we have to increase the specificity of our selection, in this case by getting a div with class ```art-info-complete``` (incredibly ad-hoc solution, if the programmers had used an ```h1``` as logic dictates, it would be quite easier). And empirically tested it needs even more specificity (in this case, the ```a```), so it ends up something like:

    document.querySelector(".special-top .art-info-complete h3>a").style.color = "#FF0000";

* Change page background color to green

This should be easy:

    document.body.style.backgroundColor = "green";
    
As it was expected, nothing works as it should (go ahead, try it), so to make it easy and fast (to write, not to process), let's go the overkill way and change **all** the backgrounds to _green_ .

    [].slice.call(document.querySelectorAll("*")).forEach(function(a){a.style.backgroundColor = "green"});

* Change subheaders to lowercase

Since, in the current implementation of the site, there are no subhaders (the only thing that look like subheaders are actually links to related articles, used to contextualize the current article), it's nearly impossible to solve this exercise.

However, if by "subheaders" you mean any _h*_ that is not actually an __H1__ (so: __H2__, __H3__, __H4__, __H5__ and __H6__), then:

    [].slice.call(document.querySelectorAll("h2,h3,h4,h5,h6")).forEach(function(a){a.style.textTransform = "lowercase";});

Actually, following the same pattern, we only need to query the correct selector, so the function would be the same, just changing the selector ```"h2,h3,h4,h5,h6"``` to whatever selector defines the subheaders.

* Hide opinion column

It's currently defined by the unique class ```border-sides-blog```, so:

    document.querySelector(".border-sides-blog").style.visibility = "hidden";

However, I like it more when the thing I hide disappear completely, even if it's not strictly _hide_ as the exercise proposes:


    document.querySelector(".border-sides-blog").style.display = "none";


* Make top Ad banner sticky at the bottom

For some unknown reason, the top Ad banner is wrapped in a __div__ with a unique class ```hide-ad```, so I'll use that to change its position to a fixed and then move it to the bottom.

    document.querySelector(".hide-ad").style.position = "fixed";
    document.querySelector(".hide-ad").style.bottom = "0";


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



