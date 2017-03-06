# [resprite-less](http://uptoweb.info/resprite-less)

A light collection of mixins for automatic calculation of CSS properties for responsive background images (RBI) from sprite.

## Content of resprite-less

* The basics
* Universal mixin .rs for any cases of RBI
* Example of RBI with different sizes
* Example of RBI with equal sizes (grids, columns, etc)

## The basics

Simply @import the resprite.less file into the top of your main Less file for its working and use .rs mixin:
 
```
.img1 {
    .rs(@spr-url, @spr-width, @spr-height, @img1-width, @img1-height, @x1, @y1);
}
```

![sprite](https://github.com/uptoweb/resprite-less/blob/master/img/spr.png?raw=true)

#### Initial data:

1. @spr-url
2. @spr-width = 382px
3. @spr-height = 556px
4. @img1-width = 322px
5. @img1-height = 238px
6. @x1 = 40px
7. @y1 = 42px

HTML:
```html
<!--Any parent container-->
<div class="container">
    <!--Responsive background image element-->
    <div class="img1"></div>
</div>
```

Less:
```less
.img1 {
    .rs("../img/spr.png", 382, 556, 322, 238, 40, 42);
}
```

The code above resprite.less will compile to such CSS code

CSS:
```css
.img1 {
    background: url("../img/spr.png") 66.67% 13.21%;
    background-size: 118.63% 233.61%;
    padding-top: 73.91%;
    width: 100%;
}
```

The result you can see [here](http://uptoweb.info/code/resprite-less/basics.html) or in case with pseudo-element, [here](http://uptoweb.info/code/resprite-less/basics-pseudo-el.html)

More information [here](http://uptoweb.info/resprite-less)

## Author
[uptoweb](http://uptoweb.info)
