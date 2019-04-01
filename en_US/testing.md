# Auto Load Next Post Documentation

## Testing

Testing or debugging is a common thing for developers but users may have very little knowledge on how to go about doing so. This guide will help you figure out how to test with Auto Load Next Post.

### Beta Testing

First and foremost, I want to say thank you if you are beta testing or interested in beta testing future releases. Your feedback is important to making Auto Load Next Post better.

You can [download the beta tester](https://github.com/AutoLoadNextPost/alnp-beta-tester/releases). I would always recommend beta testing in a staging environment.

### Debugging a White Screen or Error 500

If you find a white screen or error 500 that usually means something has triggered a PHP error, but errors are hidden on your server. To find out the cause of the error you have two choices:

1. Look at your server error logs and find the latest ‘fatal error’.
2. Enable [WP_DEBUG](http://codex.wordpress.org/WP_DEBUG) mode and view the page again.

Enabling `WP_DEBUG` involves editing your `wp-config.php` file and changing, or adding if its not there:

```php
define( 'WP_DEBUG', true );
```

When this is done, a more useful error message should be shown. Most of the time this contains the name of the plugin and the line number causing the issue allowing you to act.

### Debugging JavaScript

Debugging the Javascript for Auto Load Next Post is available with console logs. If you want to read the console logs with the browsers developer tools you will need to enable `SCRIPT_DEBUG` and `ALNP_DEV_DEBUG` to `true`.

By default your `wp-config.php` file will not have `SCRIPT_DEBUG` set for you so you will need to add it.

```php
// Enables none minified assets to load.
define( 'SCRIPT_DEBUG', true );
```

Once you have this added, Auto Load Next Post will load the unminified version of the Javascript on the front end.

To view the developers version, also add `ALNP_DEV_DEBUG` to your `wp-config.php` file but only if you are a developer yourself and looking to make a change, addition or improvement to the script.

```php
// Enables the development version of the JavaScript to load.
define( 'ALNP_DEV_DEBUG', false );
```

---

If you have followed the instructions above to enable `WP_DEBUG`. Auto Load Next Post also allows you to...

## Debugging Functionality Issues

If something is not working after installing a beta, the best thing to do is to narrow down the cause. To do this you can temporarily:

* Switch to a default WordPress theme and test again.
* Disable all other plugins except for Auto Load Next Post itself, retest, and re-activate plugins until the issue occurs. This will help you find the culprit.

## Memory Issues

If after doing the above steps you find that you are hitting the memory limit, you can increase WordPress’ limit. [See here](http://docs.woothemes.com/document/increasing-the-wordpress-memory-limit/).

---

If you have any issues with this guide, or the documentation that is linked throughout, please [open a new issue](https://github.com/autoloadnextpost/alnp-documentation/issues/new) in this repository for it to be reviewed. Thank you!