# Auto Load Next Post Documentation

## Theme Selectors

When you view the settings page of Auto Load Next Post you will be presented with theme selectors.

![Auto Load Next Post - Settings - Theme Selectors Section](https://raw.githubusercontent.com/AutoLoadNextPost/alnp-documentation/master/assets/wp-admin/alnp-settings-theme-selectors-section.png)

Each theme is different so in order for Auto Load Next Post to work, the theme selectors must be set according to the theme you currently have active for each section.

> If you see a notice at the top of the settings page as shown in the screenshot above then you can skip setting up Auto Load Next Post. If not, please continue reading this article.

The first three selectors are necessary for Auto Load Next Post to work. The first is the content container, the primary container where the post content is loaded in. This is where the next posts will load as the viewer scrolls down reading your content.

The second is the post title. This is used to identify which article the viewer is reading and if enabled it allows Google Analytics or other analytics if applied to track the posts being viewed.

The third selector is used to identify the post to load next, if any. The fourth is optional and is used to remove the comments container that holds the comments form and comments. This also includes removing the comments container from the initial post.

When Auto Load Next Post is activated, default theme selectors are set for you. These theme selectors are the most commonly used in any WordPress theme. If they don’t work for your theme then you need to find the matching theme selectors.

I recommend looking at the [CSS selectors reference](https://www.w3schools.com/cssref/css_selectors.asp) at w3schools.com if you are not familar with CSS to help you.

### Default Theme Selectors

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

If you are using Safari 10 or above on Mac, ensure that the **Develop** menu is in the menu bar. If not, enable it under `Safari > Preferences > Advanced`. Then under **Develop**, click on **Show Web Inspector**.

#### Content container

Now to first find the content container of your theme. For example you may be looking for `<main class=“site-main”>`.

As I said from the start, each theme is different so it maybe something different or similar. If the theme is well developed and follows WordPress theme code standards then it should be easy to find.

Once you have found the content container, go to the settings page and place the element name first followed by the class name like so `main.site-main` in the content container field.

> If the element has more than one class applied then only enter the first class. This is 99% the main class. If there is not a class but an ID then simply enter the element name followed by the ID name instead.

#### Post title

Next will be the post title. This one in particular I find does not change from the many themes that I have looked at so you may find that you do not need to change this one.

This will be the first heading `<h1 class="entry-title">` but may be added differently with a featured image depending on how the theme is developed.

#### Post navigation

Finally, the post navigation. Auto Load Next Post reads the post navigation once the user has reached or is near the end of the initial post to load the next post. This is a crucial step. Unfortunately there is no guarantee that your theme may have a post navigation on a single post. Should that be the case you will need to [apply one](https://github.com/autoloadnextpost/alnp-documentation/blob/master/en_US/post-navigation.md).

> In the future, the post navigation selector will not be required as the next post will be identified via a database query. This will support themes that do not have a single post navigation on single posts.

Once you have all your theme selectors entered in the settings page of Auto Load Next Post, press **Save Changes**.

After that, view any single post and scroll down to see if the next post loads. If another post loads, then the setup was successful. If not and you are getting only parts or a constant loop of nothingness then the repeater template also needs to be adjusted.

For more information, view the [repeater template](https://github.com/autoloadnextpost/alnp-documentation/blob/master/en_US/repeater-template.md) guide.

<!-- link "apply one" to the post navigation documentation -->


### Use the theme customizer

To make things easier between switching from viewing the settings page and a single post while using the developer tool to inspect your theme selectors. You can find the same settings in [the WordPress theme customizer](https://raw.githubusercontent.com/autoloadnextpost/alnp-documentation/master/assets/theme-customizer-theme-selectors.png) under the Auto Load Next Post section.

Once you have opened the WordPress theme customizer, view any single post or view your blog archive (or the frontpage depending if you have set a frontpage and blog archive from the **Reading** settings in WordPress), then the Auto Load Next Post section will appear. Enter it and the plugin settings will show. From there you can enter the theme selectors the same way as the settings page and save them by pressing the **Publish** button.

> ℹ️ Do not forget to have the developer tools open when viewing a single post to help you find your theme selectors.

## For theme developers

If you are a theme developer submitting your WordPress theme to the WordPress.org theme directory, then you may want to [add theme support](https://github.com/autoloadnextpost/alnp-documentation/blob/master/en_US/add-theme-support.md) for Auto Load Next Post. Using the theme selectors you just found you can add theme support so your users don't have to follow the same process in finding them.

The next time your theme is installed/updated with Auto Load Next Post installed, the theme selectors will be set automatically for the theme upon activation.

For more information, view the [Add Theme Support](https://github.com/autoloadnextpost/alnp-documentation/blob/master/en_US/add-theme-support.md) guide.


---

If you have any issues with this guide, or the documentation that is linked throughout, please [open a new issue](https://github.com/autoloadnextpost/alnp-documentation/issues/new) in this repository for it to be reviewed. Thank you!