# Tempo

Responsive CSS Layout Modules
http://jxnblk.github.io/tempo

Tempo is designed to work well independently, but is built in the same spirit as [BASSCSS](http://jxnblk.github.io/basscss). Mix and match as you see fit.

## Basic Usage
Use the vanilla CSS files or import the files in the `scss/` folder with SASS. Set custom variables in the `_variables.scss` partial.

## Grid
The default grid only kicks in at a set breakpoint.

Start with a generic clearfix container, like the one found in BASSCSS.

```html
<div class="clearfix">
</div>
```

Add the `.container` class to limit the max-width. Note: this is optional, but `.centered-grid-X` classes will not properly align to the grid without this.

```html
<div class="clearfix container">
</div>
```

Use the `.grid` class to float elements left. Add a grid width class to control width. Make sure the total number of columns adds up to 12.

```html
<div class="clearfix container">
  <div class="grid grid-4">4 columns wide</div>
  <div class="grid grid-8">8 columns wide</div>
</div>
```

Use `.grid-pre-X` and `.grid-post-X` classes to add spacing between columns.

```html
<div class="clearfix container">
  <div class="grid grid-4">4 columns</div>
  <div class="grid grid-7 grid-pre-1">7 columns with space to the left</div>
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

Please note:
- Centered grid elements are not floated and contain themselves, so there's no need for a clearfix.
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

