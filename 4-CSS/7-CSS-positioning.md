# CSS Positioning
As well as moving things around with margins and sizes, we can place our boxes on the page in a few different ways.

## Positioning - Static
By default, most HTML elements are statically positioned. This means that they appear according to their place in the HTML, affected of course by their box-model sizes. They are considered to be in the normal flow of the document.

We can change this with the `position` property.

## Positioned Elements
When we change the `position` property of an element to something other than `static`, then we create a 'positioned' element - this means it behaves slightly differently depending on how it is positioned.

## Positioning - Relative
If we set `position: relative;` then we can offset the element from its ordinary location using `top`, `left`, `bottom`, `right`.

This will place the div 50px further across than it would be ordinarily:
```css
div{
	position: relative;
	left: 50px;
}
```

This is similar to adding `margin-left: 50px`, except that the element will not move any other elements, it will overlap (or go under) them.

Relatively positioned elements remain in the normal document flow - there will be a space reserved for them in the layout - but their movement causes them to dispay offset from that space.

## Positioning - Absolute
If we set `position: absolute;` then we can place the object using `top`, `left`, `bottom`, `right` coordinates. The position will then be set absolutely, offset from the edges of the element's containing block.

The containing block is the closest element that is *positioned* - that is, that has a `position` value other than `static`. If there are none, then the containing block will be the root element (`<html>`).

This will place the div 200px from the left, and 40px from the top, of its container:
```css
div{
	position: absolute;
	left: 200px;
	top: 40px;
}
```

Absolutely positioned elements are removed from the normal document flow - no space is created for them in the page layout and they don't affect the position of any neighbouring elements.

#Positioning - Fixed
Setting `position: fixed;` will cause an object to behave much like an absolutely positioned one, except that its containing block is the viewport. This means that fixed position can be used to create elements that remain in view even when the page is scrolled.

If an ancestor element (a containing element that may not be direct) has the `transform`, `perspective`, or `filter` properties set, then that will be used as the containing block instead of the viewport.

#Positioning - Sticky
`position: sticky;` causes an element to behave as if it was `position: relative;` positioned until its container reaches a particular point, then it will appear as if it was `position: fixed;`.

For example, to set a div to appear normally until it is about to leave the top of the page, and for it to then remain stuck to the top, the following rules could be used:

```css
div{
	position: sticky;
	top: 0px;
}
```
