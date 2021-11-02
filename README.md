# Themes

This repository is for the application themes and tools used across the [Hundred Rabbits](http://100r.co) [Ecosystem](https://github.com/hundredrabbits). 

<img src='https://raw.githubusercontent.com/hundredrabbits/Themes/master/PREVIEW.jpg' width='600'/>

## Setup

**Install Theme support** by adding [theme.js](https://github.com/hundredrabbits/Dotgrid/blob/master/scripts/lib/theme.js) to your header. 

```
<script type="text/javascript" src="scripts/lib/theme.js"></script>
```

**Define Theme overrides** in a dedicated [theme.css](https://github.com/hundredrabbits/Dotgrid/blob/master/links/theme.css) by adding this line to your header.

```
<link rel="stylesheet" type="text/css" href="links/theme.css"/>
```

**Initiate Theme support** by adding these lines somewhere in your project. The `.install(element)` method takes an element to append the `<style>` tag to.

```
const theme = new Theme();
theme.install(document.body);
theme.start();
```

**Trigger a function** once a new theme has been loaded:

```
theme.onLoad = callback
```

The callback will fire when a new theme has loaded, perfect to connect a refresh method and update your application with the new colors.

## Format Specs

The Theme format holds 9 different colors, including 4 foreground colors, 4 background colors, and a global background color. Each foreground color should be readable on every background color, with the exception of the `inv` types, which are designed to be used in warnings or modals and should only overlap each other. 

A variable's contrast should be seen as an offset to the global background color, so instance, `f_high` represents a high contrast color against the global `background`, and so does `b_high`, representing a highly contrasted color against the global `background`.

You can test your themes online with the [Theme Benchmark](https://hundredrabbits.github.io/Themes/).

- `background`, Application Background.
- `f_high`, Foreground, high-contrast.
- `f_med`, Foreground, medium-contrast.
- `f_low`, Foreground, low-contrast.
- `f_inv`, Foreground, for modals and overlays.
- `b_high`, Background, high-contrast.
- `b_med`, Background, medium-contrast.
- `b_low`, Background, low-contrast.
- `b_inv`, Background, for modals and overlays.

## The Theme Format

The Theme file format is a simple SVG file. The [theme.js](https://github.com/hundredrabbits/Dotgrid/blob/master/scripts/lib/theme.js) loader will look for colors found in the element's `id` attributes. **Save the image on your computer and drag it** over the application window to install it.

### Example

![apollo](themes/apollo.svg)

### Content

```
<!-- Author: Unknown -->
<svg width="96px" height="64px" xmlns="http://www.w3.org/2000/svg" baseProfile="full" version="1.1">
  <rect width='96' height='64'  id='background' fill='#E0B1CB'></rect>
  <!-- Foreground -->
  <circle cx='24' cy='24' r='8' id='f_high' fill='#231942'></circle>
  <circle cx='40' cy='24' r='8' id='f_med' fill='#5E548E'></circle>
  <circle cx='56' cy='24' r='8' id=
