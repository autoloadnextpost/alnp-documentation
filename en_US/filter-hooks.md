# Auto Load Next Post Documentation

## Filter Hooks

### Template

#### Filter: `alnp_template_redirect`

When Auto Load Next Post makes a request via Ajax, the `/alnp` endpoint is used to force a template redirect to retrieve only the post content from the repeater template located here: `wp-content/plugins/auto-load-next-post/template/content-alnp.php`

Auto Load Next Post will check if the theme (child or parent) has one of it's own. If the theme has not overridden the repeater template file, Auto Load Next Post will load the default template.

If you have overriden the repeater template in your theme or plugin but want to store the repeater template elsewhere, this filter allows you to do that.

In this example, the repeater template is located at `templates/alnp/content-alnp.php` within a theme folder. Simply apply the filter like so to your `functions.php` file of your theme (_if you are not the original theme developer then this would be preferable if added to a child-theme_) and Auto Load Next Post will load the repeater template located there.


```php
function my_repeater_template() {
    return 'templates/alnp/content-alnp.php';
}
add_filter( 'alnp_template_redirect', 'my_repeater_template' );
```

#### Filter: `alnp_template_location`

You have setup your theme selectors, that's great but themes are structured differently from one another and there is no way of detecting how that theme is structured so this filter was put in place should you experience any of the following as you scroll down your posts.

* No content, not even the post title is appearing.
* The permalinks changing in your browser URL bar.
* The comment form and comments for each post load.

If any of them or all happened then the repeater template has not located your theme templates.

To solve this problem you need to find your theme templates location and apply it using this filter. This will then allow Auto Load Next Post to find where the theme templates for your content is located.

In this example, a theme has its template files located at `template-parts/post/` within its theme folder. Simply apply the filter like so to your `functions.php` file of your theme (_if you are not the original theme developer then this would be preferable if added to a child-theme_) and Auto Load Next Post will know where to look the next time you scroll down.

```php
function my_template_location() {
    return 'template-parts/post/';
}
add_filter( 'alnp_template_location', 'my_template_location' );
```

You only need to enter the folder location within the theme you are supporting nothing more.

---

If you have any issues with this guide, or the documentation that is linked throughout, please [open a new issue](https://github.com/AutoLoadNextPost/alnp-documentation/issues/new) in this repository for it to be reviewed. Thank you!