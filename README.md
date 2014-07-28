buttons-collection.scss
=======================

Simply an open source collection of buttons made with SASS:  
* [Demo](http://riccardo-zanutta.github.io/buttons-collection.scss/);
* [Sache.in link](http://www.sache.in/search?query=button-collection.scss).

Getting started
===
* You can grab the compiled CSS directly from the css folder;
* If you're using SASS, import in your main stylesheet(or whatever you want) the **buttons.scss** and **mixins.scss** files:

```sass
@import 'mixins';
@import 'buttons';
```

In **buttons.scss** there is:

```sass
/* Buttons */

// variables: button colors.
$base-button-color:     #fff !default;
$base-button-bg:        #0074d9 !default;
$btn-primary-border:    darken($base-button-bg, 5%) !default;

// Base Button
@include button;

// Themes
@include button_flat;
@include button_ghost;
@include button_ghost;
@include button_ghost_light;
@include button_3d;

.btn, .btn-flat, .btn-ghost, .btn-ghost-light, .btn-3d, {
  @include blockbreak;
}

// Sizes
.btn-s { font-size: 12px; }
.btn-m { font-size: 18px; }
.btn-l { font-size: 20px; }

// Border radius.
.radius {border-radius: .3em;}
```

So if you want to create a new button, or change the color, ovverride or create a new button class, simply @include your desired mixin in the **buttons.scss** file.

Note that there are some helper classes to increase/decrease the size of the buttons and to make them rounded.

Examples
--------

```sass
// buttons.scss
// $red is a variable I defined in a separate "_vars.scss" file.

@include button_flat($class: -red, $bg: $red)

```

Output in **main.css**: 


```css

/* Consider to apply this style to an anchor tag <a/> */ 
.btn-flat-red,
.btn-flat-red:link,
.btn-flat-red:visited {
  position: relative;
  color: white;
  background-color: #e74c3c;
  -webkit-box-shadow: 0px 4px #d62c1a;
  box-shadow: 0px 4px #d62c1a;
  margin-bottom: 1.5em;
  -webkit-transition: all 0.3s;
  transition: all 0.3s;
}

.btn-flat-red:hover,
.btn-flat-red:focus {
  text-decoration: none;
  background-color: #d62c1a;
  -webkit-box-shadow: 0px 4px #a82315;
  box-shadow: 0px 4px #a82315;
}

.btn-flat-red:active {
  top: 3px;
  outline: 0;
  background-image: none;
}
```

In the mixins file you can find:
* the main %button placeholder;
* A mixin for responsive breakpoints;
* (obviously) the main mixins. 
* a "blockbreak" mixin, useful for making a full-width button on a certain breakpoint. So, once you have created your classes, make sure to include them:

```sass
// buttons.scss

.btn, .btn-flat, .btn-ghost, .btn-flat-custom, .btn-ghost-custom, .btn-3d, {
  @include blockbreak;
}
```

* You can change the breakpoint in the **mixins.scss** file;
* You can include only the theme you want to avoid bloat of code;

:warning: I'm using [PrePros App for Windows](http://alphapixels.com/prepros/) to compile and autoprefix SASS. Consider to use that or a library such as [Bourbon](http://bourbon.io).

**I'm going to add more and more themes**. So feel free to fork this repo, use the code for **personal and commercial** uses, extend its functionality and make a pull request :)


