# Harmon
A simple typographic scale written in Sass. 

If you need something more powerful or flexible, check out [modularscale-sass](https://github.com/modularscale/modularscale-sass).

## What is this?
Harmon is a simple typographic scale made for Sass-based projects. It's built on the principal that using a modular scale in web design will help you achieve visual harmony, particularly with typography. Read more about modular scales in Tim Brown's [A List Apart article](http://alistapart.com/article/more-meaningful-typography).

I tried [modularscale-sass](https://github.com/modularscale/modularscale-sass) but it felt a bit heavy duty for my needs. I wanted something simpler and lighter, so I built Harmon to scratch the itch.

## Install
* Install via Bower ```bower install harmon --save```
* Download ZIP and install manually

## Use
#### Configure the variables
The first step is to configure your scale. The default values are:
```scss
$base:  16px; // This is your base font size
$ratio: $minor-third; // The ratio for your scale
```
If those don't work for you, you have two options:

1. Edit ```$base``` and ```$ratio``` variables found in ```_harmon.scss``` to your liking.
2. Override them in your own settings.

Choose whichever method suits your needs. Note that ```$base``` should always be a ```px``` value; it gets converted to ```rem``` or a unitless value later.

#### Set the base font size
Next you need to set the base font size somewhere in your stylesheets using the ```$base``` variable you configured earlier. We all have different approaches to this. Here's my personal approach:
```scss
:root {
  font-size: $base;
}
```

#### Call the scale() function
Now you're ready to use the ```scale()``` function in your stylesheets. It takes a ```$step``` parameter for which step on the scale you want to move to. For example, to move 1 step up the scale:
```scss
body {
  font-size: scale(1);
}
```
To move 1 step _down_ the scale:
```scss
body {
  font-size: scale(-1);
}
```
When you want to use the base size:
```scss
body {
  font-size: scale(0);
}
```
Harmon uses ```rem``` units by default. You can optionally output a unitless value (useful for line heights). Example:
```scss
body {
  font-size: scale(1);
  line-height: scale(2, unitless);
}
```
Harmon uses the same ratios and steps seen on [modularscale.com](modularscale.com). **You can travel 6 steps down the scale or 16 up.** Harmon will throw an error if you try to go below -6 or above 16. I find this range to provide good coverage across all of the ratios available. Going beyond -6 and 16 seems to lead to diminishing returns anyway.

## Issues
If you find a bug or have a feature suggestion, feel free to [submit an issue](https://github.com/nickpfisterer/harmon/issues).

## Changelog
##### version 1.0.0 (April 13, 2015)
  * First version
  * Bower support
  * Sache support
