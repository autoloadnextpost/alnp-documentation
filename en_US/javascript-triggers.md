# Auto Load Next Post Documentation

## JavaScript Triggers

JavaScript triggers can come in handy when you need something to happen a certain way or at a certain time. Below are the triggers available that you can use dispatched directly from the core of Auto Load Next Post.

If you are wanting to trigger a 3rd party script then you may find the **Events** section under Auto Load Next Post settings page useful.

> ✏️ Note: Not all 3rd party scripts trigger the same way.

### Entering a post

`alnp-enter` is triggered when entering a post.

```javascript
$('body').on( 'alnp-enter', function( e, divider ) {
    console.log('Entered post!');
});
```

### Leaving a post

`alnp-leave` is triggered when leaving a post.

```javascript
$('body').on( 'alnp-leave', function( e, divider ) {
    console.log('Left post!');
});
```

### Post changed

`alnp-post-changed` is triggered when the viewer is reading another post.

An example of using this trigger would be to track other analytics of your choosing such as [Facebook pixels](https://wordpress.org/plugins/alnp-facebook-pixel-tracking/). 

```javascript
$('body').on( 'alnp-post-changed', function( e, this_title, this_url, this_post_id, post_count, stop_reading, initial_post ) {
    console.log('Post has changed!');
});
```

### Post URL

`alnp-post-url` is triggered before the post is fetched. This is useful should you wish to change the URL of the next post to load after X amount of posts.

```javascript
$('body').on( 'alnp-post-url', function( e, post_count, post_url ) {
    console.log('Post URL changed!');
});
```

### Post data

`alnp-post-data` is triggered before the post is appended to the DOM should you need to manipulate the post data.

```javascript
$('body').on( 'alnp-post-data', function( e, post ) {
    console.log('Post data has appended!');
});
```

### Post loaded

`alnp-post-loaded` is triggered once a post has loaded.

An [example](https://github.com/autoloadnextpost/alnp-code-snippet-library/blob/master/snippets/alnp-post-limit.js) of using this trigger would be to limit the number of posts per session and prevent further posts from loading once the `post_count` has reached its total.

```javascript
$('body').on( 'alnp-post-loaded', function( e, params ) {
    console.log('Post loaded!');
});
```

[Other usage and examples are available](https://github.com/autoloadnextpost/alnp-documentation/blob/master/en_US/post-loaded-examples.md).

### Previous post

`alnp-previous-post` is triggered when you have pressed the back button in your browser.

```javascript
$('body').on( 'alnp-previous-post', function( e, previous_post ) {
    console.log('Gone back to the previous post!');
});
```

> ✏️ Note: Your JavaScript triggers must be loaded after Auto Load Next Post in order to trigger these callbacks.

#### Are you looking for examples?

You're in luck as I also have a [code snippet library](https://github.com/AutoLoadNextPost/alnp-code-snippet-library) which I am compiling a list of examples in use by Auto Load Next Post users.


### Javascript boilerplate

I created a [boilerplate](https://github.com/autoloadnextpost/alnp-js-boilerplate) for the purpose of adding your own callbacks via a plugin. All that you have to do is edit the [Javascript file](https://github.com/autoloadnextpost/alnp-js-boilerplate/blob/master/assets/js/alnp-js-boilerplate.js) and customize the trigger you wish to apply your callback to.


---

If you have any issues with this guide, or the documentation that is linked throughout, please [open a new issue](https://github.com/autoloadnextpost/alnp-documentation/issues/new) in this repository for it to be reviewed. Thank you!