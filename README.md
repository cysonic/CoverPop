# coverPop.js

**coverPop.js** is a lightweight (but customizable) jQuery plugin to set a fullscreen popup overlay on a visitor's initial visit and hide for a set period of time.

Since styling is handled through CSS, **coverPop.js** integrates well with responsive sites.

## Example

![Example GIF](https://dl.dropboxusercontent.com/u/9008516/Screencast-2013.05.22-21.57.gif)

## Usage

### CSS

Include the plugin css file:

```html
<link rel="stylesheet" href="css/coverPop.css">
```

### JS

Include jQuery and the plugin js:

```html
<script src="//ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>
<script src="js/jquery.coverPop.js"></script>
```

Start it with the default settings:

```javascript
$(document).coverPop();
```

**coverPop.js** can has the ability to customized:

```javascript
$(document).coverPop({
    coverClass:        'coverPop-cover',       // set default cover class
    contentClass:      'coverPop-content',     // set default content class
    fadeInDuration:    500,                    // time (in milliseconds) to fade in
    fadeOutDuration:   500,                    // time (in milliseconds) to fade out
    expires:           30,                     // duration (in days) before it pops up again
    jsCenter:          false,                  // if we want the plugin to center the middle box with js (nasty and unrecommended)
    closeClass:        "coverPop-close",       // close if someone clicks an element with this class
    cookieName:        "coverPop",             // to change the plugin cookie name
    onPopUpOpen:       function() {},          // on popup open
    onPopUpClose:      function() {},          // on popup close
    forceHash:         'splash',               // add to url to force display of popup (e.g. http://yourdomain.com/#splash)
    closeOnEscape:     true                    // close if the user clicks escape
    info:              false                   // toggle console.log statements
});
```

### HTML

`.coverPop-cover` is used on the full window cover. `.coverPop-content` is used for the content of the popup.

By default, a click on any element with `.coverPop-close` will close the popup. The plugin adds `preventDefault()` to elements with this class.

```html
<body>


  <!-- your site's markup -->


  <!-- start popup -->
  <div class="coverPop-cover splash">
      <div class="coverPop-content splash-center">

          <!-- the popup content (form, welcome message, etc.) -->

          <a class="coverPop-close" href="#">or skip signup</a>

      </div><!--end .splash-center -->
  </div><!--end .splash -->
  <!-- end popup -->

  <!-- js, etc. -->

</body>
```

## Updates

* v1.0.2 - Add option to close popup by hitting escape *(5/23/2013)*
* v1.0.1 - Add ability to force the popup by adding a hash to the url *(5/22/2013)*


### License

MIT