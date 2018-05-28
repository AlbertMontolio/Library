Create two files:

- index.html
- style.css

In `index.html` we will create the structure of the web page, the skeleton.

In `style.css` we will put the style.

In your index.html, if you write the word "doc" and press tab, you will get the common structure of an html file:

```html
<html>
<head>
  <meta charset="UTF-8">
  <title>Document</title>
</head>
<body>
  
</body>
</html>
```

In the head we put the metadata.

In the body what we want to show.

```html
<html>
<head>
  <!-- intelligence (metada-data) -->
</head>
<body>
  <!-- Stuff to display -->
</body>
</html>
```

In html you create elements of your page (titles, subtitles, paragrafs, etc) with tags

- h1, h2, h3, h4, h5, h6
- p
- img
- a

ul: unorder list
li

example slide

you can add some style to these tags with css


Live Code

Create h1 and h3 tags

Two clicks: open in browser

```html
<body>
  <h1>Web Developers & Tech- Teachers</h1>
  <h3>We create Web Applications.<br>We bring technology to passionate people.</h3>
  <h1>Projects</h1>
  <h1>Gallery</h1>
</body>
```

We have various h1, we have an h3. We see that we have spacing around the elements, and we didn't define it.



# Apply CSS

we want to custom the style of these headeres

let's do some css

```
/* style.css */
h1 {
  color: red;
}
```

to write comments we use `/* some comment */`

To style an HTML element, we use its name and curly braces. Inside, we explain through properties how this element should look like.

In our example, we want that the color is red.

if we go to our web page, nothing happened. The h1 are still black. Why?

We are defining the style in the style.css. The structure of the page is in the HTML file. There we have the head. The brain of our web. We need to tell the header, where is this css file.

```html
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <link rel="stylesheet" href="style.css">
</head>
```


Awesome! it's working

we can play with more CSS

```css
h1 {
  color: red;
  font-size: 60px;
  font-family: arial;
  background-color: pink;
}
```

Up to you to discover more.

Remember, you define the CSS-property, and you assign a value.

# Classes and Ids

Everything is great, but we are styling all the h1. What if I just want to style the first one?

I need it to select it somehow. That's why we use Ids. To select an HTML element, and give the style, just to this specific element

```html
<h1 id="title-banner">Web Developers & Tech- Teachers</h1>
```

That's the syntax, the keyword id, and the name that we want to give. the label.

in css, now we can point to this element. we can select this element

```css
#title-banner {
  color: orange;
}
```

Awesome. Now we know how to select one element. But what happens, if we have two titles that have the same style? Like Projects and Gallery

We use classes!

We select the elements that we want to style. Now, they are several

we use for example the class, secondary-headers, and we will apply some css rules in this class.

```html
<h1 class="secondary-headers">Projects</h1>
<h1 class="secondary-headers">Gallery</h1>
```

now, the CSS style that we apply to this class, will be applied to these two tags.

```css
.secondary-headers {
  color: blue;
}
```

you can change the color in the html browser.
Right click, inspect, and in the color, click and play



Awesome, now we can apply styles to multiple elements and to unique elements.

# Box model. Everything in boxes!

HTML is the structured. Best way to structure something, put every element in containers!

This containers are called divs.

Every container has a name, wheather an id-name or a class-name.

Let's create the structure of this first part of the web page, the banner!

```html
<body>

  <div class="title-wrapper">
    <h1 id="title-banner">Web Developers & Tech- Teachers</h1>
    <h3>We create Web Applications</h3>
    <h3>We bring technology to passionate people.</h3>
  </div>

</body>
```

in the browser nothing changed, but if we see the structure of our page, in the browser, we have our container!

Let's do the same for the top-navbar

```html
  <div class="top-navbar">
    <div class="company-name">
      DIGITAL TWINS
    </div>
    <ul>
      <li>COURSES</li>
      <li>ABOUT US</li>
      <li>CONTACT</li>
    </ul>
  </div>
```

we are done with the banner! almost! the banner is the big div! everything is inside

