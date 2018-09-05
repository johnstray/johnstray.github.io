---
title: Documentation
layout: default-gsusers
---

#### [Installation and Configuration](/gs-users/documentation/installation-configuration.html)

##### [Minimum Requirements](/gs-users/documentation/installation-configuration.html#minimum-requirements)
To be able to install and use this plugin, there are a few minimum requirements that will have to be met first. This includes the version of GetSimple CMS you are using, plus the server environment being run on.

##### [Installation](/gs-users/documentation/installation-configuration.html#installation)
You can install this plugin to your GetSimple installation by following these simple instructions. After activation, two default user groups will be created, “Administrators” and “Standard Users”. Once installed, go to the settings tab in the Admin panel, then click on the new “User Management” link in the sidebar. 

##### [Configuration](/gs-users/documentation/installation-configuration.html#configuration)
To configure the plugins settings, go to the Settings tab in the Admin panel, then click on the “User Management” link in the sidebar. Then, in the top-right you will find the settings button. Click the Settings button.

#### [Front-End Display Functions](/gs-users/documentation/front-end-display.html)

##### [Profile Templates](/gs-users/documentation/front-end-display.html#profile-templates)

##### [get_user_profile()](/gs-users/documentation/front-end-display.html#get-user-profile)

---
### Plugin Developer Information

#### [Integrating Your Plugin](/gs-users/documentation/integrating-plugin.html)

##### [Setting up permissions](/gs-users/documentation/integrating-plugin.html#setting-up-permissions)

##### [Checking permissions](/gs-users/documentation/integrating-plugin.html#checking-permissions)

#### [Action & Filter Hooks](/gs-users/documentation/action-filter-hooks.html)
There are currently no Action or Filter Hooks available, however this is a feature that is planned for a future version. When this feature does become available, it will be documented here. Stay tuned for more…

#### [Public Functions](/gs-users/documentation/public-functions/)

##### [add_permissions()](/gs-users/documentation/public-functions/add-permissions.html)
Adds the permissions array to the global list of permissions as used by other functions. This function is designed to be used in an action hook within a plugin, but can be used stand alone if you prefer (eg.: in a theme’s functions.php file).

##### [exec_permission()](/gs-users/documentation/public-functions/exec-permission.html)
This is a filtering function that’s used to determine if the currently logged in user has permission to view the page that you pass to it. It work by taking an output buffer of your page’s content and will only echo it out if permission is granted.

##### [get_user_permission()](/gs-users/documentation/public-functions/get-user-permission.html)
Checks the given permission agains the given user or current user and returns the result. This function is useful when you need to check if a user has permission to perform an action, such as save or delete.

---
### Project Guidelines and Information

#### [Contribution Guidelines](/gs-users/documentation/contributing.html)
Everyone is welcome to make suggestions o how thisi plugin can be improved. You can do this by either submitting an issue to report a bug or discuss a feature, or a pull-request to fix a bug or add a feature. Here you will also find the following information:
##### [Pull Request Guidelines](/gs-users/documentation/contributing.html#pull-request-guidelines)
##### [Issue Reporting Guidelines](/gs-users/documentation/contributing.html#issue-reporting-guidelines)
##### [Repository Structure Information](/gs-users/documentation/contributing.html#repository-structure)
