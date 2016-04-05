# Background Blur Plugin

Background Blur plugin is a cross browser jQuery plugin for blurring images.

See http://msurguy.github.io/background-blur/ for documentation and demos 

## Installation and Usage

Install the plugin with Bower:

`bower install background-blur`

Or with NPM:

`npm install background-blur`

Or manually:
```javascript
<script src="jquery.min.js"></script>
<script src="background-blur.min.js"></script>
```

Create a container which will contain the blurred image:

```html
<div id='some-element'></div>
```
Then create a blurred image in that container:

```javascript
$('#some-element').backgroundBlur({
    imageURL : 'http://URL-of-the-image',
    blurAmount : 50,
    imageClass : 'bg-blur'
});
```

OR Create a blurred image and fade it in:

```javascript
$('#some-element').backgroundBlur({
    imageURL : 'http://URL-of-the-image',
    blurAmount : 50,
    imageClass : 'bg-blur'
    duration: 1000, // If the image needs to be faded in, how long that should take
    endOpacity : 1 // Specify the final opacity that the image will have
});
```

OR Create a blurred image, fade it in and switch to another image:

```javascript
// Initialize the blur
$('#some-element').backgroundBlur({
    imageURL : 'http://URL-of-the-image',
    blurAmount : 50,
    imageClass : 'bg-blur'
    duration: 1000, // If the image needs to be faded in, how long that should take
    endOpacity : 1 // Specify the final opacity that the image will have
});

//Switch the image
$('#some-element').backgroundBlur('http://URL-of-another-image');
```

## Browser Support:

- Chrome
- Firefox
- Safari and Safari Mobile (iOS)
- IE6, IE7, IE8 - blur is supported without animation (need to omit "duration" property in those browsers to make this plugin work, the problem will get fixed when Velocity.js issue gets fixed)
- IE9, IE10, IE11
- Android browsers

Possibly, more. Please let me know if some browser doesn't work

## Under the hood:

This plugin utilizes SVG filter to blur the image if SVG is supported by the browser (all except IE), otherwise the plugin creates an IMG tag and applies a special IE-only filter in CSS

**Q:** Why not simply use CSS 3 blur filter? 
**A:** The browser support for SVG blur filter is much wider when it comes to older browsers.

**Velocity.js** support:

If you are using Velocity.js animation library, the plugin will automatically detect its presence and make fade in/fade out animations more performant, especially on mobile. If Velocity is not present on the page, jQuery's "animate" is used instead.

## Where is this used?

This plugin is currently used on http://www.nbcnews.com/video

Have questions / suggestions or using the plugin? Please reach out on Github or Twitter at http://twitter.com/msurguy

## LICENSE 

This plugin is released under MIT license, giving you permission to use for commercial and non-commercial projects.
