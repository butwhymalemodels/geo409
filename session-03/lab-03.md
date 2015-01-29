# Module 03: Basics of Web Design: HTML, CSS
## Overview
In this lab we will do the following:

* Get familiar with the Brackets text-editor and its live-preview capabilities.
* Understand the different roles html, css and javascript play and make changes to each of them without (hopefully!) breaking our web page. (But if we do break it, we'll figure out how to fix it

## Brackets

After completing Task A, you should have a project repository that can be found online at github.com/yourusername/geo409 as well as on your lab computer or laptop. Within it, you should have the following directory structure:

![](assets/Screenshot%202015-01-20%2012.55.40.png)


As our next homework is called Task B, **let's go ahead and duplicate the task-a directory and call it task-b**. Do this on your local machine rather than the Github webpage. Remember you can do this as you would copy any file on your machine (via Finder or File Manager). Once you make a local copy of the directory (and the files within) you should sync the local version up with the online files.

**This is a key part of the web mapping workflow. So go to your Github client and go ahead and commit this to our git repository as well.** Remember how to do this?

![](assets/Screenshot%202015-01-21%2023.39.39.png)

Now we're ready to roll! We have a new directory (Task B) and it is replicated on the local machine and the web. 

Open Brackets and use File | Open Folder to open the index.html file in the Task B folder in the local geo409 repository in Brackets. This is the map centered on Lexington with your name you made in Task A.

Let's get to know the various parts of Brackets a little better.

![](assets/Screenshot%202015-01-21%2023.40.33.png)

In the left column, we can see all the files and subfolders within our project folder (see how we are in the task-b directory and editing the index.html file). This allows you to navigate around the various files within a project without having to go back into the project folder in Windows or Mac OS. Of course, the central part of the application is reserved for actually displaying and editing the text files. 

Looks straight-forward enough, but there's actually a number of handy features implemented beneath the surface. We'll keep you in suspense on those for now -- you'll see them in the next section of the lab. After all, anticipation is a lot of the fun.

Have a look at the right menu bar/panel first. It has a number of little icons, the top-most being a lightning bolt. The lightning bolt opens up a **live preview** of the current document. Go ahead and click on it. This will open a Chrome window with your webpage! See it is the map from Task A. Any change we'll now make to the underlying HTML and CSS will automatically update in Chrome as well. So it is really useful for making a small change and seeing what happens to your map. 

---

**STUFF FOR YOU TO TRY** 

---

For now, arrange both windows next to each other so you can see them at the same time:

![](assets/Screenshot%202015-01-21%2023.53.03.png)

Try out the live preview by looking for the bit where it says "Map Title" (line 52) in task-b/index.html and change it to something more personal. Like, **Lexington: Home of the IGUANAS.**

So cool! Don't you just love online mapping?  And Iguanas too, of course.

## HTML

It turns out, that all modern online maps use the same building blocks: html, css and javascript. And not a single online map is made without using HTML. The hypertext markup language is at the very core of the world wide web -- structuring each and every webpage you visit -- and online maps are web pages too, using HTML in much the same way.

Text you find in an online newspaper, or this very lab, is always structured. There are titles, subtitles, headings and subheadings; normal paragraphs and footnotes. Each of these are elements, often visually distinct, that make up the larger whole (much like how the scales, claws, body and tail make up the larger iguana). On the web, html indicates where in the hierarchy each element stand and a html file is nothing more than a normal text file that uses that special hypertext markup language (or coding) to structure text. HTML is just another form of *structured content*.  (And keeping up with the iguana analogy, an iguana (or any lizard for that matter) is in some ways just another form of structured anatomy.)

In this case, our index.html is such a file. The things in blue, between the angled brackets (<>), are called tags and they indicate which type of element they enclose. Each elements always starts with a tag that has the name of the element between brackets -- `<element>` -- and is ended by repeating that name but now adding a forward-slash -- `</element>`. For example, `<h1>My First Map</h1>`. An html page always starts with an html element `<html>` that indicates that indeed we’re going to write html. It is followed by `<head>`, which holds all the information that isn’t displayed on the page perse, but is about the page. This is also the place we find all of the CSS styling between `style` tags. Finally, but most importantly, there is a `<body>` element that includes anything and everything that is shown on the actual webpage.

Sadly, no one has implemented an `<iguana>` tag `</iguana>` in html yet. Not sure what it would do but it would no doubt be cool. Just like Iguanas.

Our body has a `header` with two titles -- `h1` for the main title and `h2` for the subtitle. It then continues with a `div` element. Div is kind of a weird beast (very non-iguana like)-- it defines a specific division or section of a webpage and is completely flexible. Do you see how this div has an `id=map` addition. This gives this division an identifier called 'map'. This is really handy, for example if we wanted to include two maps on the same page, we could create two separate div elements one with `id=map1` and the other with `id=map2`. And because these are user defined (except for some restricted terms) we could even use an `id=jacktheiguana` if we wanted to. Although that will likely be a bit confusing so best to keep with more logical terms like 'map' for now.

Apart from an identifier, elements can also have a 'class' attribute. An identifier always uniquely identifies a specific element (like map1, map2 or jacktheiguana) but a class can be used on multiple elements. Another way to think about this is that iguana is a class (there can be many iguanas) but jacktheiguna is an identifier because there can only ever be one Jack the Iguana, because he's supercool. Don't break a sweat on this right now though as we'll get intimately familiar with classes and identifiers soon enough. Lastly, our page has a `footer` that consists of three paragraphs (that's that `<p>` tag).

