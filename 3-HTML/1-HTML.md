# HTML

## What is HTML?
HTML stands for HyperText Markup Language.

It's used to add meaning to content so that it can be understood by machines (i.e. web browsers) and presented on the web.

It provides structure to a page.

## What is HTML not?
HTML doesn’t (or, shouldn’t) provide presentational information about the content. It’s not for layout or styling.

It isn’t a programming language, there is no logic - only structure.

## What does HTML look like?
HTML consists of tags. These are words found between angle brackets.

Most tags come in pairs, an opening tag which is the tag’s name between angle brackets, and a closing tag with a forward slash before the name.

`<tagname></tagname>`

## Tags
Tags go around content, they provide meaning to the content.

They tell us (and machines) what kind of content it is.

Content can be text, or other tags.

`<tagname>CONTENT</tagname>`
```html
<tagname>
	LOTS AND LOTS OF CONTENT
</tagname>
```

## Writing HTML
HTML is written in .html  files. The contents of the file create an HTML document.

Opening the .html file in a web browser (either from a server, or directly from your computer) will show the web page.

The following HTML, when put into an .html file will create an incredibly simple web page. It contains everything necessary for the browser to present simple information to the visitor.

```html
<!DOCTYPE html>
<html>
	<head>
		<title>We Made an HTML Page, You'll Never Guess What Happened Next</title>
	</head>
	<body>
		<h1>We Made an HTML Page, You'll Never Guess What Happened Next</h1>
	</body>
</html>
```

## Semantics
When we write HTML, we should choose tags in a way that enhance the semantics, or meaning of the content. Rather than choosing tags that control the presentation of elements, we add context or meaning and the stylesheet (which we are most likely writing too) decides how these semantically chosen elements should look. For example, if we have a quotation with a citation, or an image with attribution, rather than using the `<i>` tag to say that the citation should be italic, we tell the browser that it is a citation using the `<cite>` tag, and then - in the stylesheet - tell the browser that citations should be represented by italic type.

## Tag Types
We can loosely group tags into a few categories. These are not exhaustive, nor are they necessarily 'official', but they represent a useful way of considering the different types of tag we can use.

- HTML Structure
- Sectioning
- Headings
- Content
- Text
- Semantics
- Media

A reference of all HTML tags, grouped by function can be found on MDN at [https://developer.mozilla. org/en/docs/Web/HTML/Element](https://developer.mozilla. org/en/docs/Web/HTML/Element)

### HTML Structure
Ordering the document parts so the browser can parse them correctly.

- `<html>` - the base of the document
- `<head>` - metadata about the page, the content inside is not displayed on the page
- `<body>` - the displayed content of the page

### Content Structure
Dividing and organising the page content logically & semantically.
- `<header></header> and <footer></footer>`
- `<nav></nav>`
- `<article></article>`
- `<section></section>`
- `<div></div>`

`<div>` tags, or divisions, carry no meaning with them and can be used to arbitrarily group or divide elements on the page. The other tags have specific places they are recommended to be used. For example, the content of an `<article>` should be able to stand alone without the context of the page - i.e. if it would work like a clipping from a newspaper, or if it was pulled into a social media feed it would still make sense.

### Headings
The structural sections can be given titles, these are h tags and are numbered hierarchically 1-6. The most important title of a section should be `<h1>`, subtitles would be `<h2>` and sub-subtitles `<h3>`, sub-sub-subtitles `<h4>` and so on.

Usually there should be only one `<h1>` on the page - as that will contain the main title encompassing all the content (this might be the name of the site, or the headline of the article) there will be likely many `<h2>` elements as each part (sidebars, sub headers, lists etc) are often titled.

It's rare (but possible on complex pages) to go much beyond `<h3>`.

### Content
Content elements group or explain parts of the document.

- `<p>` delineate paragraphs of text
- `<ol>` and `<ul>` define lists (ordered and un ordered)
- `<li>` define individual elements in a list
- `<figure>` shows, generally, an image, illustration, diagram or something referenced from the main text.
- `<figcaption>` is used within a `<figure>` to provide a caption.


### Text
Tags used to add meaning to text are many and varied. For example, the `<q>` tag to mark out a short quotation, `<abbr>` which shows that something is an abbreviation or `<strong>` which marks out importance in text.

These will almost always appear inside other elements, to highlight, or add meaning to a part of a paragraph (`<p>`) or header (`<h1>`,`<h2>` etc) for example.

## Block vs. Inline
By default, some tags display as inline elements (they will sit next to each other like words in a sentence) and some display as block elements (they will force all other elements of of their line and try and take the full width of the page). This can be changed with CSS.

## Self Closing (void) tags
The tags we’ve seen so far have an opening and a closing component and content sits between them.

Some tags, though, such as those for images, do not have an opening & closing tag but are known as void tags or self closing tags.

They consist of a single tag, so the following would be a valid way of specifying an image (although no image would appear):

`<img>`

### Media
In order to have the image appear as an image, we need to tell the tag what image it should show and where to find it.

To do this we specify the src (source) attribute which contains the path to an image file.

`<img src=”gr8-image.png”>`

The path is relative to the html file we are currently writing so here, there would need to be an image called “gr8-image.png” in the same folder as our index.html.

Common image formats that can be displayed are .jpg/.jpeg, .png and .gif files (and .gif files can include animation)

There are tags for other kinds of media, such as audio and video - these work similarly, although there are more considerations that need to be made around the formats of the files and support across different browsers and platforms. This article on MDN can help with this: [https://developer.mozilla.org/en-US/docs/Web/HTML/Supported_media_formats#Browser_compatibility](https://developer.mozilla.org/en-US/docs/Web/HTML/Supported_media_formats#Browser_compatibility)

## Attributes
Above we saw the src="" attribute in use on an `<img>` tag. There are many more attributes we can use in HTML (and some we can define ourselves), and we can specify more than one attribute per tag. For example we might want to tell the browser the size of an image file so that it can use a placeholder while it’s still loading.

`<img src=”gr8-image.png” width=”640” height=”480”>`

We should also always include the alt="" attribute on an image with a description of the image. This means that if the file goes missing, or doesn't load for some reason, there is still some indication of what should be shown. It also means that screen readers can describe the contents of the image to visually impaired users.
