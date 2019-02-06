# Auto Load Next Post Documentation

## Theme Selectors

When you view the settings page of Auto Load Next Post you will be presented with theme selectors.

![Auto Load Next Post - Settings - Theme Selectors Section](https://raw.githubusercontent.com/AutoLoadNextPost/alnp-documentation/master/assets/wp-admin/alnp-settings-theme-selectors-section.png)

Each theme is different so in order for Auto Load Next Post to work, the theme selectors must be set according to the theme you currently have active for each section.

> If you see a notice at the top of the settings page as shown in the screenshot above then can skip setting up Auto Load Next Post. If not then please continue reading this article.

The first three selectors are necessary for Auto Load Next Post to work. The first is the content container, the primary container where the post content is loaded in. This is where the next posts will load as the viewer scrolls down reading your content.

The second is the post title. This is used to identify which article the viewer is reading and if enabled it allows Google Analytics or other analytics if applied to track the posts being viewed.

The third selector is used to identify the post to load next, if any. The fourth is optional and is used to remove the comments container that holds the comments form and comments. This also includes removing the comments container from the initial post.

When Auto Load Next Post is activated, default theme selectors are set for you. These theme selectors are the most commonly used in any WordPress theme. If they don’t work for your theme then you need to find the matching theme selectors.

I recommend looking at the [CSS selectors reference](https://www.w3schools.com/cssref/css_selectors.asp) at w3schools.com if you are not familar with CSS to help you.


#### Default Theme Selectors

By default we set each theme selector with the element followed by a `.class` or `#id`.

| Selector | Value |
| -------- | ----- |
| Content Container | `main.site-main` |
| Post Title | `h1.entry-title` |
| Post Navigation | `nav.post-navigation` |
| Comments Container | `div#comments` |


### How to find your theme selectors

First, make sure that you are viewing a single post on the site you are setting up Auto Load Next Post on. Then depending on your browser, you need to open the developer tools to inspect the theme elements.

You will most likely find the hot key to be **F12** on your keyboard. You will then see something like this.

![Developer tool](https://raw.githubusercontent.com/autoloadnextpost/alnp-documentation/master/assets/developer-tools-firefox.jpg)


### Theme customizer

To make things easier between switching from viewing the settings page and a single post while using the developer tool to inspect your theme selectors. You can find the same settings in [the WordPress theme customizer](https://raw.githubusercontent.com/autoloadnextpost/alnp-documentation/master/assets/theme-customizer-theme-selectors.png) under the Auto Load Next Post section.

Once you have opened the WordPress theme customizer, view any single post or view your blog archive (or the frontpage depending if you have set a frontpage and blog archive from the **Reading** settings in WordPress), then the Auto Load Next Post section will appear. Enter it and the plugin settings will show. From there you can enter the theme selectors the same way as the settings page and save them by pressing the **Publish** button.


### Inspecting your theme

> ℹ️ Do not forget to have the developer tools open when viewing a single post on your website.


#### Content Container

Now to first find the content container of your theme. For example you may be looking for `<main class=“site-main”>`.

As I said from the start, each theme is different so it maybe something different or similar. If the theme is well developed and follows WordPress theme code standards then it should be easy to find.

Once you have found the content container, go to the settings page and place the element name first followed by the class name like so `main.site-main` in the content container field.

> If the element has more than one class applied then only enter the first class. This is 99% the main class. If there is not a class but an ID then simply enter the element name followed by the ID name instead.


#### Post title

Next will be the post title. This one in particular I find does not change from the many themes that I have looked at so you may find that you do not need to change this one.

This will be the first heading `<h1 class="entry-title">` but may be added differently with a featured image depending on how the theme is developed.


#### Post navigation

Finally, the post navigation. Auto Load Next Post reads the post navigation once the user has reached or is near the end of the initial post to load the next post. This is a crucial step. Unfortunately there is no guarantee that your theme may have a post navigation on a single post. Should that be the case you will need to apply one.

> In the future, the post navigation selector will not be required as the next post will be identified via a database query. This will support themes that do not have a single post navigation on single posts.

Once you have all your theme selectors entered in the settings page of Auto Load Next Post, press **Save Changes**.

After that, view any single post and scroll down to see if the next post loads. If another post loads, then the setup was successful. If not and you are getting only parts or a constant loop of nothingness then the repeater template also needs to be adjusted.

For more information, visit the [repeater template](https://github.com/autoloadnextpost/alnp-documentation/blob/master/en_US/repeater-template.md) documentation.

<!-- link "apply one" to the post navigation documentation -->


## For theme developers

If you are a developer submitting your WordPress theme to the WordPress.org theme directory then maybe you want to add theme support with the theme selectors you just found so your users don't have to follow the same process.

Simply use `add_theme_support` function for Auto Load Next Post as shown in the example below and the next time your theme is used with Auto Load Next Post, the theme selectors will be set automatically.

[add_theme_support](https://developer.wordpress.org/reference/functions/add_theme_support/) must be called in your theme's functions.php file to work and it must be hooked to `after_setup_theme`. See example below.

```php
/**
 * Add theme support for Auto Load Next Post by setting the 
 * theme selectors to be applied once the theme is activated. 
 */
function add_alnp_theme_support() {
  add_theme_support( 'auto-load-next-post', array( 
    'content_container' => 'main.site-main',
    'title_selector' => 'h1.entry-title',
    'navigation_container' => 'nav.post-navigation',
    'comments_container' => 'div#comments',
    'load_js_in_footer' => 'no',
    'lock_js_in_footer' => 'no',
  ) );
}
add_action( 'after_setup_theme', 'add_alnp_theme_support' );
```

---

If you have any issues with this guide, or the documentation that is linked throughout, please [open a new issue](https://github.com/AutoLoadNextPost/alnp-documentation/issues/new) in this repository for it to be reviewed. Thank you!