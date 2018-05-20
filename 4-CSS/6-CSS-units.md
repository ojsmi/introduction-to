# CSS Units and Sizes
We can set the sizes of things such as width, height or padding in css using different numerical units. These fall into 2 categories - absolute units and relative units.

## Absolute Units
Absolute units are the same, regardless of any other settings or rules they come into contact with.

## Absolute Units - px
The most common of the absolute units, these set styles to an absolute css pixel value.

As an absolute unit, this is the same regardless of where in the code or hierarchy it sits. `10px` is the same everywhere on the page,

A CSS pixel is not necessarily the same as a pixel of the screen on which it is being displayed due to the way things scale (for example with someone zooming in on a web page), HiDPI screens, retina displays, etc.

## Relative Units
Relative units set a size in relationship to the element’s font size, or viewport size. The viewport is the viewable area of the page so - on desktop browsers - the size of the window.

It's useful to use font-relative units so that a page's vertical rhythm is maintained even if the font size is changed (either by the user - through zooming, or the designer - through design changes).

Viewport-relative units are useful for creating pages that scale to fit different screen sizes, or even approach resolution-independence.

## Relative Units - em
The value of an `em` is based on the `font-size` of the element it is being used on. This could be a font size that is explicitly set or inherited.

So `1em` is set to whatever the `font-size` is, `2em` is double that, `0.5em` is half and so on.

On an element with `10px` font-size then, `1em` = `10px`.

Ems are inherited, so sizing elements with ems inside elements with changed font sizes can get confusing. For example, if you're setting a bottom margin on paragraphs and headings of `1em` to maintain vertical rhythm throughout the page but then some of the headings are larger, say `font-size: 15px;` rather than `font-size:12px;`, then the margins will be different.

## Relative Units - rem
`rem` stands for root em.

They work like ems, except they are based on the font-size of the root element of the page. Usually this is the `<html>` element, so setting the `font-size` there sets the basis value for anything sized using `rem` values.

## Relative Units - viewport (vw,vh)
1vh is 1/100th of the height of the viewport.
1vw is 1/100th of the width of the viewport.

## Percentages
You can also use percentages as units. How they behave depends on the property you’re using.

### font-size
If you are setting the font-size, then percentages work similarly to ems in that `200%` is double the parent’s font-size, the same as `2em`.

### width
You can also use % to set an element’s width, for example. This sets the size relative to the element's container.

A width of 50% will make the box half the size of its container.

### height
If you set height using %, you have to make sure that the container has a size specified, otherwise the browser will get confused.

Sometimes you need to make sure sizes are specified all the way up to the html element (this can be as simple as setting `height: 100%;` on all container elements).
