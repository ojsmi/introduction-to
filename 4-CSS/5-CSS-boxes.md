# CSS Boxes
Building a webpage is a case of putting boxes, that are the right size, in the right place. (There's some nuance to it, of course, but that's the essence)

## Box Model
The Box Model controls the way the browser considers each element as a rectangular box, and the way we can adjust the size of the box with CSS.

We can consider each element as 4 nested boxes, from inside to outside.

Innermost
- Content Box
	The content box contains the actual content of the element. e.g. the image or video, or the text.

	The size of the content box can be set with the `width` and `height` properties.
- Padding Box
	The padding box controls the space between the element’s content and its edge, or border.

	The size of the padding box, adding to the size of the content box, can be set with the `padding` property.
- Border Box
	The border box is the area of the element's border.

	By default on most elements this is invisible, but can be set with the `border` property, adding to the padding-box.
- Margin Box
	The margin box is the space outside the border between the element and any others.

	The size of the margin box, extending from the border box can be set with the `margin` property,
Outermost

## Changing the box model
The way that the 4 boxes within the CSS box model combine to set the size of an element and the space it takes on a page can be adjusted using the `box-sizing` property. `box-sizing` has two possible values:
- `content-box`
	This is the default CSS box model, the contents of the element, or the `width` and `height` properties set the size of the content box, with `padding` and `border` adding to this to set the overall size of the element. The margin box then extends around this to space the element out away from others.
- `border-box`
	The `width` and `height` properties set the size of the element, including the padding and border boxes. This means that padding pushes content inwards, away from the edges of the element. The margin still operates the same as before.

The default - `content-box` - is somewhat counter intuitive, especially when trying to produce flexible layouts. Setting `box-sizing: border-box;` on elements can be a useful way to make your task easier.
