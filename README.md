# Grider

## What is this?
Grider is a simple and lightweight CSS framework that allows you to create fully responsive flexbox grid for your website quick and effective.  
It's basically a set of CSS styles, but you don't need to use additional classes in your HTML file (like in Bootstrap).  
<b>Note that you should know basics of flexbox (more at [https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)).</b>

## How to use?
1. Copy `grider.scss` to your styles directory and import it in your main stylesheet.
2. Define your own RWD breakpoints and assign them to `resolutions` variable in `grider.scss [line 118]`.
3. Build your project.
4. You can now use <i>grider</i> attributes in your HTML.

## Attributes
According to what what RWD breakpoints you were defined, you can use corresponding attributes.    
For example, if you defined these breakpoints:
```SCSS
$resolutions: 0, 360, 768, 992, 1280;
```
you can write something like
```HTML
<div grider-0="data"></div>
```
or
```HTML
<div grider-0="data" grider-360="data" grider-768="data" grider-992="data" grider-1280="data">
</div>
```

Additionally, no matter what breakpoints you were defined, there is always available pure `grider` attribute which basically means
```CSS
[grider] {
    display: flex;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
}
```
to use it just type
```HTML
<div grider></div>
```

## RWD
Grider supports <i>mobile first</i> phillosophy, so each `grider-X` attribute means
```CSS
@media all and (min-width: X px) {
    /* some styles */
}
```
In consequence, attribute `grider-360` will work on every browser with width `>= 360px` unless it will be overwritten by for ex. `grider-992`.  
Note that overwriting styles applies only to opposing values (for ex. `vertical` and `horizontal`).

## Values (of attributes)
It's impossible to make a good grid (or any grid) using only pure attributes. To see the effects we need to fill them with some values from the list below:

- horizontal
- vertical
- reversed
- center
- top
- bottom
- left
- right
- middleX
- middleY
- between
- around
- wrap
- nowrap
- hidden
- visible
- empty
- absolute
- relative
- fixed
- flex-X (where X is from range 0 - 12)
- order-X (where X is from range 0 - 12)

## Demos
You can find more demos [here](http://00.cba.pl/grider/)