# CSS Selectors
There are a few varieties of CSS selector the primary ones are

- tag
- .class
- #id

## Selectors (tag)

You can select by the tag name of the element. To do this, you write the name of the HTML tag without < or >.

```css
div{ }
h1{ }
span{ }
```

## Selectors (class)
You can select by the class of an element, as applied by the class=”” attribute in HTML.

To do this, you write the name of the class with a . in front.

```css
.the-class{ }
.important{ }
.tiny{ }
```

## Selectors (id)
You can select by the id of an element, as applied by the id=”” attribute in HTML.

To do this, you write the name of the id with a # in front.

```css
	#the-id{ }
	#important-article{ }
	#first{ }
```

## Combined Selectors
Selectors can be combined to select one element more specifically.

```css
.class.another-class{ }
h2.important{ }
span.red.spaced{ }
```

## Hierarchical Selectors
You can also select items based on where they are in the page, for example select the `<h1>` tag within an `<article>`, or the links inside a paragraph.

The selected item will be the one on the right.

Select any `<h1>` tags inside an article:
```css
article h1{ }
```

Select any links (`<a>`) inside paragraphs (`<p>`):
```css
p a{ }
```

Select any elements with the class `.name` inside `<article>`s
```css
article .name{ }
```

## Attribute Selectors
You can also select items based on particular attributes, for example you could style only links that point to the google.com homepage:
```css
a[href="https://www.google.com"]{ }
```

Or you could style links that have the word 'google' in them somewhere, at least once:
```css
a[href*="google"]{ }
```

Or you could style links that start with 'https:', to show that they are encrypted and possibly more secure:
```css
a[href^=https:]{}
```

## The Universal Selector
An asterisk (\*) can be used to match all elements on the page.

```css
*{ }
```

## The :not() Selector
You can take items out of your selection with the :not() selector function.
So, you could select everything on the page that isn’t a <p>:
```css
:not(p){ }
```

Or you could style all `<h2>` that *dont* have the class `.crazy`:
```css
h2:not(.crazy){ }
```

Or everything inside an `<article>` that isn't a link:
```css
article *:not(a){ }
```

## Pseudo Class Selectors
You can also select items based on their current context, a common use of this is to add styling to items when the mouse hovers over them signifying interactivity.

Pseudo selectors are specified by a colon (:)

For example, to show an underline when all links on the page are hovered:
```css
a:hover{
	text-decoration: underline;
}
```
