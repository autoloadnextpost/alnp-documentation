# Auto Load Next Post Documentation

## Post Navigation

The post navigation is an important part in order for Auto Load Next Post to work. Most themes should have one applied for single posts, preferrably at the end of the article. Without the post navigation, Auto Load Next Post will **not** know which post to load next.

### My theme does not have a post navigation

If the theme that you are using does **not** have a post navigation then you will need to add one. The [Next and Previous Links](https://codex.wordpress.org/Next_and_Previous_Links) guide available at WordPress.org will help you along.

Once you have a post navigation applied, Auto Load Next Post will be able to load the next post when the post navigation is read.

### My theme has a post navigation

Great. By code standards a post navigation should have the `rel` attribute applied to both the previous and next post link. However, some themes dont use the standard post navigation or at least extend the standard post navigation and provide their own post navigation to provide the style they wish to present. Alot of these types of themes tend to forget about applying the required attribute to the links or enter a different attribute altogether.

Auto Load Next Post looks for two possible types of `rel` attributes applied to the previous post link, `rel="prev"` and `rel="previous"`.

If your theme does have a post navigation but posts are still unable to load, then it is most likley because the post navigation in your theme is missing either attribute assigned to the previous post link.

In this case, you will need to apply it in order for Auto Load Next Post to recognize the link of the previous post.

#### How to fix this

One way to apply the missing attribute to the post navigation is via JavaScript. Simply change `div.previous-post` to your themes post navigation theme selector.

```javascript
// Runs on page load, the initial post.
jQuery( document ).ready( function() {
    jQuery( 'div.previous-post' ).find( 'a' ).attr( 'rel', 'prev' );
});

// Runs once a post has loaded.
jQuery('body').on( 'alnp-post-loaded', function( e ) {
    jQuery( 'div.previous-post' ).find( 'a' ).attr( 'rel', 'prev' );
});
```

Another would be to find the source of the post navigation function within your theme and apply the `rel="prev"` attribute to the previous post link.

Either solution applied will then allow Auto Load Next Post to function.

### Im seeing two post navigations, why?

Auto Load Next Post inserts a post navigation for you within the [repeater template](https://github.com/autoloadnextpost/alnp-documentation/blob/master/en_US/repeater-template.md). This is because themes that are well [structured](https://github.com/autoloadnextpost/alnp-documentation/blob/master/en_US/content-and-structure.md#structure) do not include them within the template loops.

Should the theme you are developing or the theme you are using did add a post navigation to the template loops then it would be best to remove the post navigation Auto Load Next Post inserts.

All you have to do to remove it is add this line to your `functions.php` file. Or if you prefer you can use a plugin like [My Custom Functions](https://wordpress.org/plugins/my-custom-functions/) to apply it without modifying your files.

```php
remove_action( 'alnp_load_after_content', 'auto_load_next_post_navigation', 1, 10 );
```

### Only one post loads after the initial post viewed. Why?

This is caused generally because there are two different post navigations. The post navigation the theme provides and the post navigation Auto Load Next Post inserts with the repeater template. Both do not match either due to using a different theme selector or because the post navigation that the theme provides is customized.

To fix this you will need to make sure the post navigation matches from your theme so Auto Load Next Post recognizes it. First, you will need to [remove the post navigation](https://github.com/autoloadnextpost/alnp-documentation/blob/master/en_US/post-navigation.md#im-seeing-two-post-navigations-why) from the repeater template (as shown above) and then hook in the themes post navigation in place instead.

```php
add_action( 'alnp_load_after_content', 'your_theme_post_navigation', 1, 10 );
function your_theme_post_navigation() {
    // Place your themes post navigation here.
}
```

Once done, posts will load without issue.

---

If you have any issues with this guide, or the documentation that is linked throughout, please [open a new issue](https://github.com/autoloadnextpost/alnp-documentation/issues/new) in this repository for it to be reviewed. Thank you!