=== Pagely MultiEdit ===
Contributors: joshua.strebel 
Tags: admin,formatting,pages,page,cms,multiedit, blocks, editable regions, tinymce, custom fields, pagely, pods
Requires at least: 2.9
Tested up to: 4.1.1
Stable Tag: 0.9.8.5

MultiEdit adds tinyMCE editable "blocks" to WordPress custom page templates. 
== Description ==

One thing I always wished WP would do better is allow for multiple editable content blocks on page templates. This plugin uses custom fields to create simple tinyMCE editable regions on page templates. 

See Instructions and Usage Examples here: [Page.ly MultiEdit plugin](https://pagely.com/multiedit-plugin/)

NOTE: Must be used inside/after the opening loop statement: 
while (have_posts()) : the_post(); 
  multieditDisplay('YourBlockName'); 

Brought to you by: [Pagely WordPress Hosting](https://pagely.com)

Follow [@strebel](http://twitter.com/strebel) and feel free to check out [Pagely](https://pagely.com)


== Installation ==

# [Instructions here](https://pagely.com/multiedit-plugin/)
== Changelog ==
= 0.9.8.5 =
Tested w/ 4.1.1 did some cleanup to make sure we save properly
Hat tip: [rado.at] (https://wordpress.org/support/topic/change-request-tinymce-cleanup?replies=5)
= 0.9.8.4 =
Tested w/ 3.8
= 0.9.8.3 =
* proper plugins_url() usage, Hat tip: [Scott Cariss] (http://wordpress.org/support/topic/plugin-pagely-multiedit-plugin-assets-not-loading-from-https)
* added global $post; to drawMultieditHTML function, Hat Tip [adamnbowen](http://wordpress.org/support/topic/undefined-post-variable)
* Render underscores in Declared names as spaces, and Camelcase as normal case, Hat Tip [adamnbowen](http://wordpress.org/support/topic/feature-camelcase-and-underscores-to-spaces-in-admin)
= 0.9.8.2 =
* Simple tweak to .js file to add new handles used in WP 3.3 
= 0.9.8.1 = 
wp_enqueue_style and wp_enqueue_script.  #facepalm
= 0.9.8 = 
* tested with 3.1.2
* commented out the print_r that shows the array of multi edit elements at the bottom of the admin screen.
* added file_exists to prevent error output for non-existent template file addressing [jmalleck's comment](http://wordpress.org/support/topic/plugin-pagely-multiedit-compatibility-of-multiedit-097-and-wp-301)
* added support for shortcodes (ONLY TESTED WITH [gallery]) in multi-edit regions.  Thanks [Nick Ciske](http://wordpress.org/support/profile/nickciske)
* clean some mce tags from regions, thanks [inpixelitrust](http://wordpress.org/support/profile/inpixelitrust)
* added options page (with advert) to toggle shortcode usage. With shortcodes on it will apply filters to post data.. like displaying tweetmeme buttons.. again.
* added a second param to multieditDisplay function for return, if true will return the value instead of echo. example: Assign content to $foo, `<?php $foo = multieditDisplay('Right',true)?>` then at some other time echo $foo `<? echo $foo ?>`
* added a closing php ?> tag.. go figure.

= 0.9.7 = 
Re-assigned $post->page_template to page.php if "default".  Respects multiedit declaration in header of page.php now. Still need to publish/update the page a couple times before the multi edit tabs appear above tinymce. I figure this is becuase $post->page_template is null until the page is actually saved.
= 0.9.6 = 
Tested with 3.0.. added post.php to array in init check
= 0.9.5 =
* force tinymce to visual mode when saving post
* fixes the bug that main content was being overwritten if saved in html mode
= 0.9.4 = 
* added some trim() to a few places.
= 0.9.3 =
* Did some refactoring, made sure no php notices were being thrown, added a notice if you have existing multiedit regions on the page, then change template to another multiedit enabled template with different declarations.
= 0.9.2 =
* check for empty $post->page_template and ignore
= 0.9.1 =
* changed version number so wp repo will show update
= .9g =
* fixed weird behavior when saving a page not using multiedit.. basically does not load the js
= .9f =
* Fixed bug that would replace tinymce content before save if no multiedit fields avail.  You deleted or changed content, and hit update page and it would put your old content back in.
= .9e =
* Added disabled message if tinymce is not being used.. for now
= .9d =
* Mo betta 
= .9c =
* Better check for edit page and custom template before running 
= .9b =
* Fixed dumb oversight that borked 0.9, plugin can now find the .js and .css file.
= .9 =
* Ported from an [old plugin](http://saint-rebel.com/2008/09/26/multiedit-region-wordpress-plugin/) we wrote.
