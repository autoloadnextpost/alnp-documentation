# Auto Load Next Post Documentation

This guide will help explain a little about content and structure.

## Content

Auto Load Next Post is designed to display your content in the same style and design of the theme you have active. Unlike other infinite scrolling plugins, no additional CSS is applied.

Your theme provides the templates and styling the plugin requires to display your content when loaded.

## Structure

Structure varies in many ways because of how the theme developer has managed it.

There are at least 5 or more different structures depending on the type of theme made. Some are basic while others are more advanced.

Here are just a few of the folder locations used to manage templates, loops or partial content that is shared across many theme files.

- `templates/`
- `template-parts/`
- `template-parts/post`
- `partials/`
- `loop-templates/`

Auto Load Next Post by default will only look in the themes parent folder for the content files to load. Should the theme placed them elsewhere it is most likley they are in one of these directories above.

> ✏️ Note: Unfortunatley Auto Load Next Post does not automatically identify the location where the templates are located so you will need to [apply a filter](https://github.com/autoloadnextpost/alnp-documentation/blob/master/en_US/filter-hooks.md#filter-alnp_template_location) for Auto Load Next Post to look into the appropriate directory for the content file to be discovered and load.

---

If you have any issues with this guide, or the documentation that is linked throughout, please [open a new issue](https://github.com/autoloadnextpost/alnp-documentation/issues/new) in this repository for it to be reviewed. Thank you!