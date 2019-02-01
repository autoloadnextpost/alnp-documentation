# Auto Load Next Post Documentation

## Action Hooks

Auto Load Next Post enables the ability to add extra content or a feature and one of the easiest way to acheive that is the usage of an action hook. Action hooks provide developers with a means of extending functionality with just a few lines of code.

Within the default repeater template, many have been provided for the query loop and content, both before and after.

To show these action hooks in action, a developer tool is available to show the action hooks in action as you scroll down to view your posts.

> ℹ️ Note: Auto Load Next Post requires to be setup already for the tool to be of use.


### The Loop

Use this action hook to display content before the loop.

`add_action( 'alnp_load_before_loop', 'your_function_name' );`

Use this action hook to display content after the loop.

`add_action( 'alnp_load_after_loop', 'your_function_name' );`

### The Content

Use this action hook to display content before the content.

`add_action( 'alnp_load_before_content', 'your_function_name' );`

Similar to the one above only this action hook is specific to the post format of the loaded post.

`add_action( 'alnp_load_before_content_post_format_' . $post_format, 'your_function_name' );`

Use this action hook to display content after the content.

`add_action( 'alnp_load_after_content', 'your_function_name' );`

Similar to the action hook above only this action hook is specific to a single post format of the loaded post.

`add_action( 'alnp_load_after_content_post_format_' . $post_format, 'your_function_name' );`

Replace `$post_format` with one of the supported formats. See [Post Formats](#) for a list of supported formats that you can use to display content for a specific post format.

An example of adding content to a specific post format with one of the action hooks.

```php
function your_function_name(){
  echo 'This video is awesome. Share it with your friends!';
}
add_action( 'alnp_load_after_content_type_video', 'your_function_name' );
```

So whenever a post that is formatted for a video, after the content it will display whatever you want it to display.

> ℹ️ Dev Note: Not all themes support post formatting but if you are creating a WordPress theme yourself with post formatting then this would add extra support.

---

If you have any issues with this guide, or the documentation that is linked throughout, please [open a new issue](https://github.com/AutoLoadNextPost/alnp-documentation/issues/new) in this repository for it to be reviewed. Thank you!