At the very end of the body we also see some javascript popping up -- always between `<script>` tags -- but ignore that for now. We are going to change around some of the HTML first. Let's say we wanted to add another paragraph right below the 'Map authored by...' one -- how would you do that? Go ahead and try it out. Once you start typing, you will notice that Brackets gives you auto-complete suggestions. Very handy later on but now we only need to type a single letter anyways. Once you've typed `<p>` you will notice that Brackets automatically provides the closing tag. 

This is really great as it makes sure we don't forget it later on. This is important because if you forget the closing tag you'll get error and the page won't load.

Finish up typing your paragraph. If you move your cursor to the next `<p>` on (line 61) you also see that Brackets always highlights the corresponding closing tag. This is helpful is spotting mistakes. In fact, if you go to line 62, you will notice a small typo: it doesn't have a closing tag.

---

**STUFF FOR YOU TO TRY**

---

Correct the error so it looks like the below and make sure you save and commit your progress.

![](assets/Screenshot%202015-01-22%2000.21.39.png)

One more thing. If you have ever used the internet before, you might have noticed that one of the core ingredients is the fact that we can link to other sites from our webpage. To include a link, we use an `a` tag in the following way:

```
<a href="http://mycoolwebsite.com">Visit My Website</a>
```

We'll be using the `<a>` tag and href a lot, so be aware.

## CSS

Cascading Stylesheets, or CSS, is how we style or design the structure that HTML provides. If HTML is the rough build of a house (or the skeleton of the Iguana) -- the two-by-fours and drywall -- then CSS is the paint on the walls, the granite on the countertops, and, if you’re so inclined, the artistic and soulful renderings of sheep portraits hung on the walls. Or the soulful eyes and emerald skin of Jack the Iguana.

There are two ways to include CSS in a website. The first is through an external stylesheet. This is really useful when your stylesheets and projects become bigger; imagine the clutter! Right now we’re using a standard stylesheet but in later modules we’ll discuss how you can make your own. Loading a style sheet is always done by using the `<link>` tag with two attributes: a ‘rel’ attribute that states that we’re dealing with a stylesheet, and a ‘href’ attribute giving the external location of our stylesheet. You can see this at work on line 10 -- here we load an external stylesheet called leaflet.css. It is doing some default, advanced styling for the map on our page. All of our own styling uses a second way of including CSS, through the use of the `<style>` tag.

CSS has a slightly different syntax from HTML and doesn’t have opening and closing tags, but rather consists of a *selector* that refers to a specific HTML element, and then a *declaration* that is always enclosed in curly brackets. 

![](assets/selector.gif)

```
h1 {
    color: red;
}
```

