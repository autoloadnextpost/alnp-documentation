# Auto Load Next Post Documentation

## Add Theme Support

Adding support for Auto Load Next Post in your theme is great way for users to install the plugin with ease should you be sharing the theme for free to the WordPress community or selling it. Auto Load Next Post is designed for developers to help users skip the process of setting up the plugin.

The [add_theme_support](https://developer.wordpress.org/reference/functions/add_theme_support/) function is used to set the required theme selectors and set the plugin's JavaScript to run in the footer.

Should the plugin only run if the JavaScript is set in the footer, you can force a lock to hide the option to remove it from the plugin settings page. This will help prevent a user error should it be disabled.

Copy and paste the code snippet below to your theme's `functions.php` to add support and it must be hooked to `after_setup_theme`.

> ✏️ Note: Don't forget to change the theme selectors to match your theme selectors that you have used when developing your theme.

```php
/**
 * Adds theme support for Auto Load Next Post.
 */
function add_alnp_theme_support() {
  add_theme_support( 'auto-load-next-post', array(
    'content_container' => 'main.site-main',
    'title_selector' => 'h1.entry-title',
    'navigation_container' => 'nav.post-navigation',
    'comments_container' => 'div#comments',
  ) );
}
add_action( 'after_setup_theme', 'add_alnp_theme_support' );
```

To set the JavaScript of Auto Load Next Post to load from the footer, simply add `load_js_in_footer` as a variable and set it to `yes`.

```php
/**
 * Adds theme support for Auto Load Next Post and loads in the footer.
 */
function add_alnp_theme_support() {
  add_theme_support( 'auto-load-next-post', array(
    'content_container' => 'main.site-main',
    'title_selector' => 'h1.entry-title',
    'navigation_container' => 'nav.post-navigation',
    'comments_container' => 'div#comments',
    'load_js_in_footer' => 'yes',
  ) );
}
add_action( 'after_setup_theme', 'add_alnp_theme_support' );
```

To force the JavaScript of Auto Load Next Post to load only from the footer, simply add `lock_js_in_footer` as a variable and set it to `yes`. You must also have it set to load in the footer to enable the lock.

```php
/**
 * Adds theme support for Auto Load Next Post
 * and is locked and loading from the footer.
 */
function add_alnp_theme_support() {
  add_theme_support( 'auto-load-next-post', array(
    'content_container' => 'main.site-main',
    'title_selector' => 'h1.entry-title',
    'navigation_container' => 'nav.post-navigation',
    'comments_container' => 'div#comments',
    'load_js_in_footer' => 'yes',
    'lock_js_in_footer' => 'yes',
  ) );
}
add_action( 'after_setup_theme', 'add_alnp_theme_support' );
```

If you happen to be supporting Auto Load Next Post via a plugin, a simple additional variable simply allows the plugin to tell the user so via the plugin settings page. Simply add `plugin_support` as a variable and set it to `yes`.

```php
/**
 * Adds theme support for Auto Load Next Post
 * and notifies the user that the theme is supported via a plugin.
 */
function add_alnp_theme_support() {
  add_theme_support( 'auto-load-next-post', array(
    'content_container' => 'main.site-main',
    'title_selector' => 'h1.entry-title',
    'navigation_container' => 'nav.post-navigation',
    'comments_container' => 'div#comments',
    'plugin_support' => 'yes',
  ) );
}
add_action( 'after_setup_theme', 'add_alnp_theme_support' );
```

---

If you have any issues with this guide, or the documentation that is linked throughout, please [open a new issue](https://github.com/autoloadnextpost/alnp-documentation/issues/new) in this repository for it to be reviewed. Thank you!
