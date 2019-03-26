# Auto Load Next Post Documentation

## Upgrading from old to new

If you had previously installed Auto Load Next Post before with a version prior to 1.5 then there are two things that you may need to address. Both are really simple and quick to do.

> ✏️ Note: Auto Load Next Post works by registering a unique endpoint to any post type and is used to filter the repeater template that is called with an Ajax request.

### 404 on Ajax Request

In the early versions of Auto Load Next Post the endpoint was not distinct and could have caused a compatibility issue with other plugins that may use the same endpoint so I made a change in version 1.5.

Old: `http://yourdomain.com/hello-world/partial/`

New: `http://yourdomain.com/hello-world/alnp/`

If you having been experiencing a 404 on Ajax requests with the new endpoint then you have to refresh the rewrite rules. Simply go to the **Permalink Settings** page within the WordPress dashboard and press the save button.

Once saved, view any single post with `alnp/` at the end to view the repeater template load.

### Renaming the repeater template

Just as the endpoint was changed for the Ajax request, the repeater template file name was also changed. If you have a custom repeater template file within your theme, make sure it is labelled to the new file name.

Old file name: `your-theme/auto-load-next-post/content-partial.php`

New file name: `your-theme/auto-load-next-post/content-alnp.php`

If you don't find a repeater template file in your theme then you have nothing to worry about.

---

If you have any issues with this guide, or the documentation that is linked throughout, please [open a new issue](https://github.com/autoloadnextpost/alnp-documentation/issues/new) in this repository for it to be reviewed. Thank you!