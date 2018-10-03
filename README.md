# HTML

`id` in HTML must be a unique `selector`. Two elements can **NOT** share the same `id`!
```html
<div id="must-be-unique"></div>
```
`class` in HTML is used to represent a repeated `selector`. As many elements as you want can share the same `class` tag.
```html
<div class="can-be-repeated"></div>
```

# CSS
To access `id` elements in CSS you type `#` followed by the `id` tag.
```css
#must-be-unique {
    
}
```
To access `class` elements in CSS you type `.` followed by the `class` tag.
```css
.can-be-repeated {

}
```
`#must-be-unique` & `.can-be-repeated` are referred to as `selectors`.

You can also use the HTML `element` as a selector.
```css
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
$('#must-be-unique') // Will select the #must-be-unique element
$('.can-be-repeated') // Will select ALL the .can-be-repeated elements
$('h1') // Will select all h1 elements
$('img') // Will select all img elements
$('div > p') // Will select all p elements that are right after a div element
```
Now that you know how to *hopefully* select elements you can start using JQuery to manipulate the [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction#What_is_the_DOM), and CSS to style.
## Using JQuery for 'advanced' stuff
We can use `JQuery` to add [event bindings](https://learn.jquery.com/events/handling-events/). The following code will make it so anytime a `button` is `click`ed the `callback` function will be called. In this case it'll give you a nice little alert.
```js
$('button').on('click', function() {
	alert('Hey');
});
```
