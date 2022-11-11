# Phil notes on Flexbox
reliable cross browser tools for creating CSS layouts were:
* floats
* positioning
* https://caniuse.com/ (show how this site gives you info on float, position and flexbox)

## Problems with position and float
* vertical center a block of content inside it's parent
* make children of container take up equal amount of the available width/height, regardless of how much width/height is available
* making all columns in a multiple-column layout adopt the same height even if they contain a different amount of content
* flexbox makes a lot of layout tasks easier
* have a section with 3 child articles
* make parent section display flex and they are 3 columns automatically
  * section becomes a flex container
  * it's children become flex items
* flexbox allows us to use rows or columns (display which direction the main axis runs (aka which direction the flexbox children are laid out in) - `flex-direction`)
  * default flex-direction is `row`
* use shorthand code where possible as it cuts down on your lines of code dramatically, overwrite with long form

## Align Items
* by default align-items is `stretch`
* if parent doesn't have fixed height in cross axis direction, then all flex items become as tall as the tallest flex item (first exam showed this)
* `center` causes items to maintain their intrinsic dimensions but be centered along the cross axis (this is ohow our buttons are centered vertically)
  * override for individual items with `align-self`
  * `justify-content` controls where the flex items sit on the main axis (default is `flex-start`)
* order
  * by default all flex items have an order value of 0
  * higher order appear later in items with lower values
  * you can have negative orders
* support
  * safe for students to test
  * but older browsers support flexbox but an outdated version of it
  * in production you have to test it - which browsers is your client using - they will usually let you know 
  * with layout browser support is very important, css drop shadow isn't supported, not a big deal as it won't be shown and your site is still relatively the same and won't be hard to view/decipher
  * but if your layout breaks because the browser doesn't support flexbox and you are using flexbox this is serious and will cause your site to not be viewed in the way you intended and could cause UX issues and customer complaints
  * cross browser testing is important

















