# jQuery.lazyexecute

jQuery.lazyexecute allows you to lazily execute a function when an element appears on the browsers viewport. By lazily executing functions, e.g. binding events to elements in the footer, on JavaScript heavy sites, you are able to prevent the users browsers from "hanging" right after the page is loaded.


## Usage

The plugin can for example be used to initialize a carousel as soon as the element, which wraps the carousel, is 200 pixels below the users viewport: 

```js
$("#footer > .carousel").lazyexecute(function($carousel) {
  $carousel.jcarousel();
}, {
  threshold: 200,
  failure_limit: 0,
  event: "scroll",
  container: window,
  skip_invisible: true
});
```

The options hash is optional and these options are the defaults.

So this does the same:

```js
$("#footer > .carousel").lazyexecute(function($carousel) {
  $carousel.jcarousel();
});
```


## Chaining

The plugin returns the given jQuery element for further usage.


```js
$("#footer > .carousel").lazyexecute(function($carousel) {
  $carousel.jcarousel();
}).css("border", "1px solid red");
```


## Minimize it

```
curl \
  -d output_info=compiled_code \
  -d compilation_level=SIMPLE_OPTIMIZATIONS \
  -d code_url=https://github.com/andfx/jquery.lazyexecute/raw/master/jquery.lazyexecute.js \
  http://closure-compiler.appspot.com/compile
```


## Credits

jQuery.lazyexecute is written on top of jQuery and is based on [jquery_lazyload](https://github.com/tuupola/jquery_lazyload) by [Mika Tuupola](https://github.com/tuupola/).


## License

Copyright (c) 2007-2012 Mika Tuupola

Licensed under the MIT license:

http://www.opensource.org/licenses/mit-license.php
