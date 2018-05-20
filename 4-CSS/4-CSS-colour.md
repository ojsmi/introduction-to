# CSS Colour
One of the simplest things we can do with CSS to change the presentation of a page is to change the colour of elements within it.

## Text vs background
We can colour elements in CSS. We can set the colour of text with the `color` property and we can set the fill or background colour with `background-color`.

## Solid Colours
We can set solid colours with keywords such as ‘red’ or ‘blue’. There are around 160 keywords.

To give all `<div>`s on the page a blue background, we could write:
```css
div{
	background-color: blue;
}
```

or to make all `<h1>` elements yellow with a green background, we would write:
```css
h1{
	color: yellow;
	background-color: green;
}
```

For more control we need to use hex codes, or the `rgb()` and `hsl()` functions.

## Solid Colours - rgb()
The `rgb()` function allows us to specify colours by the values of their red, green and blue channels. We can use decimal numbers from 0 to 255 for each channel to choose any one of around 16 million colours.

- `rgb( 0, 0, 0 )` gives us black
- `rgb( 255, 255, 255 )` gives us white
- `rgb( 255, 0, 0 )` gives us red
- `rgb( 0, 0, 255 )` gives us blue
- `rgb( 125, 20, 226 )` gives us a purple

## Solid Colours - hsl()
`hsl()` stands for Hue, Saturation, Lightness and relates more closely to the way we might see colours on a colour wheel than value mixing we do with `rgb()`.

The first argument - hue - is a value from 0-360 to select a colour at a location, in degrees, around the colour wheel.

Saturation and lightness are percentages.

0 saturation makes the colour grayscale
0 lightness will give us black, regardless of the hue and 100 lightness will give us white.

- `hsl( 0, 0, 0 )` gives us black
- `hsl( 0, 0, 100% )` gives us white
- `hsl( 0, 100%, 50% )` gives us red
- `hsl( 240, 100%, 50% )` gives us blue
- `hsl( 271, 84%, 48% )` gives us the same purple as above

## Solid Colours - Hexadecimal
It's common to see colours in CSS specified as hexadecimal values. Depending on your experience with other programming languages or technical notations, you might find this easier than `rgb()`, or it might look like nonsense. It's important to be aware of it - so you can understand code you find or see, even if you choose mostly to use the `rgb()` functional notation.

A hexadecimal (or hex for short) string begins with a hash (#) and consists of 6 characters which range from 0 to F, these stand for the numbers from 0 to 16 - but need only one character to fit any of those values. So, 0 means 0, and 8 means 8, but B means 11 and F means 16.

This, then gives us the values 0-255 in only 2 characters - 00 being 0, and FF being 255. In between we have things like 01 for 1, and C8 for 200, or 18 for 24.

And so 6 hexadecimal digits gives us our r, g and b values as before.

- `#000000` gives us black
- `#FFFFFF` gives us white
- `#FF0000` gives us red
- `#0000FF` gives us blue
- `#7D14E2` gives us the purple from above

(You don't need to know how to calculate these things yourself! Most colour pickers will tell you the hex string.)

It's possible to make the strings shorter, if the two characters for each channel are the same, for example in full red - `#FF0000`, we can drop the duplicates to get `#F00`.


## Transparent Colours - rgba() / hsla() / transparent
The `rgba()` and `hsla()` functions allow for transparency to be set on the colour.

They add a fourth parameter that goes from 0 to 1 to specify the opacity of the colour. 0 would mean it is fully transparent, and 1 that it’s fully opaque (or solid).

- `rgba( 0, 0, 0, 0.5 )` semi-transparent black
- `hsl( 271, 84%, 48%, 0.2 )` gives us a very transparent version of our purple from before

The keyword `transparent` can be used to make a fully transparent colour. This is the same as setting `rgba( 0, 0, 0, 0 )`.

## Setting Colours
We can freely choose which notations to use to set our colours, and we can use a mix of different notations within the same CSS document.

These two rulesets will have the same result - red text on a blue background:
```css
div{
	background-color: #0000FF;
	color: #FF0000;
}
```
```css
div{
	background-color: blue;
	color: rgb( 255, 0, 0 );
}
```