```html

  <div class="top-navbar">
    <!- [... insert top-navbar code ...] -->
  </div>

  <div class="banner">

    <div class="title-wrapper">
      <!- [... insert title-wrapper code ...] -->
    </div>

  </div>
```

we want to put some style. now we have everything structured, inside divs. but, we would like to put it in the right place right?

to posionated divs in our web page, we use two technologies:

- flexbox
- position relative, absolute

# Flexbox

flexbox is absolutely amazing. there is a lot of documentation. 

https://css-tricks.com/snippets/css/a-guide-to-flexbox/


The basics. you have a main div, the container, and you have elements inside that you want to allocate.

Let's center the title.

Before that, let's see our banner. let's put some background-color

```css
.banner {
  background-color: pink;
}
```

and now let's paint our title-wrapper

```css
.title-wrapper {
  background-color: green;
}
```

Ups, we see that the title-wrapper ocuppies all the banner. We want the banner to occupy all the screen right?

css code!

```css
.banner {
  background-color: pink;
  height: 100%;
  width: 100%;
  display: flex;
  justify-content: center;
}
```


we justify horizontally: we can use flex-start, flex-end

vertically?

```css
.banner {
  /* [...] */
  align-items: center;
}
```

# Space between elements, padding and margins

We can now positionaed what we want wherever we want. Some times we want more space between elements. 

This box model, you can put sapce inside the box, or you can move the boxes away from other boxes.

- padding: you put space inside the box

```css
.title-wrapper {
  padding: 20px;
  background-color: green;
}
```

or, we want to separate an element from the elements around him. let's separete the h1 from the other h3

first, we select the element, wheather with ids or classes. in this case, it has an id.

```html
<h1 id="title-banner">Web Developers & Tech- Teachers</h1>
```

```css
#title-banner {
  background-color: yellow;
  margin-bottom: 50px;
}
```

now, we are not putting space inside the element, but outside. there is no new space in the yellow box.

we are pushing elements aways.



now that you know about margins, what is going one with this white border? every html has this by default. look that the body engloves everything.

we need to kill it.

so, 

```css
body {
  margin: 0px;
}
```


# navbar, it's above. we want the navbar on top

we need to learn another way of positioning

# position: relative and position: absolute

we have the same situation, a big div, which contains elements inside that we want to positionated.

let's make a quick example

let's create the test element inside the banner

```html
  <div class="banner">

    <div id="test-positioning">
      albert
    </div>

    <!-- [...] -->
  </div>
```

in css

```css
.banner {
  /* [...] */

  position: relative;
}
```


```css
#test-positioning {
  position: absolute;
  top: 100px;
  right: 100px;
}
```

we pin the main container, we say, hej, you are fixed, you are the reference. you stay where you are. and the element that has the position abasolute, we can move it inside.

IMPORTANT. the element that has the position absolute, occupies no space.

that's key

let's do the same with our navbar

```css
body {
  position: relative;
}

.top-navbar {
  position: absolute;
  top: 0px;
  left: 0px;
}
```

we inspect, and it's there! but behind.

we just need to tell, hej, we want it above.

in CSS there is the z-index.

you order stuff in this axis

```css
.top-navbar {
  position: absolute;
  top: 0px;
  left: 0px;
  z-index: 2;
}
```

we are almost done with the structure. 

we need to finish the navbar

we want to align again the items of the navbar. they are in a ul. that would be the big container. inside there are li, we could use flexbox...

but, we will use a new concept.

it's time to introduce bootstrap.

bootstrap is a CSS-library. that means, you use things that are already made for you.

bootstrap it's just a huge CSS file, with a lot of classes defined.
you don't define the classes, you just use them

first of all, we need to have this huge file. how?

we get it from the internet. we just need the link, and put it in our head of the html file. the brain of our web


https://getbootstrap.com/docs/4.0/getting-started/introduction/

```html
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">
```

copy this in your head tag

the letters change a little bit. cool, signal that bootstrap is there.

now we can use stuff from them


list linline

