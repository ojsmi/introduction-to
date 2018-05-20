# CSS Cascade
In CSS, if multiple rules on the page could match an element, the browser has to decide which ones to apply. To do this, it measures rules against 2 metrics - their place of origin and the specificity of their selector.

This is known as the ‘cascade’ - hence Cascading Style Sheets.

## Cascade - Origin
First it looks at the origins of the styles its received.

Least Important
- Browser Default Styles
- Browser User Styles
- Page/Author Styles
Most Important

## Cascade - Page / Author Styles
When looking at the page styles, the order of inclusion is important.

Least Important
- First Linked Stylesheet or `<style>` block
- Next Linked Stylesheet or `<style>` block
- ...more sheets/blocks  
- Style Attributes on an element
Most Important

Within a stylesheet or style block, the rules at the bottom (if they have equal specificity) will override those at the top. Essentially, the browser joins all the style rules together into one large ruleset, according to their place in the cascade, and then applies them in order of importance, from top to bottom.

## Cascade - Animations
Styles being set by CSS animations will override other styles (so that they can override properties to animate them)

## Specificity
Having calculated the importance of various rules from their origin and order of inclusion, the browser will compare rules by assessing the specificity of their selectors.

The more specific a selector, the more weight its rules will carry.

Least Specific
- tag
- class, attribute, or pseudo-class
- id
- style attribute
Most Specific

As selectors are combined, they become more specific too.

So `p span` is more specific than `span`, even though they're both tag type selectors and something like `p.fancy:hover` would override `p.fancy`.

## !important
Rules can be made more specific or weighty by adding the `!important` keyword.
```css
span{
	color: red !important;
}
```
This can help you get around tricky situations (such as where an included library is setting some styles, or you need a really specific override of a style for just some elements), but normally points to bad planning in the structure of your CSS.
