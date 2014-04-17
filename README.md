# Tempo

Responsive Grid System
http://jxnblk.github.io/tempo

Tempo is designed to work well independently, but is built in the same spirit as [BASSCSS](http://jxnblk.github.io/basscss). Styles follow the open/closed principle. Mix and match as you see fit.

## Features
- Breakpoint-based mobile-first design
- OOCSS-inspired styles
- Fixed-width gutters
- Customizable variables
- Non-grid-sytem-based containers to control typographic measure
- Mobile grid styles
- Reusable width utilities
- Nesting, reverse ordering, margin, and centering utilities

## Basic Usage
Use the vanilla CSS files or import the `scss/tempo.scss` file with SASS.
Set custom variables within the same file or in a separate variables file.

## Grid
The default grid only kicks in at a set breakpoint, defined by the `$breakpoint` variable.

Start with a container to set a max-width. The container is optional if you wish to span the full-width of the screen.

```html
<div class="container">
</div>
```

Wrap each row of grid columns with the `row` class.

```html
<div class="container">
  <div class="row">
  </div>
</div>
```

Use the `.col` class to float elements left. Add a column width class to control width. Make sure the total number of columns adds up to 12.

```html
<div class="container">
  <div class="row">
    <div class="col col-4">4 columns wide</div>
    <div class="col col-8">8 columns wide</div>
  </div>
</div>
```

*Note: there is no `.col-12` class. For full-width content, simply omit the `.row` container.*

Use `.col-pre-X` and `.col-post-X` classes to add spacing between columns.

```html
<div class="container">
  <div class="row">
    <div class="col col-4">4 columns</div>
    <div class="col col-7 col-pre-1">7 columns with space to the left</div>
  </div>
</div>
```

*Note: To prevent bloated CSS, the `$pre-post-max` variable limits the number of styles available.*

To reverse the order of grid columns, use the `.col-right` class in place of `.col`.

```html
<div class="container">
  <div class="row">
    <div class="col-right col-6">First</div>
    <div class="col-right col-6">Second</div>
  </div>
</div>
```

To center a column, use the `.col-center` class in place of `.col`.

```html
<div class="row">
  <div class="col-center col-8">Centered column</div>
</div>
```

*To achieve a similar effect, see the [Smaller containers](#smaller-containers) section*

## Mobile Grid
Use mobile grid classes to affect layout at all screen widths.

```html
<div class="container">
  <div class="row">
    <div class="mobile-col mobile-col-6">Half width</div>
    <div class="mobile-col mobile-col-6">Half width</div>
  </div>
</div>
```

*Note: the mobile grid does not include pre/post classes.*

### Combined mobile and desktop grid
Use mobile grid classes as a base, then add default grid width classes to adjust layout at large screen widths.

```html
<div class="container">
  <div class="row">
    <div class="mobile-col mobile-col-6 col-7">Half width at mobile - 7 columns on larger screens</div>
    <div class="mobile-col mobile-col-6 col-5">Half width at mobile - 5 columns on larger screens</div>
  </div>
</div>
```

## Smaller Containers
Use these container classes to create single columns that line up with the grid, without floats and extra markup.

```html
<div class="container-col-8">Centered 8-column wide container</div>
```

*Note:*
- *These containers are not floated so there's no need for a clearfix or parent container.*
- *Containers are only available at these sizes: 4, 6, 8, & 10 column.*


## Customizing
Adjust these basic variables to suit your needs.

```scss
// .container max-width
$max-width: 75rem !default;

// Grid gutter
$gutter: 1.5rem !default;

// Maximum level of pre/post classes to generate
$pre-post-max: 2 !default;

// Breakpoint
$breakpoint: 36rem !default;
```

---

The MIT License (MIT)

Copyright (c) 2014 Brent Jackson

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
