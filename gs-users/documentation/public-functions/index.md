---
title: Public Functions
project: User Management
projectid: gs-users
lang: getsimple
layout: default
---

#### add_permissions()
Adds the permissions array to the global list of permissions as used by other functions. This function is designed to be used in an action hook within a plugin, but can be used stand alone if you prefer (eg.: in a theme's functions.php file).

#### exec_permission()
This is a filtering function that's used to determine if the currently logged in user has permission to view the page that you pass to it. It work by taking an output buffer of your page's content and will only echo it out if permission is granted.

#### get_user_permission()
Checks the given permission agains the given user or current user and returns the result. This function is useful when you need to check if a user has permission to perform an action, such as save or delete.
