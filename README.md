# Best Practices and Coding Standards
 
1. No “cowboy coding”. All code and design changes are carried out on a testing server first before implementing on a live website.
1. develop locally 
1. All code is to be modular and deployed to github for reuse. 
1. if its just a snippet of code for wp then upload it to the wp snippets repo. We also have a snippets repo for woocommerce and gravity form snippets.
 
 
1. Deploy to  the client’s staging server  
2. If they do not have a staging server – use mysite.preparetolaunch.com.au 
 
## Themes – List of Approved Themes
All website themes should be child themes of the parent theme (if not using _s)
Fortuna
Dont use Genesis
 
## Plugins – List of Approved Plugins
Please seek approval when adding a plugin that is not part of this list. (*we will add and grow this list.)
 
And please, NEVER modify a plugin directly. Use functions.php in the theme or create a custom plugin.
 
1. Advanced Custom Fields Pro (we have a premium license)
1. updraft
1. Wordfence 
1. Gravity Forms   (we have a premium license)
1. Tablepress 
1. Yoast
1. woocommerce
 
 
# For Custom Coding
1.   Prefix all functions with pxs_.

We adhere to WordPress best practices broadly defined here:

http://codex.wordpress.org/Working_with_WordPress  http://codex.wordpress.org/Developer_Documentation  
1.   All code should be compatible with the latest version of WordPress.
1.   Follow the WordPress Coding Standards.  http://codex.wordpress.org/WordPress_Coding_Standards
1.   Data must be validated and sanitized on input and escaped on output.
1.   Avoid direct calls to PHP scripts in your theme and do not try to load the WordPress environment on your own.
1.   Ensure code will be both backward-compatible and future-proof using the WordPress Core APIs.
1.   Encapsulate all code within a theme and plugins – do not scatter scripts or other assets in other locations.
1.   Use standard WordPress theme development practices. Avoid overriding the native theming engine with a third party engine (e.g. Mustache or Smarty) or an unusual framework.
1.   Avoid modifying the server side page rendering based on visitor or other one off properties for unauthenticated visitors (this is imperative in environments with page caching enabled).
1.   Avoid interacting with cookies on the server side. Client side interaction (JavaScript) is fine.
1.   Avoid direct interaction with database tables (SQL queries). Strongly avoid scripts that alter the database structure by, for example, adding or altering database fields, and creating new tables.
1.   Clean up after yourself: remove unused files and directories and any unused code fragments or debugging comments.
1.   Adhere to a consistent coding style.

*Under NO circumstances should you ever edit WordPress core files OR plugin files directly. 
If you need to modify a plugin, hook from the theme’s functions.php file or create a custom plugin.
Database

Avoid direct interaction with database tables (SQL queries). 
In reality, 9 out of 10 times, the same result can be accomplished by using an official WordPress function or API, which often include sophisticated caching while ensuring forwards compatibility.

Strongly avoid scripts that alter the database structure by, for example, adding or altering database fields, and creating new tables. In most cases, WordPress’s sophisticated custom post types, taxonomies, options, and meta data API’s can accomplish the same result with superior security and performance (especially in cache-enabled environments). Scripts that alter the database structure require dramatically more time to audit, review, and test.

In the event that database interaction is truly essential, WordPress provides a class of functions for all database manipulations. The class is called wpdb and is loosely based on the ezSQL class written and maintained by Justin Vincent.

Learn more about the $wpdb Object: http://codex.wordpress.org/Class_Reference/wpdb

Validation and Sanitization
### Input Validation
To validate is to ensure the data you’ve requested of the user matches what they’ve submitted. There are several core methods you can use for input validation; usage obviously depends on the type of fields you’d like to validate.
More
information:http://codex.wordpress.org/Validating_Sanitizing_and_Escaping_User_Data#Validating:_Checki ng_User_Input
### Escape Output
For security on the other end of the spectrum, we have escaping. To escape is to take the data you may already have and help secure it prior to rendering it for the end user.
More information: http://codex.wordpress.org/Validating_Sanitizing_and_Escaping_User_Data#Escaping:_Securing_Output
