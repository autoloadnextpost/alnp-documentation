# Auto Load Next Post Documentation

## Post Title

The post title is required to help identify which post the viewer is viewing. Without the post title any anayltics installed can not be used and it also makes your browser history hard to follow back.

Your theme should always have a valid first heading using the `<h1>` element. Applied to the heading there should be at least one class. Most themes use `entry-title`.

When using the [browser developer tools](https://github.com/autoloadnextpost/alnp-documentation/blob/master/en_US/theme-selectors.md#how-to-find-your-theme-selectors) to [find your theme selectors](https://github.com/autoloadnextpost/alnp-documentation/blob/master/en_US/theme-selectors.md#how-to-find-your-theme-selectors), you will find something similar to this. `<h1 class="entry-title">Hello world</h1>`

> Developers: Your theme must **not** be using the first heading on a single post _more_ than once. This is not only bad for the site owners SEO but will make it harder for Auto Load Next Post to identify the post title should there be more than one using the same class.

---

If you have any issues with this guide, or the documentation that is linked throughout, please [open a new issue](https://github.com/autoloadnextpost/alnp-documentation/issues/new) in this repository for it to be reviewed. Thank you!