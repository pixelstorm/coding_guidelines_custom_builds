# Best Practices and Coding Standards for custom builds
 
1. Develop using php 7 and above 
1. No inline code, no hardcoding content into theme files, no code is to be exposed to the client in the admin area. 
1. Use inline svgs for icons and logos 
1. Develop locally before implementing on staging or live site
1. Develop using reusable modular components
[usable component guide](https://github.com/pixelstorm/coding_guidelines_reusable_components)

### Css
1. we prefer to use bourbon and neat NOT BOOTSTRAP  
1. Use a BEM css metholodgy

### html
HTML5 elements and markup to be used according to best practices
 
### wordpress setup
1. choose a unique relervent username

## Plugins – List of Approved Plugins
Please discuss if when adding a plugin that is not part of this list.
 
And please, NEVER modify a plugin directly. Use functions.php in the theme or create a custom plugin.
 
1. Advanced Custom Fields Pro (we have a premium license)
1. Updraft
1. Wordfence 
1. Knowlege base by press apps (premium) 
1. Enhanced media library (premium) 
1. Wp all import (premium) 
1. Query monitor (premium) 
1. Gravity Forms   (we have a premium license)
1. Tablepress 
1. Timber 
1. Yoast
1. Woocommerce
 
# Custom Coding
1.  Prefix all functions with pxs_ and tables with a unique white_label prefix.
1. Provide comments for functions and templates.
1. follow html 5 best practices
1. Site must validate on [wave]( http://wave.webaim.org/ ) and [ csslint ](http://csslint.net/)


# Testing in browser stack (login supplied)
1. Ios iphone4 and up, Ipad all versions 
1. Android S4 and up, Galaxy 3 and up, Galaxy SS mini 
1. Internet Explorer 11 and up 
1. latest versions of Firefox, Chrome and Safari 

### We adhere to wordpress best practices broadly defined here:

http://codex.wordpress.org/working_with_wordpress  http://codex.wordpress.org/developer_documentation  

1. All code should be compatible with the latest version of wordpress.

1. Follow the wordpress coding standards.  http://codex.wordpress.org/wordpress_coding_standards

1. Data must be validated and sanitized on input and escaped on output.

1. Avoid direct calls to php scripts in your theme and do not try to load the wordpress environment on your own.

1. Ensure code will be both backward-compatible and future-proof using the wordpress core apis.

1. Encapsulate all code within a theme and plugins – do not scatter scripts or other assets in other locations.

1. Use standard wordpress theme development practices. avoid overriding the native theming engine with a third party engine (e.g. mustache or smarty) or an unusual framework.

1. Avoid modifying the server side page rendering based on visitor or other one off properties for unauthenticated visitors (this is imperative in environments with page caching enabled).

1. Avoid interacting with cookies on the server side. client side interaction (javascript) is fine.

1. Avoid direct interaction with database tables (sql queries). strongly avoid scripts that alter the database structure by, for example, adding or altering database fields, and creating new tables.

1. Clean up after yourself: remove unused files and directories and any unused code fragments or debugging comments.

1. Adhere to a consistent coding style.

*under no circumstances should you ever edit wordpress core files or plugin files directly. 
if you need to modify a plugin, hook from the theme’s functions.php file or create a custom plugin.

### Database

Avoid direct interaction with database tables (SQL queries). 
In reality, 9 out of 10 times, the same result can be accomplished by using an official WordPress function or API, which often include sophisticated caching while ensuring forwards compatibility.

Strongly avoid scripts that alter the database structure by, for example, adding or altering database fields, and creating new tables. In most cases, WordPress’s sophisticated custom post types, taxonomies, options, and meta data API’s can accomplish the same result with superior security and performance (especially in cache-enabled environments). Scripts that alter the database structure require dramatically more time to audit, review, and test.

In the event that database interaction is truly essential, WordPress provides a class of functions for all database manipulations. The class is called wpdb and is loosely based on the ezSQL class written and maintained by Justin Vincent.

Learn more about the $wpdb Object: http://codex.wordpress.org/Class_Reference/wpdb

### Validation and Sanitization

#### Input Validation
To validate is to ensure the data you’ve requested of the user matches what they’ve submitted. There are several core methods you can use for input validation; usage obviously depends on the type of fields you’d like to validate.
More
information:http://codex.wordpress.org/Validating_Sanitizing_and_Escaping_User_Data#Validating:_Checki ng_User_Input

#### Escape Output
For security on the other end of the spectrum, we have escaping. To escape is to take the data you may already have and help secure it prior to rendering it for the end user.
More information: http://codex.wordpress.org/Validating_Sanitizing_and_Escaping_User_Data#Escaping:_Securing_Output
