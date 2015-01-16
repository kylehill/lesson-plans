## Advanced CSS

#### Box Model

Remember: Every element is encapsulated by a rectangular box.

Box Model properties:

* `margin`
* `padding`
* `height` - also, `max-height` and `min-height`
* `width`
* `border`
* `border-radius`

Specified `width`s only apply to content, and do not include `margin`, `padding`, or `border` width, so precise positioning and sizing content can be difficult and/or mathy.

Consider using `box-sizing: border-box;`, as the specified width will include `margin`, `padding`, and `border` and the content.

#### `display`

Determines how an element is drawn on a page, and how it affects other elements after it.

By far the four most common values for `display`:

* `none` - Element is entirely removed from the flow; other content rendered as if the tag isn't there.
* `block` - Element is rendered as a block -- accepts box model properties and fills all available width. Inline content can't start on the same line.
* `inline` - Element is rendered inline like text. Does not accept box model properties
* `inline-block` - Element is rendered inline, but accepts box model properties and does not word wrap within larger inline blocks.

Different elements have different default styling (`block` or `inline`), but that can be changed at the element or class level.

#### `position`

#### `float`

#### `z-index`

#### References

* [Learn Layout](http://learnlayout.com/)
* [Mozilla - CSS display property](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
* [Mozilla - CSS position property](https://developer.mozilla.org/en-US/docs/Web/CSS/position)