---
title: ChangeLog
layout: default-gsblog
---

### Version 3.5.0 ~ Beta
#### Feature Enhancements
- [#006] Created a new Post Image uploader/selector
- [#120] Added support for layout templates in the active theme's directory
- [#110] More enhancements to the Posts Admin Page
- Created post filtering mechanisim to compliment the search function
- Modified the layout of the posts list to now include a bit more information about a post
- New layout now includes a mini version of the image thats attached to the post
- Action icon changed to now use the FontAwesome library of icons.

#### Back End (Admin) Changes
- [#111] Enhancements to the Category Management Page
- Category names are now editable. Click the new edit button will reveal a text field for updating the name.
- Number of posts in category now shown next to category name
- Post quantity links back to post management page with a filter applied to only show posts from the click category.
- Filtering or sorting of Categories by name or popularity (# of posts) is now possible
- New category action icons using FontAwesome library.
- Page layout cleaned up to look much better and inline with the new styles.
- [#134] Added 'Save Post' button to Post Editor page.
- [#104] Better metadata management for search engine optimisation
- Added the ability to include a description for each of the core pages; categories, archives, tags, search results
- Descriptions are used in the html "description" meta tag.
- New settings page added specifically for SEO based settings such as the page descriptions.
- Option to enable showing the descriptions on the respective page's list-layoutBefore template.
- Placeholders available to description texts: {archive}, {category}, {tag}, {search}, {results}.

#### Frontend UI Improvements
- [#085] Added read more link to layout-list.php file.

#### Bug Fixes
- [#119] Fixed php parse error: missing '$' on lines 417 and 418 in Blog.php
- [#119] Fixed php parse error: missing ',' on line 716 in Blog.php

#### Core Code Changes
- [#110] Significant improvements to the search class method to also include filtering.
- Allows searching for keyword in specific node, combining search and filter functions
- Removed the now redundant filtering class method, but mapped it to search to allow backwards compatibility

### Version 3.4.4 ~ Latest Stable
#### Back End (Admin) Changes
- [#128] Created a more uniform method of displaying success/error messages that prevents displaying on the frontend.
- [#116] Dropped support for old UserManagement plugin

#### Bug Fixes
- [#109] Fixed class constructor after previous rewrite. Fixes the message 'Blog Settings Successfully Saved!' Message always being displayed.
- [#115] Fixed alignment of input field boxes in the metadata section of the post editor.
- [#117] Hide tags when there are no tags attached to a post.
- [#119] Removed some unused variable declarations.
- [#122] Fixed incorrect double slash in GSBlog->listPosts function.
- [#125] Unpublished posts (dated in the future) could not be viewed when accessed directly for previewing.
- [#131] Fixed trailing comma showing at the end of the list of tags.
- [#132] Fixed PHP parse errors for improper method of accessing array element.
- [#133] Fixed CKEditor triggered twice on Post Editor page.
- [#135] Fixed Incorrect values used in html input/label tag attributes, causing the `blogurl` setting not to save.
- [#138] Fixed PHP fatal error: Using string offset as an array in customFields.php

### Version 3.4.3
#### Feature Enhancements
- [#095] A few minor imrovements to the RSS generator:
- `<description>` now respects the excerpt length setting.
- Added `<content:encoded>` tag to include the full text including html of the post.
- Added `<pubDate>` tag to each post in the feed.
- Added `<generator>` tag to the `<channel>`.
- [#102] Minor enhancements to the Posts Management page:
- Search button is now hidden when there are no posts in the database.
- The search field is now shown by default when listing the results of a search. Allows use of the 'Cancel' button to clear a search.
- When showing the results of a search and no posts were found, a new message is now displayed instead of the default no posts message.
- Covnerted no posts message to use the `<h5>` tag instead of `<strong>`, added centre alignment and fixed missing closing tag. `<h4>` used for notice on no search results.
- The page navigation container box is now hidden when there are no posts on the page. 
- Category Admin Page: Removed the uncecessary 'Or Cancel' button in the 'Add Category' box
- Added unversal alignment layouts and properties for the search box on the posts admin page and the add category box on the category admin page.

#### Bug Fixes
- [#097] Fixed unprotected quotes in Russian language file.
- [#098] Fixed critical error where adding a node to the settings xml would fail because an array was given when a string was expected.
- [#100] Fixed "Search Engine Suicide" bug where the meta description of a multi-post page would contain the excerpt of the last post on the page.
- [#105] Corrected a spelling error in a variable name in `versionCheck.php`.
- [#106] Removed a runaway closing `</p>` tag on the Post Editor page.

#### Core Code Changes
- [#090] Implemented a function that will read, reorder, then write the `plugins.xml` file so that the 'user-managment.php (MultiUser)' plugin will work as expected.
- [#109] Rewrote the class constructor function: Added check for missing or redundant settings in the settings file and update if required.

#### Languages
- [#099] Updates to the Russian language file thanks to f30d0r.

### Version 3.4.2
#### Back End (Admin) Changes
- [#088] Added paging of posts list on Post Management page. Qty per page is determined by "# posts per page" blog setting.
- [#088] Implemented Column width limiting on Post Management page; Prevents line-wrapping, making things a bit neater.
- [#088] Removed redundant "Custom Fields" button on Post Management page.
- [#087] Moved RSS Feed Title and Description to the correct settings page. Cleaned up layout of Main Settings page.
- [#088] Post searching feature now available on Post Management page.
- [#064] Sorted out the Spanish es_ES language file. Some translations may be incomplete or incorrect.

#### Bug Fixes
- [#074] Missed part of this fix... Whoops...

#### Front End UI Improvements
- [#083] Category and Date are now links to their relevant category or archive page when showing a post or in a list.
- [#081] All list sections (categories, archives, tags, search) now include layout-listBefore and layout-listAfter files.

#### Code Changes
- [#080] Even better date internationalisation on both the front end and the backend. Creating/editing a post will now accept any date format supported by `strtotime()`, including "today".

### Version 3.4.1
#### Bug Fixes
- [#---] Some language files were missing some commas in the array. Added html entities for certain characters.
- [#075] German and French language files were missing some commas in the array.
- [#075] German language file had 9 missing strings.
- [#074] Fixed issues with post count in categories: casting of XMLobjects to string, a few missing punctuation marks, updated en_US language file to add Categories to Archvie Post Count string.
- [#074] Fixed 'illegal offset' warning in `show_blog_category()` function. XMLoject is now cast properly as a string to use as array ofset. This prevented `show_blog_categories()` from being able to count the posts.
- [#076] Fixed language string concatenated use for 'Manage Custom Fields'.
- [#077] Fixed incorrect language string references for the RSS Auto-Importer Settings page.
- [#079] Fixed some issues with the CustomFields Manager. Also added a sidebar button so that CFM could actually be used.
- [#080] Much better handling of date format internationalisation.

#### Front End UI Improvements
- [#074] Properly implemented post counts in categories. This was incomplete in the previous release. Rebuilt methods to make it more robust than originally planned.

### Version 3.4.0
#### Bug Fixes
- [#068] Fixed string not translated in `generateRSSFeed()`
- [#067] Fixed rss.php issues ... Finally...
- [#043] Fixed syntax error, unexpected ';' - Related to the rss.php issues.
- [#058] Variable `$p['thumbnail']` needed to be casted correctly because it was returning a `SimpleXMLObject` even when empty. This caused an `IF` statement in the layout operate incorrectly.
- [#057] Fixed language setting not being available to language based functions. The language string is now stored in the language files and loaded from there instead of settings.
- [#054] Fixed Advertising code in 'Original' theme causing php warning because the setting wasn't available in fresh installs.
- [#051] Fixed Hierarchical URLs not supported by i18n plugin. A function was updated to use i18n's `find_i18n_url` instead of the core `find_url`
- [#050] Removed obsolete `IF` statement related to versionCheck. This may have been the cause of the slowness!
- [#000] Updated version number definition. I forgot it again...

#### Front End UI Improvements
- [#036] Front-end functions modified to allow lists to be echoed or returned.
- [#056] Image thumbnail paths separated into parts to allow for easier customization in the layout. `IF` statement added to check if an image is included with the post or not.
- [#055] Removed theme layouts and converted to using 2 include files for layout generation. You can customize these as needed.
- [#029] Better handling of date/time formats for different languages. Format string now stored in language file.

#### Back End (Admin) Changes
- [#011] Added 2 actions to allow for compatibility with other plugins, such as 'Auto-open Page Options'.
- [#069] Removed reliance on private server for "What's New" information.


#### Updated Languages
- [#029] Added English (British) Language file to enable date formats for this region.
- [#059] Add German (DE) Language file.
- [#061] Updated English (US) language file with new strings and removed old strings.
- [#061] Updated French (FR) language file with new strings and removed old strings.
- [#035] Updated Spanish (ES) language file with new strings and removed old strings.
- [#034] Updated Italian (IT) language file with new strings and removed old strings.
- [#061] Updated Polish (PL) language file with new strings and removed old strings.
- [#061] Updated Russian (RU) language file with new strings and removed old strings.
- [#062 - #066] Layout of language files changed so that they are much neater and easier to read.

### Version 3.3.1
#### Bug Fixes
- [#039] Fixed runaway string on Help page
- [#038] Fixed hard coded English string in Custom Fields management.
- [#043] Fixed syntax error in rss.php
- [#044] Fixed only 1 blog post showing on main frontend page
- [#045] Fixed RSSBody generation method. Now uses create_excerpt function instead. HTML characters shouldn't show up in there now.

### Version 3.3.0
#### Back End (Admin) Changes
- [#003] Implemented selectable layout templates system
- Re-wrote `show_settings_admin()` function from scratch.
- Removed settings that are no longer needed. Most tasks can now be completed by creating/modifying template file.
- Created function `blog_theme_layouts()` which gets the list of available theme files.
- [#022] Added `pluginManagementFA.js` script : Adds icon to plugin's listing on the Plugin Management admin tab.
- [#021] Updated FontAwesome version to 4.2.0 and changed `$media` from 'screen' to 'print'.
- [#023] Updated website address in plugin registration

#### Front End UI Improvements
- [#003] Implemented selectable layout templates system
- Re-wrote `show_blog_post()` function from scratch. Old: 131 lines, New: 31 lines.
- Created 1 layout: Original. More will be available in future bugfix releases.
- [#003] Modified original layout to add scoped CSS functionality (New in HTML 5.1) : Backwards compatible with most current browsers.
- [#008] Fixed "Go Back" links in posts (sort of). The link is now in the template file. You can change it as needed, or remove it if you like.

#### Bug Fixes
- [#014] Fixed undefined variable in `manage_custom_fields.php`

#### Code Changes
- [#018] Removed social media functions. If you need this, add your own code to a template file.
- [#017] Cleaned up functions and comments in `adminFunctions.php`
- [#020] Cleaned up functions and comments in `frontEndFunctions.php`
- [#019] Moved some HTML sections of the code to separate files in 'html' folder to make for much easier reading and modification of code.
- [#028] Cleaned up functions and comments in common.php
- [#027] Removed redundant CodeMirror files.
- [#020] Moved RSS Auto-Importer functions into it's own file.

#### Updated Languages
- [#016] Added new strings to English en_US language file.
- [#026] Added new strings to Russian ru_RU language file.
- [#025] Added new strings to Italian it_IT language file.
- [#024] Added new strings to Spanish es_ES language file.
- [#041] New Polish pl_PL language file added.

### Version 3.2.4
#### Bug Fixes
- Removed blank line at start of English en_US language file that caused headers to be sent early.
- Fixed `undefined variable $data in frontEndFunctions.php on line 71`. Should have been $post.
- Fixed `undefined variable $data_edit in manage_custom_fields.php on line 28`3. The defining location has been moved outside of an 'if' condition and should be set all the time now. This should also fix Trying to get property of non-object.
- Fixed `undefined variable $blog_data in adminFunctions.php on line 1049`. This variable was not needed there and has been removed.
- Fixed link for "Display CSS: Click here to view available classes and ids". FancyBox JavaScript had not been made availble on that page when Settings was split into multiple pages.

#### Front End UI Improvements
- Separator pipe ( | ) has been removed from the info line. If you really want it back, create a custom layout.

### Version 3.2.3
#### Bug Fixes
- Posts with dates in the future are now hidden in all frontend areas (inc. Archives) but not in admin.
- Date format in RSS feeds should now be standards compliant.
- Language will now be selected based on GetSimple's language or will properly default to English (US) if the language is not available in GS Blog.

#### Updated Languages
- Russian ru_RU language file, thanks to 'Oleg06'.
- Fixed missing strings in Italian it_IT language file.
- Fixed missing strings in Spanish es_ES language file.
- Fixed missing strings in English en_US language file.

### Version 3.2.2
#### Bug Fixes
- Updated version number in `gs-blog.php`. Forgot to do this in the previous version. Updater will now show the correct results.
- Fix PrettyURL setting on Settings admin page. Converted to radio buttons to handle the page separation in settings. 
- Fixed link to show .htaccess example for PrettyURLs. FancyBox script was in the wrong place. It has been moved accordingly.
- Fixed thumbnail as link to post. Link A tag was missing but has now been added again.


### Version 3.2.1
#### Security Fixes
- Added check if defined 'IN_GS' to all php files. This prevents files being loaded directly, rather they need to be called from within GS.
- Updated MagpieRSS from 0.7a to 0.72

#### Code Changes
- MagpieRSS will now use the GS cache instead of trying to create its own. This would fail because of permissions in the plugin dir.
- Added Italian (it_IT) language file, thanks to Nicola Laviola (nikynik)
- Fixed typos and a missing string in `en_US` and `it_IT` language files.
- Fixed issue with RSS Auto-Importer creating blank posts when using content. 
- Fixed author not showing in post.
- Changed strings in en_US language file for descriptions on settings pages.
- CKeditor Bug? Mentioned in the forums, but I couldn't reproduce it. Used given fix anyway.
- Removed outdated language files. As translators come on board, languages will be added.

### Version 3.2.0
#### Back End (Admin) Changes
- Split 'Blog Settings' page into 4 sections : Main, Customisation, Advertisement, Social.
- Moved 'Create Post' link from side-bar to 'Manage Posts' page.
- Moved 'Custom Fields' link from side-bar to 'Manage Posts' page.
- Renamed 'RSS Feeds' to 'RSS Auto-Importer'.
- Added 'Settings' button to 'RSS Auto-Importer' page.
- 'RSS Auto-Importer' related settings are now on their own page.
- HTML Layouts changed to match the GS Admin default layout.
- Plugin is now compatible with the awesome 'Modern Admin' backend theme. Seriously, try it!
- Added setting to RSS Auto-Importer to choose between getting content if available or description with link back to original article.
- Added setting to Settings page to show/hide Post Author.
- Added setting to Settings page for Default Post Author if none is defined. Enter 'hidden' to hide if not defined.
- Added setting to Settings page to show/hide Category.

#### Front End UI Improvements
- Added ability to show Author's name. A default will be shown / or hidden if author not defined. These can be setup in settings.
- Added ability to show the category the post has been saved in. Hidden if not defined.

#### Code Changes
- VersionCheck now gets it's "What's New" messages encoded and will decode them for display.
- Download link updated in VersionCheck.
- `adminController.php` has been merged into `adminFunctions.php`
- `displayPosts.php` merged into `frontEndFunctions.php`
- `pageTitle.php` merged into `frontEndFunctions.php`
- Original Settings button idea ditched along with `settingsButton.php`
- Fixed yet another URL problem in `ckeditor.php`
- Added new strings for Settings and Sidebar buttons to en_US language file. Really need some translators here, please help?
- RSS Auto-Importer now has the ability to search for a `<content:encoded>` tag in rss files, and if it exists, will fill the post with that rather than the description.
- Fixed date localization on Windows based systems.

### Version 3.1.3
#### Back End (Admin) Changes
- VersionCheck updated to include the ability to show What's New information on update page.

#### Bug Fixes
- Fixed constant `'BLOGFILE'` not defined when calling rss.php.
- Added better handling of having no posts on systems where `glob()` returns `'false'`.
- Fixed cache generation : Cache will not generate if there are no posts.
- Fixed 'Delete RSS Feed' link in admin panel.
- Update MagpieRSS to use `explode()` instead of the depreciated `split()`.
- Fixed stupid syntax mistakes. I really shouldn't code whilst tired...

### Version 3.1.2
#### Bug Fixes
- Fixed a URL in `manage_custom_feilds.php`
- Fixed 2 URLs in the Primary Class File `blog.php`
- String `'Directory Successfully Created'` changed to `'File Successfully Created'` for categories XML file in EN_us language file.

### Version 3.1.1
#### Back End (Admin) Changes
- Updated VersionCheck system to use PHP's version_compare() function instead of a simple < or >.
- Added strings to EN_us language file for VersionCheck's admin page status table.

#### Bug Fixes
- Fixed missing semi-colon in `gs-blog.php` causing a syntax error.
- Fixed missing forward-slash for the variable `BLOGPLUGINFOLDER` in `common.php` that caused issues with missing include files and a file copy failure on initial setup.
- Fixed URLs for buttons and links across the admin area.

### Version 3.1
#### Back End (Admin) Changes
- Added Version Checking system
- Created Function
- Function moved to external include file.
- Added strings to en_US language file. Further translations required.
- Added link to version string on admin panel. Points to new Update page.
- Added Update Check page to admin panel under settings.
- Added slug transliteration support - Thanks to Carlos for spotting that I'd missed that while scouring the forums for bugs.

#### Bug Fixes / Code Cleanup
- Core plugin file now somewhat smaller and easier to read.
- Moved Admin Controller function(s) to external include file. Code still needs cleaning.
- Moved Front End Controller function(s) to external include file. Code still needs cleaning.
- Page Title fix function moved to external include file.
- Require_once paths now reference `$thisfile` to make future updating easier.
- Fixed some spelling errors in en_US language file.

### Version 3.0 (Where I took over)
#### Front End UI Improvements
- Page Title is now changed to either the Post's Title, Category Name, or Archive Date
- `$post->title` now only shows on the listing page, not on the individual posts page. This prevents double titles with the above UI fix.
- When `show_blog_categories()` is called and no categories exist, a message is displayed saying "No Categories Exist!"
- When `show_blog_archives()` is called and the archive contains no posts, a message is displayed saying "Nothing in the Archives!"

#### Back End (Admin) Changes
- The blog now has its own tab in the Admin area, which also includes its own sidebar links for each area of configuration.
- Each admin page now has it's own title and description at the top of the page and will also show the version of the plugin you are running.

#### Bug Fixes
- Clicking on Cancel in the post editor will now take you back to the Posts Management page. Previously it would take you to a different plugin, or throw an error if that plugin wasn't installed.
- Fixed Read More links on post excerpts. Previously the link was empty.
- Fixed default values not showing in custom fields when creating or editing a post.
- Removed `<ul>` tags from Archive functions to bring it in line with the rest of the plugin and the standard list format used in GetSimple. You now need to provide your own `<ul>` tags and apply attributes as needed. 
- Fixed improperly closed `<strong>` tags on Help admin page.
- Fixed error `Trying to get property of non-object in frontEndFunctions.php on line 671`.
