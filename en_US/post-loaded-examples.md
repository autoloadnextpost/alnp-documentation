# Auto Load Next Post Documentation

## alnp-post-loaded

The `alnp-post-loaded` callback is public JavaScript function dispatched after every successful Ajax load by Auto Load Next Post. The callback can be used to trigger functions in other JavaScript files, manipulate DOM content or simply _console.log_ a message for debugging – how you utilize the callback is completely up to you.

### Usage Examples

The following callback examples are used to initiate 3rd party scripts after successful Ajax requests.

Developers: You can copy and paste these into your theme so your theme supports these plugins with Auto Load Next Post.

<!--Users: Go to the extension section under Auto Load Next Post settings page to install the support you require.-->

#### Easy Fancybox - https://wordpress.org/plugins/easy-fancybox/

You can either use this code snippet or use the events section via the Auto Load Next Post settings to trigger Easy FancyBox.

```js
$(function() {
  $('body').on( 'alnp-post-loaded', function( e, params ) {
    $(document.body).trigger('post-load');
  });
})(jQuery);
```

#### AddToAny - https://wordpress.org/plugins/add-to-any/

```js
$(function() {
  $('body').on( 'alnp-post-loaded', function( e, params ) {
    if ( window.a2a_config ) {
       a2a.init_all("page"); // Trigger AddToAny
    }
  });
})(jQuery);
```

#### Addthis - https://wordpress.org/plugins/addthis/

```js
$(function() {
  $('body').on( 'alnp-post-loaded', function( e, params ) {
    if ( typeof addthis !== 'undefined' ) {
      addthis.layers.refresh(); 
    }
  });
})(jQuery);
```

#### ShareThis - https://www.sharethis.com/

```js
$(function() {
  $('body').on( 'alnp-post-loaded', function( e, params ) {
    if ( window.stButtons ) {
      stButtons.locateElements();
    }
  });
})(jQuery);
```

#### Facebook Comments, Like Button, Share etc.

```js
$(function() {
  $('body').on( 'alnp-post-loaded', function( e, params ) {
    FB.XFBML.parse();
  });
})(jQuery);
```

#### Jetpack - Tiled Galleries

```js
$(function() {
  $('body').on( 'alnp-post-loaded', function( e, params ) {
    var base_url = 'http://mywebsite.com';
    $.getScript( base_url + "/wp-content/plugins/jetpack/modules/tiled-gallery/tiled-gallery/tiled-gallery.js" );
  });
})(jQuery);
```

### Other 3rd party plugins

> These plugins have not yet been tested with Auto Load Next Post.

* [MetaSlider](https://wordpress.org/plugins/ml-slider/)
* [Easy SwipeBox](https://wordpress.org/plugins/easy-swipebox/)
* [Simple Lightbox](https://wordpress.org/plugins/simple-lightbox/)
* [Responsive Lightbox & Gallery](https://wordpress.org/plugins/responsive-lightbox/)
* [FooBox Image Lightbox WordPress Plugin](https://wordpress.org/plugins/foobox-image-lightbox/)
* [WP Video Lightbox](https://wordpress.org/plugins/wp-video-lightbox/)
* [WP Featherlight – A Simple jQuery Lightbox](https://wordpress.org/plugins/wp-featherlight/)
* [WordPress Colorbox Lightbox](https://wordpress.org/plugins/wp-colorbox/)
* [ARI Fancy Lightbox – WordPress Popup](https://wordpress.org/plugins/ari-fancy-lightbox/)
* [Gallery Manager](https://wordpress.org/plugins/fancy-gallery/)

---

If you have any issues with this guide, or the documentation that is linked throughout, please [open a new issue](https://github.com/autoloadnextpost/alnp-documentation/issues/new) in this repository for it to be reviewed. Thank you!