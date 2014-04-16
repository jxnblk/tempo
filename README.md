# Tempo

Responsive Grid System
http://jxnblk.github.io/tempo

Tempo is designed to work well independently, but is built in the same spirit as [BASSCSS](http://jxnblk.github.io/basscss). Mix and match as you see fit.

## Basic Usage
Use the vanilla CSS files or import the `scss/tempo.scss` file with SASS.
Set custom variables within the same file or in a separate variables file.

## Grid
The default grid only kicks in at a set breakpoint `$breakpoint`.

Start with an optional container to set a max-width.

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

Use `.col-pre-X` and `.col-post-X` classes to add spacing between columns.

```html
<div class="container">
  <div class="row">
    <div class="col col-4">4 columns</div>
    <div class="col col-7 col-pre-1">7 columns with space to the left</div>
  </div>
</div>
```

## Mobile Grid
Use mobile grid classes to affect layout at all screen widths.

```html
<div class="clearfix container">
  <div class="mobile-grid mobile-grid-6">Half width</div>
  <div class="mobile-grid mobile-grid-6">Half width</div>
</div>
```

Note: the mobile grid does not include pre/post classes. Why would you want that?

### Combined mobile and desktop grid
Use mobile grid classes as a base, then add default grid width classes to adjust layout at large screen widths.

```html
<div class="clearfix container">
  <div class="mobile-grid mobile-grid-6 grid-7">Half width at mobile - 7 columns on larger screens</div>
  <div class="mobile-grid mobile-grid-6 grid-5">Half width at mobile - 5 columns on larger screens</div>
</div>
```

## Centered Grid
Use the centered grid classes to create single columns that line up with the grid.

```html
<div class="centered-grid-8">Centered single column</div>
```

Note:
- Centered grid elements are not floated and contain themselves, so there's no need for a clearfix or parent container.
- Centered grid is only available at these sizes: 4, 6, 8, & 10.


## Tiles
Tiles are automatically resizing containers intended for collections of items, such as thumbnails.

```html
<div class="clearfix">
  <div class="tile-big">Big Tile</div>
  <div class="tile-big">Big Tile</div>
  <!--

    include as many as needed - no need for row containers

  -->
  <div class="tile-big">Big Tile</div>
  <div class="tile-big">Big Tile</div>
</div>
```

By default, tiles come at three sizes: `.tile-small`, `.tile-medium`, and `.tile-big`.

### Mixin
Use the mixin to define your own tiles. Pass the `build-tile()` mixin a list of 4 integers. They represent the number of columns across breakpoints. Use this mixin with care and be sure to remove any unused styles.

```scss
.tile-small {
  @include build-tile( (3, 6, 9, 12) );
}
```

## Customizing
Adjust these basic variables to suit your needs.

```scss
// .container max-width
$max-width: 75rem !default;

// Grid and tile gutter
$gutter: 3% !default;

// Maximum level of pre/post classes to generate
$pre-post-max: 2 !default;

// Breakpoints
$bp1: 36rem !default;
$bp2: 60rem !default;
$bp3: 75rem !default;
```


MIT License http://opensource.org/licenses/MIT

