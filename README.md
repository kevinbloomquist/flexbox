# CSS Box Model and Positioning: Flexbox Model

## Objectives
After this lesson, students will be able to:
- Describe how the Flexbox model differs from the regular CSS Box Model
- Name the basic properties that compose the Flexbox structure
- Explain a scenario in which Flexbox would be useful
- Create a simple layout using only Flexbox properties

##Preparation
- Before this lesson, students should already be able to:
- Write basic CSS
- Write basic HTML
- Use the chrome console
- Use the CSS box model to create simple layouts

## Why Flexbox?
So by now pretty much everyone is familiar with the CSS box model. But perhaps while constructing your last page layout, you noticed some of the flaws in the available tools - clearing and floating alone is enough of a headache to modern developers that many people working in the field have trouble describing how it works.

That's one reason why the Flexbox Model was created - its a more logical layout model that was added to the CSS3 spec in order to streamline page structuring, using CSS properties that match more common layout needs.

Flexbox is so new that it doesn't yet have full browser support, but that's no reason why we shouldn't learn it - within the next year, as IE11 support comes to an end, it will start to replace the CSS box model as the dominant tool for page structure - and we can arrive there already understanding it!

## An Intro to The Flexbox Model
The Flexbox Model is a series of CSS rules that affect the two main components of a web layout - the parent container, and the child elements. This is a structure we're already familiar with from past lessons - a block-level element is created as a "container", and holds inside of it a list of smaller elements:

```html
	<ul class="flex-container">
		<li id="item-1" class="flex-item">1</li>
		<li id="item-2" class="flex-item">2</li>
		<li id="item-3" class="flex-item">3</li>
		<li id="item-4" class="flex-item">4</li>
		<li id="item-5" class="flex-item">5</li>
		<li id="item-6" class="flex-item">6</li>
	</ul>
```
By default, the CSS Box Model allows you to control your child elements as a list - they can be arranged only in the order they appear in the DOM. With the Flexbox Model, you'll be able to rearrange your child elements along a grid, in any direction and order you wish, sorted either forward or backwards. The chart below details the names Flexbox uses to denote different positions along the grid - think of it like the nautical names for different sides of a ship (i.e. Port and Starboard):

![Flexbox Orientation](https://cdn.css-tricks.com/wp-content/uploads/2011/08/flexbox.png)

- **main axis** - The main axis of a flex container is the primary axis along which flex items are laid out.
- **main-start | main-end** - The flex items are placed within the container starting from main-start and going to main-end.
- **main size** - A flex item's width or height, whichever is in the main dimension, is the item's main size. The flex item's main size property is either the ‘width’ or ‘height’ property, whichever is in the main dimension.
- **cross axis** - The axis perpendicular to the main axis is called the cross axis. Its direction depends on the main axis direction.
- **cross-start | cross-end** - Flex lines are filled with items and placed into the container starting on the cross-start side of the flex container and going toward the cross-end side.
- **cross size** - The width or height of a flex item, whichever is in the cross dimension, is the item's cross size. The cross size property is whichever of ‘width’ or ‘height’ that is in the cross dimension.

Here, our unordered list "flex-container" is holding a collection of list items we'd like to arrange. From here, there's a number of CSS properties that we can apply to either our container or our children.

##Box Model Demo 

Let's write some HTML we can come back to and use to visualize what we're talking about.

1. Create an new directory called flexbox-model-work
2. Create html page called index.html with an externally linked css stylesheet called main.css
3. Inside your html page create a "flex-container" ul holding six list items within, with each next node numbered.

Your HTML should look something like this:

```html
	<html>
	<!DOCTYPE html>
	<html>
	<head>
		<title>Flexbox Practice</title>
		<link rel="stylesheet" type="text/css" href="main.css">
	</head>
	<body>
		<ul class="flex-container">
		  	<li id="item-1" class="flex-item">1</li>
		  	<li id="item-2" class="flex-item">2</li>
		 	<li id="item-3" class="flex-item">3</li>
		  	<li id="item-4" class="flex-item">4</li>
		  	<li id="item-5" class="flex-item">5</li>
		  	<li id="item-6" class="flex-item">6</li>
		</ul>
	</body>
	</html>
</html>
```
4. Let's also add some basic styles to reset our list and list items:

```css
ul {
	list-style: none;
}
ul li {
	padding: 14px;
	font-size: 2em;
	border: 1px solid #000;
}
```
## The Flexbox Model and its components

As we've discussed, the Flexbox Model has two main components - the parent element, and the children. Let's break down the Flexbox properties based on which object they're meant for:

### Properties of the Parent
First, let's take a look at the CSS calls we can use to shape the parent container:

#### Display
This one should be familiar - only the value of the property is new:
```css
.flex-container {
	display: flex;
}
```
This call denotes that our parent - and everything inside it - will be using the Flexbox Model. Just declaring this is enough to turn our layout into a very basic Flexbox layout - but probably not with any of the customization we want. This call has to be made before any of the following Flexbox properties can be used. 
*Note - display: flex gives your element Flexbox properties, but will allow it to be treated as a block-level element by all the other elements it share the page with. If you'd like your parent element to mimic the display properties of an inline element, use display:inline-flex. 

Go ahead and add display: flex; to our flex-container.

#### Flex-Direction
Flex-direction determines how our child elements will lay out inside their parent:

```css
.flex-container {
	flex-direction: row;
}
```
- **row (default)**: left to right 
- **row-reverse**: right to left
- **column**: top to bottom
- **column-reverse**: bottom to top























