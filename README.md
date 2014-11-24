Animate.less
============

*CSS animation pack for Less.*

`animate.less` is a collection of cross-browser CSS animations that you can plug right into your Less pre-processor for use in your projects. Thanks to the power of [Less](http://lesscss.org/), you can now create seriously complex animations, even without using any JavaScript or jQuery magic. More on this later.

##What is Less?
Less is a CSS pre-processor, meaning that it extends the CSS language, adding features that allow variables, mixins, functions and many other techniques that allow you to make CSS that is more maintainable, themable and extendable.

Less runs inside Node, in the browser and inside Rhino. There are also many [3rd party tools](http://lesscss.org/usage/index.html#guis-for-less) available that allow you to compile your files and watch for changes. The latter is the way to go if you want to get up and running quickly.

##Usage
To use animate.less in your website, simply drop this single file into your Less pre-processor and press `compile`. The pre-processor will generate an `animate.css` stylesheet. Just drop the stylesheet into your document's `<head>`, and add the class `animated` to an element, along with any of the included animation names. That's it! You now have an CSS animated element.

```html
<head>
  <link rel="stylesheet" href="animate.css">
</head>
```

You can do a whole bunch of other stuff with animate.css when you combine it with jQuery or add your own CSS rules. Dynamically add animations using jQuery with ease:

```javascript
$('#yourElement').addClass('animated bounceOutLeft');
```

You can also detect when an animation ends:

```javascript
$('#yourElement').one('webkitAnimationEnd mozAnimationEnd MSAnimationEnd oanimationend animationend', doSomething);
```

**Note:** `jQuery.one()` is used when you want to execute the event handler at most *once*. More information [here](http://api.jquery.com/one/).

You can change the duration of your animations, add a delay or change the number of times that it plays:

```css
#yourElement {
  -vendor-animation-duration: 3s;
  -vendor-animation-delay: 2s;
  -vendor-animation-iteration-count: infinite;
}
```

*Note: be sure to replace "vendor" in the CSS with the applicable vendor prefixes (webkit, moz, etc)*

##Script-less Animations
One of the advantages of using Less is that you can create functions, which are basically [Mixins](http://lesscss.org/features/#features-overview-feature-mixins) containing nested rules and other function calls. Animate.less contains a set of mixins that make manipulating your animations easier. For example, the above jQuery example can be written as:

```less
#yourElement {
  .animated();
  .bounceOutLeft();
}
```

Which will output:

```css
#yourElement {
  -webkit-animation-duration: 1s;
     -moz-animation-duration: 1s;
      -ms-animation-duration: 1s;
       -o-animation-duration: 1s;
          animation-duration: 1s;
  -webkit-animation-fill-mode: both;
     -moz-animation-fill-mode: both;
      -ms-animation-fill-mode: both;
       -o-animation-fill-mode: both;
          animation-fill-mode: both;
  -webkit-animation-name: bounceOutLeft;
     -moz-animation-name: bounceOutLeft;
      -ms-animation-name: bounceOutLeft;
       -o-animation-name: bounceOutLeft;
          animation-name: bounceOutLeft;
}
```

And there you have it! The animation has been achieved without using any jQuery. Of course, this is only a tiny fraction of what can be achieved with Animate.less. Please head on over to [AnimateForLess.com](http://animateforless.com) for a full demo and to join the duscussion.

##Documentation
Coming soon. I promise!

## License
Animate.less is licensed under the MIT license. (http://opensource.org/licenses/MIT)

## Contributing
Pull requests are the way to go here. I only have two rules for submitting a pull request: match the naming convention (camelCase, categorised [fades, bounces, etc]) and let us see a demo of submitted animations in a [pen](http://codepen.io).
