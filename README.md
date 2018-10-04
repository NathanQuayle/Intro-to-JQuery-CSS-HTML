# HTML
`id` in HTML must be a unique `selector`. Two elements can **NOT** share the same `id`!
```html
<!-- index.html -->

<div id="must-be-unique"></div>
```
`class` in HTML is used to represent a repeated `selector`. As many elements as you want can share the same `class` tag.
```html
<!-- index.html -->

<div class="can-be-repeated"></div>
```

## Including files in your HTML
`Link`ing files to your HTML is crucial to getting your CSS & scripts working.

Inside your HTML you need a `head` tag which holds all the `metadata`.

## ["The HTML `head` element provides general information (metadata) about the document, including its title and links to its scripts and style sheets."](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head)
```html
<!-- index.html -->

<html>
    <head>
        <meta charset="UTF-8">
        <title>My really awesome website</title>
        <link rel="stylesheet" href="style.css">
        <!-- script location one -->
        <script src="script.js"></script>
    </head>
    <body>
        <!-- script location two -->
        <script src="script.js"></script>
    </body>
</html>
```

`Scripts` can be placed in the `head` however this is generally avoided since the website will stop rendering to first fetch the script, this is known as `render-blocking`. Sticking the script at the bottom of the body tag will make the website render first and then fetch the script. Depending on what your script does this is normally the best approach - Do you NEED to manipulate the `DOM` before the page has finished loading?

[Flaviocopes has a good article on this, and all the possible workarounds and locations of where to put your scripts.](https://flaviocopes.com/javascript-async-defer/)


# CSS
To access `id` elements in CSS you type `#` followed by the `id` tag.
```css
/* style.css */

#must-be-unique {
    
}
```
To access `class` elements in CSS you type `.` followed by the `class` tag.
```css
/* style.css */

.can-be-repeated {

}
```
`#must-be-unique` & `.can-be-repeated` are referred to as `selectors`.

You can also use the HTML `element` as a selector.
```css
/* style.css */

h1 {
    /* Will style all h1 elements */
}

img {
    /* Will style all img elements */
}

div > p {
    /* Will style all p elements that are right after a div element */
}
```

# JQuery
In `JQuery` the `$() method` is used to select **all** elements with that selector.
```js
// script.js

$('#must-be-unique') // Will select the #must-be-unique element
$('.can-be-repeated') // Will select ALL the .can-be-repeated elements
$('h1') // Will select all h1 elements
$('img') // Will select all img elements
$('div > p') // Will select all p elements that are right after a div element
```
Now that you know how to *hopefully* select elements you can start using JQuery to manipulate the [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction#What_is_the_DOM), and CSS to style.
## Using JQuery for 'advanced' stuff
We can use `JQuery` to add [event bindings](https://learn.jquery.com/events/handling-events/). The following code will make it so anytime a `button` is `click`ed the `anonymous` `callback` function will be called. In this case it'll give you a nice little [alert](https://developer.mozilla.org/en-US/docs/Web/API/Window/alert).
```js
// script.js

$('button').on('click', function() {
	alert('Hey');
});
```
