# Auto Load Next Post Documentation

## Repeater Template

Auto Load Next Post uses a templating system referred to as a "Repeater Template" to manage the front-end display of your Ajax loaded content.

The repeater template will execute over and over to display post content within ALNP loop. This template will look for and load the appropiate template files according to your theme using core WordPress functions such as `locate_template()` and `get_template_part()` to load in the content.

[Action hooks](https://github.com/AutoLoadNextPost/alnp-documentation/blob/master/en_US/action-hooks.md) are also available to use before and after the content.

Should the default repeater template not be suited to your theme structure, it can be overridden by copying it to `wp-content/themes/yourtheme/auto-load-next-post/content-alnp.php`

---

If you have any issues with this guide, or the documentation that is linked throughout, please [open a new issue](https://github.com/AutoLoadNextPost/alnp-documentation/issues/new) in this repository for it to be reviewed. Thank you!