```html
<ul class="list-inline">
  <li class="list-inline-item">Lorem ipsum</li>
  <li class="list-inline-item">Phasellus iaculis</li>
  <li class="list-inline-item">Nulla volutpat</li>
</ul>
```


now we want to positionate the elements. we know how to do that. we have the container, the topnavbar, and two elements inside, the company-name and the list

let's put first some colors, to see, and make the topnavbar with 100%.



```css
.top-navbar {
  /* [...] */
  width: 100%;
  background-color: yellow;
}

.company-name {
  background-color: blue;
}

#navbar-items {
  background-color: red
}
```

you see the structure

let's use a new property of flex, instead of justify-content: center

we have:

```css
.top-navbar {
  /* [...] */
  display: flex;
  justify-content: space-between;
}
```

it separates the elements

we have a small issue. bootstrap puts some margin-bottom in the ul, because he wants to do that. we don't, we kill it

```css
#navbar-items {
  background-color: red;
  margin-bottom: 0px;
}
```

let's put some spacing inside the topnavbar

```css
.top-navbar {
  /* [...] */
  padding: 40px 80px;
}
```

buala! the structure is beautiful

let's take out some ugly colors

# Video in the background. 

let's add the magic

now we are masters in positioning and styling, let's add the magic, a youtube video that will play automatically, loop automatically etc.

where do we put it? exactly. like the topnavbar, we want to put it in a different layer. we want to put it behinde the banner, behind the topnavbar


how?

let's put our first youtube video first in our page

you go to youtube, you search for a video

you go to share

you click embeded, it gives you the code

copy

we put it as the first element in our body

```html
<iframe width="560" height="315" src="https://www.youtube.com/embed/LAySCljzpAE" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
```

that's it. we have a nice video. it could be from us. we have to play the video, it's boring. and the video does not loop when it's done. and we listen to the sound.

you can pass some settings to achieve that

```html

<iframe id="bannerVideo" width="560" height="315" src="https://www.youtube.com/embed/LAySCljzpAE?loop=1&autoplay=1&playlist=LAySCljzpAE&showinfo=0&controls=0&start=4&rel=0&mute=1" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen class="banner-video"></iframe>
```

?loop=1&
autoplay=1&
playlist=LAySCljzpAE&
showinfo=0&
controls=0&
start=4&
rel=0&
mute=1

i looked them up for you :)


we want the video to be behind and occupy all the screen

let's give him an id and put some style


```css
#bannerVideo {
  width: 100%;
  height: 100%;
}

```

nice! almost there! now, if we want to put stuff, that does not affect the space,

we use... position: absolute!

```css
#bannerVideo {
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0px;
  left: 0px;
}
```

almost there!

let's put white letters

in the navbar and title with the color: white




```css
#title-banner {
  color: white;
}

.secondary-headers {
  color: white;
}
```

```css
#navbar-items li {
  color: white;
}
```

TRICK, you don't need to assign classes for everything that you want to select.
css has this syntax

almost done!! we can not see the white letters clearly

let's add a layer, that brings opacity

# LAYER

you know how, we create a big div that occupies all the screen, and we put there the opacity effect in the css style.



```html
  <div class="video-layer">
    
  </div>
```

```css
.video-layer {
  position: absolute;
  top: 0px;
  left: 0px;
  width: 100%;
  height: 100%;
  background-color: orange;
}
```

we don't see the background

remember, we have to tell in which position in the z-index

it must be above the video, but below the letters

```css
.banner {
  /* [...] */
  z-index: 2;
}
```

```css
.top-navbar {
  /* [...] */
  z-index: 2;
}
```

and the video is in 0, so, the layer should b in the middle, in position 1!

awesome! problem is, now we don't see the video, we don't want a background-color orange

we want it transparent, but with a filter. filters there are a lot, take this one


```css
.video-layer {
  position: absolute;
  top: 0px;
  left: 0px;
  width: 100%;
  height: 100%;
  background-image: linear-gradient( -225deg, rgba(16, 33, 43, 0.8) 0%, rgba(24, 43, 56, 0.6) 50% );
  z-index: 1;
}
```


we are done!!!!!




































































































































