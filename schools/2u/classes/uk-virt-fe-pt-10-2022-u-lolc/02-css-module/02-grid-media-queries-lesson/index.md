# 02 grid media queries lesson
## start class notes
make sure to reset any code you wrote in READ only Gitlab


* use chrome timer - https://chrome.google.com/webstore/detail/timer/hepmlgghomccjinhcnkkikjpgkjibglj/related?hl=en
* fundamentals of CSS Grids
* display-grid
* grid-template-areas
* how to build out grid columns and rows
* you can use css grids to code two-dimensional layouts

## Learning Objectives
1. Design and code basic grids using CSS Grid.
2. Build layouts by positioning elements inside grids.
3. Create a complex layout by nesting HTML elements inside of a grid.
4. Write media queries in code to create a responsive grid layout.

[my slides](https://docs.google.com/presentation/d/1IYlzRZHlXKc_OmN-edAfix5bN7Yc39rTFU6froJVnX0/edit#slide=id.gc5d1f643b4_0_3605)

[my notes](my notes)
* 2 demos in this lesson 

1. grid-template-areas
2. nesting grids

## CSS Grid
* man frontend devs think css grid is complicated but they all agree it is also very powerful
* why complicated?
  * answer: there are many different ways to build a CSS Grid
  * we will use the most straightforward method `grid-template-areas`
* why powerful?
  * answer: you can make flexible layouts with 1/3 of the code used in standard box model
  * `grid-template-areas` - also completely move HTML elements using CSS Grid without having to modify the HTML

## Instructor DO: intro CSS Grids (20 min)
* my goal of this lesson is to introduce grids on an elementary level
* get you all excited about CSS grids and using them for your website layouts
* today we build a css grid-based landing page (Furniture: Chairs and Stools)
* employers want frontend devs that understand flexbox and css grid

### Grid Layouts
* CSS Grids are used to create two-dimensional layouts
* Two-dimensional layouts are layouts that can span multiple columns or rows
* Grids allow you to define the layout section by section, allowing you to create children that span rows or columns and line up next to each other

### Before Flexbox and CSS Grids (slide #8)
* building layouts was frustrating
* lots of hacks
* getting universal browser support for layouts was next-to impossible
* 2013 Microsoft Edge shipped with it's implementation of CSS Grid
  * it was quickly adopted by the W3C
  * Soon it was standardized by all modern browsers (caniuse)

### Flexbox vs CSS Grid (slide #9)
* this is a big question asked a lot (could be an interview question)
* flexbox - 1 dimensional (left->right top->bottom)
* grid - you can create full complex designs 

## Resources
[mdn grid tutorial](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Basic_Concepts_of_Grid_Layout)


