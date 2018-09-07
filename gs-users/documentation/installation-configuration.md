---
title: Installation and Configuration
project: User Management
projectid: gs-users
lang: getsimple
layout: default
---

### Minimum Requirements
To be able to install and use this plugin, there are a few minimum requirements that will have to be met first. This includes the version of GetSimple CMS you are using, plus the server environment being run on.

You will need at least the following to successfully use this plugin:
- GetSimple CMS : version 3.1 - 3.3 (Version 3.4 has not been tested yet)
- Most hosting software should work, but only Apache 2 and Microsoft IIS 7 has been tested
- PHP version 5.3 or later. PHP version 7 has also been tested as compatible.

### Installation
You can install this plugin to your GetSimple installation by following these simple instructions.

1. Download the ZIP file with the plugin from the GetSimple Extend Repository.
2. Unzip it into the `plugins` folder of your GetSimple installation.
3. Ensure your `/data` and `/backups` folders have write permissions.
4. Log in to your GetSimple administration panel.
5. Activate the plugin under the Plugins tab.

After activation, two default user groups will be created, "Administrators" and "Standard Users". The currently logged on user will automatically be added to the Administrators group and granted full permissions, and all remaining users will be added to the Standard Users group and granted a default restrictive set of permissions.

Once installed, go to the settings tab in the Admin panel, then click on the new "User Management" link in the sidebar. From here you will be able to manage all users and groups as required.

### Configuration
To configure the plugins settings, go to the Settings tab in the Admin panel, then click on the "User Management" link in the sidebar. Then, in the top-right you will find the settings button. Click the Settings button.

##### Administrator Login Only
This setting restricts login to the admin panel to users of the Administrators group only. Enabling this setting restrict login to only Administrators, disabling this setting allows all users with appropriate permissions to login.

##### Login Screen Message
This setting allows you to define a custom message that will be displayed on the login screen. For example, you could use a message like this: "This is an ABC company system. You may not use this system to enjoy yourself while working. Smiling is strictly prohibited. By clicking Login you acknowledge that we own your soul. I bet you wish your job didnt suck, but theres nothing you can do about it."

##### User Profile Page
This setting allows you to choose a page on the frontend on which to display user profiles. You also have the option of disabling this feature by selecting "--- NONE ---" from the list. This feature could be useful for blog based website where you can show the profile of post authors. You can read more about how to use this feature later in this documentation, [here](/gs-users/documentation/front-end-display.html#user-profiles). When the GetSimple Blog (GSBlog) plugin is also installed alongside this plugin, the post author field will automatically link to the author's profile page if this feature is enabled.

##### All Users Page
This setting allows you to choose a page to use as a template for displaying a list of all users. You also have the option of disabling this feature by selecting "--- NONE ---" from the list. You can read more about how to use this feature later in this documentation, [here](/gs-users/documentation/front-end-display.html#display-all-users).
