=== Snvk Gallery Metabox ===
Contributors: WordPress.org
Donate link: https://sushilsankwal.wordpress.com/
Tags: gallery,metabox,multiple,snvk,wp images,media gallery,portfolio gallery,video gallery
Requires at least: 5.4
Tested up to: 5.8
Stable tag: 1.0.0
Requires PHP: 5.8
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Snvk media gallery metabox is a wordpress plugin that allow you to add gallery video  metabox in post, page or any custom post type. 

== Description ==

Snvk gallery Image Video metabox plugin allows user to add multiple images to particular post, page or any custom post type.

There the options provided with this plugin i.e. 

1) Dashboard > Snvk Media Gallery > Setting > Setting gallery metabox check post or custom post type for add gallary metabox.

== Website ==
https://sushilsankwal.wordpress.com/

== Installation ==

1. Upload `snvk-media-gallery` to the `/wp-content/plugins/` directory.
2. Activate the plugin through the 'Plugins' menu in WordPress.

OR

1. Goto dashboard > plugin > Add New > select `snvk-media-gallery.zip` file.
2. Activate the plugin through the 'Plugins' menu in WordPress.

== Screenshots ==

1. Snvk media: Click on menu for choose post type
2. Setting: Click setting for image gallery code
3. Upload Media: Click on button upload for image upload

== Changelog ==
= 1.0.0 = 

== Upgrade Notice ==
= 1.0.0 = 
Added plugin support for meta box , custom post type,
pages,template . 

== Frequently Asked Questions ==

= How to installation Snvk Media Gallery plugin =

1. Upload `snvk-media-gallery` to the `/wp-content/plugins/` directory.
2. Activate the plugin through the 'Plugins' menu in WordPress.

== PHP CODE ==


`<?php
 $snv_mediagallery = get_post_meta(get_the_ID(),'snv_mediagallery', TRUE);
        $snv_mediatitle   = get_post_meta(get_the_ID(),'snv_mediatitle',  TRUE);
        $snv_mediaurl     = get_post_meta(get_the_ID(),'snv_mediaurl',  TRUE);

        $snv_arraycombine =  array_map(null,$snv_mediagallery,$snv_mediatitle,$snv_mediaurl);

        if(is_array($snv_arraycombine))
        {
            
            foreach($snv_arraycombine as $snv_content)
            {
               
                //file url 
                echo esc_html($snv_content[0]);
                //file title
                echo esc_html($snv_content[1]);
                //media url for video
                echo esc_html($snv_content[2]);

            }

        }
?>`        