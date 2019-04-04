# Auto Load Next Post Documentation

## Possible Issues

If you are facing an issue with Auto Load Next Post then this guide may help you understand why and how it can be fixed.

Here are just a few that is most likley because of a permalink issue. Either Auto Load Next Post did not register the custom endpoint it requires or your permalink structure is not friendly.

### Loads the whole page and not just the content

This problem is caused due to the permalink structure that you have. Here are a few permalink structures that **do not work** for Auto Load Next Post:

* Have the author before the post slug: `/%author%/%postname%/`
* Have the post category before the post slug: `/%category%/%postname%/`

These structures cause the custom endpoint for Auto Load Next Post to redirect to the original permalink for the post while Ajax is loading the content. So in the end you are importing the whole page and not the content from the custom repeater template that is suppose to load via Ajax requests.

It's important that you have a clean friendly permalink structure so Auto Load Next Post can work it's magic.

The default permalink structures work best with Auto Load Next Post.

* Day and name: `/%year%/%monthnum%/%day%/%postname%/`
* Month and name: `/%year%/%monthnum%/%postname%/`
* Post name: `/%postname%/` (Recommend)

### Getting an error 404 when Ajax makes a request

Most likley this is caused because you previously had an older version and have now updated to the latest version. This is easly fixed. [See the upgrade guide for more](https://github.com/autoloadnextpost/alnp-documentation/blob/master/en_US/upgrading.md#404-on-ajax-request).

### Auto Load Next Post endpoint did not register

Simply go to the permalink settings page in your WordPress dashboard and press the save button to refresh. That will flush all the rewrite endpoints and register Auto Load Next Post endpoint.

### Not loading when using a Cache or Minification plugin?

If this is happening then you need to exclude **Auto Load Next Post** from being cache, JS combined or minified with the Cache or Minification plugin you are using on your WordPress website.

If you are able to do so then you need to exclude the following files:

1. `wp-content/plugins/auto-load-next-post/assets/js/frontend/auto-load-next-post.min.js`
2. `wp-content/plugins/auto-load-next-post/assets/js/libs/scrollspy.min.js`
3. `wp-content/plugins/auto-load-next-post/assets/js/libs/jquery.history.js`

---

If you have any issues with this guide, or the documentation that is linked throughout, please [open a new issue](https://github.com/autoloadnextpost/alnp-documentation/issues/new) in this repository for it to be reviewed. Thank you!