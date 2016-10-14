# Grider

## What is this?
Grider is a simple and lightweight CSS framework that allows you to create fully responsive flexbox grid for your website quick and effective.  
It is basically set of CSS styles but you don't need to use additional classes in your HTML file (like in Bootstrap).  
<b>Note that you should know basics of flexbox (more at [https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)).</b>

## How to use?
1. Copy `grider.scss` to your styles directory and import it in your main stylesheet.
2. Define your own RWD breakpoints and assign them to `resolutions` variable in `grider.scss [line 118]`.
3. Build your project.
4. You can now use <i>grider</i> attributes in your HTML.

## Attributes
According to what what RWD breakpoints you were defined, you can use corresponding attributes.    
For example, if we defined these breakpoints:
```SCSS
$resolutions: 0, 360, 768, 992, 1280;
```
we can write something like
```HTML
<div grider-0="data"></div>
```
or
```HTML
<div grider-0="data" grider-360="data" grider-768="data" grider-992="data" grider-1280="data">
</div>
```

Additionally, no matter what breakpoints we were defined, there is always available pure `grider` attribute which basically means
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
@media all and (min-width: X) {
    /* some styles */
}
```
In consequence, attribute `grider-360` will work on every browser with width `>= 360px` unless it will be overwritten by for ex. `grider-992`.  
Note that overwriting styles applies only to opposing values (for ex. `vertical` and `horizontal`).

## Values (of attributes)
It's impossible to make a good grid (or any grid) using only pure attributes. To see the effects we need to fill them with some values.


1. Direction of child DOM elements:

    - horizontal
        ```
        ___________________
        DIV1 DIV2 DIV3 DIV4
        ___________________
        ```
       
    - vertical
        ```
        ___________________
        DIV1  
        DIV2  
        DIV3  
        DIV4
        ___________________
        ```
       
    - reversed (with horizontal)
        ```
        ___________________
        DIV4 DIV3 DIV2 DIV1
        ___________________
        ```
       
    - reversed (with vertical)
        ```
        ___________________
        DIV4  
        DIV3  
        DIV2  
        DIV1  
        ___________________
        ```
       

2. Position of child DOM elements:

    - left
        ```
        ___________________
        DIV
          
          
          
        ___________________
        ```
       
    - center (with vertical)
        ```
        ___________________
                  
                  
                DIV
                  
        __________________
       ```
    - right
        ```
        ___________________
                        DIV
                  
                
                  
        __________________
       ```
    - top
        ```
        ___________________
        DIV                
                  
                
                  
        __________________
       ```
    - bottom
        ```
        ___________________
                        
                  
                
                  
        DIV_______________
       ```
    - middleX
        ```
        ___________________
               DIV       
                  
                
                  
        __________________
       ```
    - middleY
        ```
        ___________________
                      
                  
         DIV       
                  
        __________________
       ```
    - between (with horizontal)
        ```
        ___________________
        DIV             DIV
                  
                
                  
        __________________
       ```
    - between (with vertical)
        ```
        ___________________
        DIV             
                  
                
                  
        DIV_______________
       ```
    - around (with horizontal)
        ```
        ___________________
            DIV      DIV
                  
                
                  
        __________________
       ```
    - around (with vertical)
        ```
        ___________________
                     
        DIV          
                
        DIV       
        __________________
       ```
    - wrap
        ```
        ___________________
                     
        DIV DIV DIV DIV DIV 
        DIV DIV        
              
        __________________
       ```
    - nowrap
        ```
        ___________________
                     
        DIVDIVDIVDIVDIVDIVDIV 
        
              
        __________________
       ```
    

3. Additional attributes:
    
    - hidden (`display: none`)
    - visible (`display: flex`)
    - empty (`visibility: hidden`)
    - absolute (`position: absolute`)
    - relative (`position: relative`)
    - fixed (`position: fixed`)
    - flex-X (where X is from range 0 - 12, in CSS: `flex: X`)
    - order-X (where X is from range 0 - 12, in CSS `order: X`)