The CSS declaration above itself has a property (‘color’) and a value (‘red’) that are separated by a colon. It’s a deceivingly simple set-up but with these building blocks web designers make the most beautiful and intricate web sites. For our purposes, CSS is important because, just as we style the `<h1>` and `<h2>` headings on a webpage, we can use CSS to style our map elements as well.

---

**STUFF FOR YOU TO TRY**

---

Let's change up the styling of our page a bit! First off, let's change the height of the actual map to 440 pixels. Where do you think you do this.

Did you see the map change in your live preview as well? You will also notice that the the map selector is preceded by a hashtag (#). This is CSS-speak for 'identifier', i.e. `#map` refers to the html element with identifier 'map'. If there's no hash, this means we're refering an actual html element type, i.e. `p {}` refers to all `<p>` elements.

We also like to change the color of the subtitle (or the `<h2>` element to a lighter gray. You notice that the color is defined in this weird way: #001323. This is called hex-notation and is the way computers define colors. Not very human friendly but  Brackets has a nifty feature to help you here. Move your cursor to the color definition (the actual text that says #001323) and press CMD/CTRL-E. A color picker will emerge and moving around the color will update the live-preview as well. Pick a nice, light gray and press 'X' and the hex-notation for `<h2>` will automatically change. That's Iguanarific!!

![](assets/Screenshot%202015-01-22%2000.42.14.png)

You can use a similar trick to update a styling rule while working down in the HTML section. For example, move your cursor to the paragraph element on line 60 that you added earlier and press CMD/CTRL-E again. This pops up the exact section of our styling that refers to that element (the `<p>` element). Use it to change the font size to 0.9em.

![](assets/Screenshot%202015-01-22%2000.45.50.png)

Now let's assume we want to change the styling of the first paragraph. As it indicates the author, it would be nice if it stood apart a little from the other paragraphs. But we have a bit of a problem here as the styling under `p {}` refers to all our paragraphs. This is where we can use the fact that we can add a class or identifier to html elements. In this case, we are going to add a class attribute to the element at line 59:

```
<p class='author-info'>Map authored by Ate Poorthuis</p>
```

At the bottom of our style definitions we can now add a new selector that refers to this class. Just as hash (#) referred to the identifier attribute, we use a period (.) to refer to the class attribute. So to select only p elements with class 'author-info', we can do the following:

```
        p.author-info {
            /* style goes here */
        }
```

You can imagine there are dozens of different styling options and definitions. It's impossible to learn them all by heart and often the web can provide an answer within seconds. At the end of this lab, you will see a couple of additional resources that provide a good starting point, but often a quick Google search provides the answer we need. 

---

**STUFF FOR YOU TO TRY** 

---

Let's say we want to make the font style in our paragraph italic. Can you figure out which property to use here? Construct a sensible Google search to help you find the correct css definition to turn the font in that paragraph italic. *Save your changes and commit your changes to your repository.*

## Commenting

Often you want to include a note or a comment within your code that you do not necessarily want to *render* inside of your webpage. This could be because you need a placeholder, provide some explanation to your code or just make a note to which you'll come back later. Actually, the CSS code that we just looked at had such a comment in place:


```
        p.author-info {
            /* style goes here */
        }
```

Comments in CSS styling always have the same structure -- they start with `/*` and then are closed by `*/`. Everything in between is not evaluated or rendered by the browser. Sadly, commenting works slightly different in html and javascript. In HTML we comment in a slightly different way.

`<!-- Your comment goes here -->`

A very useful way of using commenting is by commenting out a particular line or style declaration to see its effects in the live preview. For example, move your cursor to the line where you declare the font style of the author-info paragraph to be italic. Then, hit CMD/CTRL-/. It will automatically comment the entire line and you should see the live preview update immediately!

## Javascript

Finally, it is Javascript that allows webpages to change dynamically, based on data or interaction from a user. Javascript can be loaded from an external file, just like CSS. We see this in our index.html page in the `<head>` of the document:

```
<script src="http://cdn.leafletjs.com/leaflet-0.7.3/leaflet.js"></script>
```

This loads the external Leaflet mapping library. We can also include our own custom Javascript in between `<script>` tags, which is what you see in the latter part of our index.html file. We will go into the inner workings of that code in the next lab but for now let's experiment a little with it.

---

**STUFF FOR YOU TO TRY** 

---

Locate the following line in your html (around line 62) 

```
<div id='map'></div>
```

and change the identifier to something else, like jacktheiguana.

```
<div id='jacktheiguana'></div>
```

Check out the live preview. What happened? The map disappeared! Although we don't need to understand exactly how this works right now it is clear that the html structure is linked together with the Javascript that produces that map.  And a quick look at the code reveals some of the initial links between the two. For example, the following line of Javascript indicates what `<div>` our map should be built in. 
```
var targetDiv = 'map';
```
Once we changed the id of our div from 'map' into something else, Javascript simply couldn't find the right `<div>` any longer and was thus unable to construct the map. Changing it back to 'map' also brings back the actual map in the live preview!

Note: There are also connections between CSS and HTML and JavaScript! If for some crazy reason you really wanted to change the identifier from 'map' to 'jacktheiguana' (a rather silly idea, btw) you would actually have to change it in three separate places:

* the CSS, where the style is declared;
* the HTML where the div element is defined; and
* the JavaScript where it is run.

So you would have to change the following code.

**CSS**
```
#jacktheiguana {
            width: 80%;
            height: 440px;
            margin: 10px auto;
        }
```

**HTML**
```
<div id='jacktheiguana'></div>
```

**JavaScript**
```
var targetDiv = 'jacktheiguana';
```

## Homework: Task B

1. Update the HTML so that the footer has two headings ('About this map' and 'Data Sources'). You want to make sure that these headings are not as large as the headings used for the title. Use the web to find out what other heading elements HTML has to offer. Give these headings the same color as the `<h2>` subtitle
2. Align the text of the author paragraph to the right through updating the p.author-info CSS rule. Take this opportunity to slightly decrease the font-size as well.
3. Include a link to your Github repository in the data sources section. You can use the `<a>` tag to do this -- if you're confused you can read up on how to do this at [W3 Schools](http://www.w3schools.com/tags/tag_a.asp). You will see that the default way to style links is using a bright blue color. Change this color to the same gray as the subtitle and make the weight of the font bold (think of a smart query to Google the right way to do this).
4. Your resulting page should look similar to ![](assets/Screenshot%202015-01-22%2011.21.04.png)
5. Commit your changes and, together with the commits you made earlier in the lab, sync your commits to the online repository.
6. Submit the github.com url of your repository to Canvas

**Addition Resource**
* [W3C Schools](http://www.w3schools.com/): accessible and useful resource for learning and referencing a variety of web languages (HTML, CSS, JavaScript)
* [CodeAcademy](http://www.codecademy.com/): online, interactive environment for learning a variety of web programming languages such as HTML, CSS, and JavaScript
* [Mozilla Developer Network](https://developer.mozilla.org): comprehensive resource for all things web, including guides and tutorials for [HTML](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML) and [CSS](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS)

**Definitions**

* HTML: HyperText Markup Language is the text-based markup language used describe all documents (i.e., pages) and document elements on the World Wide Web
* CSS: Cascading Style Sheets define how HTML elements are displayed (e.g., their size, color, or position)
* JavaScript: the modern (current) programming language of the Web
* Tag (HTML): a component of HTML that represents one node within a hierarchy of nodes, normally composed of an opening and closing tag which contain content within
* attribute: used to provide additional information about an HTML page, normally included within the opening tag (e.g., id, class, href)
* id (HTML): an attribute that specifies a unique identifer for a particular HTML element 
* class (HTML) an attribute that specifies a class (i.e., similar category) for a number of HTML elements, allowing CSS rules to be uniformly appled to them
* Selector (CSS): allows CSS to "find" HTML elements based on an attribute such as an id or class, and to apply style rules or otherwise manipulate the element (as through JavaScript)
* Declaration (CSS): component of a CSS rule comprising a property (e.g., color) and a cooresponding value (e.g., blue)

