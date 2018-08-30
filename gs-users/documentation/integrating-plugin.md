---
title: Integrating Your Plugin
layout: default-gsusers
---

Integrating your plugin with the User Management system is a two step process. The first is to create your permissions array and add it to the system; the second is to check permissions before showing any content on your plugins admin page.

### Setting up permissions
First build an array of permissions to pass into the system. The array is multi-dimensional, but only 2 levels deep in total. The system currently only supports 1 parent level of permissions and 1 child level of permissions. This should be more than sufficient for almost all plugins.

The structure of the array looks as follows:
```php
$my_permissions = array(
    
    'permissions_id' => array(
        
        'name' => "Permission Name",
        'desc' => "Description of this permisson",
        'child_perms' => array(
            'child_perm_id' => "Child Permission Name",
            // etc ...
        )
        
    )
    
);
```
Now you can pass your array of permissions into the User Management system. You do this by calling the permissions action from with your plugin and sending with it your plugin's ID and the array of permissions. This would usually be done in the same file where you call `register_plugin(...)`.

Here's an example:
```php
add_action( 'permissions', 'ass_permissions', array( $plugin_id, $my_permissions ) );
```

### Checking Permissions
The second step of this integration process is to check that a user has the correct permission before processing an action or displaying a page. Permission checking can be done by two methods, depending if you are performing an action or displaying an admin page.

#### Page Filtering
To display an admin page, you will first need to capture the content of your page into a string. This can be done using `ob_start();` and `ob_get_clean();` to create a buffer to store your page in. That buffer can then be passed as an argument to the permissions checking filter. Once you have the buffer of content ready, you'll need to call a filter that will check for the correct permission and echo/print your buffer if the permission is allowed, or drop your buffer and replace it with the Denied template if permission is denied.

Here's how to call the filter:
```php
ob_start();

include( 'my_content' );
echo "<span>This is some more content</span>";

exec_filter( 'checkPermission', array( 'permission_id', ob_get_clean() ) );
```

#### Conditional Check
When performing actions like save or delete, you can do a conditional check of the required permission using a php if condition using the `get_user_permission()` function. Beware, though, that this function is only available when this plugin is installed. There are two solutions to this problem and we'll get to those in just a moment.

Here is an example of how this function can be used:
```php
if ( get_user_permission( 'permission_id' ) ) {
    // Do something here...
}
```
There are two ways to get around the issue of the get_user_permission() not being available when this plugin is not installed on a users system.

The first method is to check if the function exists before actually calling it. If your plugin doesn't need to do this, then this method should be sufficient. Here's how:
```php
if ( function_exists( 'get_user_permission' ) ) {
    get_user_permission( 'permission_id' );
}
```
If your plugin needs to do this quite often, then this method can get quite tedious and start to make your code look messy. The next solution sorts this out by creating the function if it doesn't exist; this way the function is always available even if User Management is not installed. Here's how:
```php
if ( function_exists( 'get_user_permission' ) === false ) {
    function get_user_permission( $permission_id ) {
        return true; # Always returns true when GSUsers is not installed
    }
}
```
This way allows you to use the function as you normally would and not have to do a function_exists() check each time. When GSUsers is not installed, the function will always return true (or false if required) to your plugin.

And that's all there is to it! See, that wasn't so hard, was it...
