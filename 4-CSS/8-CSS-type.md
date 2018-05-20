# CSS Type
CSS offers us many ways to set the typography on our page, from changing the size, line height or typeface through to more fine grained adjustments such as letter-spacing and how line breaks and whitespace should be handled.

# Changing the typeface
To change the *typeface* used for an element, the `font-family` rule can be used. So, to set a title in helvetica:

```css
h1{
	font-family: helvetica;
}
```

To change it's *size*, the `font-size` rule would be used. So, to set it to 20 pixels:

```css
h1{
	font-family: helvetica;
	font-size: 20px;
}
```

To change its *weight*, i.e. to make it bold, we would use the `font-weight` property:

```css
h1{
	font-family: helvetica;
	font-size: 20px;
	font-weight: bold;
}
```

To change its *style*, i.e. to use the italic variant, we use `font-style`:

```css
h1{
	font-family: helvetica;
	font-size: 20px;
	font-weight: bold;
	font-style: italic;
}
```

And, finally, to change the leading, the space between the lines, we would use the `line-height` property:

```css
h1{
	font-family: helvetica;
	font-size: 20px;
	font-weight: bold;
	font-style: italic;
	line-height: 22px;
}
```

All of this can be combined into the shorthand `font` property like so:

```css
h1{
	font: italic bold 20px/22px helvetica;
}
```

# Available Typefaces
In order for a typeface to be used, it must be accessible to the browser. This means it needs to be installed on the user's machine, or - if it is not - loaded from a server. This may be the same server as the site, or it may be an external service that provides it.

Font files that are available on users' devices are known as *web safe fonts*, while typefaces that can be loaded from an external service or as a file on the server are known as *webfonts*.

# Multiple Typefaces
A design might require different fonts for the body copy (the majority of the text) and the headings. In general, the body font would be specified in the most general way possible - on the `html` or `body` elements - with overrides specified on the elements that use the other font so, for example on a site that is mostly set in *times*, but with *helvetica* used for headings, we might have rules like this:

```css
html{
	font-family: times;
}
h1, h2, h3, h4, h5, h6{
	font-family: helvetica;
}
```

# Fallbacks
As there are a variety of different operating systems, devices and configurations around it's difficult to guarantee that a typeface will be available. Similarly, there is a chance that fonts loaded from external services may be unavailable due to network issues, users' security settings, etc. To maintain the accessibility, and to control the display of these edge cases, typeface choice on the web is often made as a hierarchical list of fallback fonts.

For example, a site may be designed using Tinos, from Google Fonts ( [https://fonts.google.com/specimen/Tinos](https://fonts.google.com/specimen/Tinos) ) but, in case Google Fonts is unavailable (which is admittedly unlikely) or the user's connection drops as the font file is being downloaded, Times New Roman (or another serif font) could be specified as a fallback.

In case the fallback font is not available on a particular device, then the type of typeface should be specified so the browser can make the best last-resort decision. In this case, we would specify `serif`. So the `font-family` rule becomes:

```css
html{
	font-family: Tinos, 'Times New Roman', serif;
}
```

Note that Times New Roman is placed in quotations because of the spaces in its name - if this was not done, the CSS would treat it as 3 separate fonts, but break because there is no comma between them.

# Web Fonts
When including a web font we need to let the CSS know where to find the file, what type of font it is - its weight or style, for example - and how we will refer to it when we want to use it. To do this, we use a special statement, an @ rule, that allows us to define these things. We use a `@font-face` rule for each typeface, weight and style we want to include. `@font-face`, as with all CSS @ rules should be specified outside of any selectors or other rule blocks.

At its most minimal, the `@font-face` rule needs two properties, `font-family` - the name we will give the typeface - and `src` - the location of the font files.

```css
@font-face {
  font-family: "Typeface Name";
  src: url( "path/to/thefont.woff2" ) format("woff2");
}
```

The majority of browsers now support the woff2 file format for web fonts. The exception being Internet Explorer, although Microsoft Edge - Microsofts latest windows browser does support them since version 14. If it is necessary to support older browsers, then a fallback file can be specified like so:

```css
@font-face {
  font-family: "Typeface Name";
  src: url( "path/to/thefont.woff2" ) format("woff2"),
			 url( "path/to/thefont.woff" ) format("woff");
}
```

When using multiple weights or styles of the same typeface, the `@font-face` rule can be configured to instruct the browser how to correctly select the right files for the weights or other variants used within the stylesheet. For example, if we were using the normal and bold weights of a font:

```css
@font-face {
  font-family: "Special Helvetica";
  src: url( "path/to/helvetica-regular.woff2" ) format("woff2");
	font-weight: normal;
}
@font-face {
  font-family: "Special Helvetica";
  src: url( "path/to/helvetica-bold.woff2" ) format("woff2");
	font-weight: bold;
}
```

Here, then, when 'Special Helvetica' is specified as the typeface for an element the browser will choose the correct file dependent on the weight specified for that element so, for the regular weight - loading 'helvetica-regular.woff2':

```css
p{
	font-family: 'Special Helvetica';
}
```

or for the bold weight - loading 'helvetica-bold.woff2':

```css
p{
	font-family: 'Special Helvetica';
	font-weight: bold;
}
```

# External Services
External webfont services will usually create the css `@font-face` rule for us, and provide a link to include in our page to load it. So, to use a typeface from Google Fonts, we don't need to write the `@font-face` rules ourselves, but we do need to include their file.

To use the font 'Frijole', we should add the following line to our HTML:

```html
<link href="https://fonts.googleapis.com/css?family=Frijole" rel="stylesheet">
```

This must be added *before* we include our stylesheet, and before we write any styles so that the font is available when the styles are parsed.

We can also include the file in our CSS instead using another @ rule, again before we write our other styles:


```css
@import url('https://fonts.googleapis.com/css?family=Frijole');
```

Whichever method we choose, we can then use the `font-family: Frijole;` to use that typeface.
