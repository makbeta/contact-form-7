Contact Form 7
==============

This is the development repository for Contact Form 7, a WordPress plugin that lets you manage contact forms on your website. A copy of the plugin package is downloadable from the [WordPress.org Plugin Directory](https://wordpress.org/plugins/contact-form-7/).


License
-------

This plugin is released under the GNU General Public License Version 2 (GPLv2). For details, see [license.txt](license.txt).


Getting started
---------------

Install the Contact Form 7 plugin through the **Add Plugins** screen (**Plugins > Add New**). After activating the plugin, the **Contact** menu will appear in the left sidebar. For basic usage, read [Getting started with Contact Form 7](https://contactform7.com/getting-started-with-contact-form-7/) and other documentation on the [official website for the plugin](https://contactform7.com/).


Support
-------

Support for this plugin is primarily provided within the volunteer-based WordPress.org support forums. The official website also provides custom development and professional support services. See [Support](https://contactform7.com/support/) for more information.


Contributing to Contact Form 7
------------------------------

You can contribute to the project of Contact Form 7 in several ways. For more information, see [How to contribute to Contact Form 7](https://contactform7.com/contributing/).


<br/><br/><p align="center"><img src="https://s.w.org/style/images/codeispoetry.png?1" alt="Code is Poetry." /></p>


Added Features
--------------

A list of features that are present in this repository, but were not accepted by the Contact Form 7 plugin.

### Upload Folder Outside the `wp-content` Directory
For many modern hosts, such as Pantheon, the files reside at an different folder path than `wp-content/uploads` and `wp-content/uploads` is just an alias. In those cases, the uploads fail to be saved and attached to the email. Multiple issues were raised by the community: [154](https://github.com/rocklobster-in/contact-form-7/issues/154), [475](https://github.com/rocklobster-in/contact-form-7/issues/475), [707](https://github.com/rocklobster-in/contact-form-7/issues/707), [1282](https://github.com/rocklobster-in/contact-form-7/issues/1282), sadly [the author has rejected the request](https://github.com/rocklobster-in/contact-form-7/pull/708) for the plugin functionality to be extended, [citing security isses](https://github.com/rocklobster-in/contact-form-7/issues/507), which are not clearly stated [or explained]((https://github.com/rocklobster-in/contact-form-7/issues/507#issuecomment-1044129543)) even [when questioned](https://github.com/rocklobster-in/contact-form-7/issues/707#issuecomment-1350732394). 
This repository presents a solution for the problem. **Note** be sure that your upload folder is a private folder, not a publically accessible one to ensure security and integrity of the server. 

To implement:
* Install the plugin from the repository on your site, or replace installed plugin with source code from this repository
* Define `WPCF7_UPLOADS_TMP_DIR` to your _wp-config.php_ file and point to the folder path of your upload folder.
* Define `WPCF7_UPLOADS_TMP_IN_WP_CONTENT` variable to your _wp_config.php_ file and set it to `false`.

For Pantheon servers the snippet would look like this:
```php
define( 'WPCF7_UPLOADS_TMP_IN_WP_CONTENT', false );
define( 'WPCF7_UPLOADS_TMP_DIR', '/private' );
```

### Keep Uploaded Files
In some instances the uploaded files must be kept. This repository also provides for this solution.
**Note** be sure that your upload folder is a private folder, not a publically accessible one to ensure security and integrity of the server. 


To implement:
* Install the plugin from the repository on your site, or replace installed plugin with source code from this repository
* Define `WPCF7_KEEP_UPLOADS` variable to your _wp_config.php_ file and set it to `true`.

Example:
```php
define( 'WPCF7_KEEP_UPLOADS', true );
```
