# Best Practices and Coding Standards for custom builds

Read this document before starting any new builds. This document will change and evolve overtime. This document requires your contribution. 

## General Wordpress Development
1. Please read carefully and ask question for clarification. [ wp dev guidelines ](https://github.com/pixelstorm/WordPress-Development-Guidelines/)

## GIT
1. Use our [ git flow proceedure ](https://github.com/pixelstorm/git-flow)

## If Working in a team
1. When you are starting a block, Add a screenshot of the block you are working on to the slack channel. @the developers on your team to let them know.
2. When you have completed a block, add the screenshot of the block to the slack channel @the developers on your team to let them know the block is done.
3. When you have completed a block, add a "this is done" comment on the block in Figma. Add any development notes in the comments.

# Gutenberg Blocks Page Builder Guidelines:
If custom theme website project is a [ Gutenberg Build ](https://github.com/pixelstorm/Custom-theme-with-gutenberg)

# ACF Page Builder Guidelines (flexible blocks):
If website project is using a [ ACF page builder ](https://github.com/pixelstorm/Custom-theme-with-ACF-Page-Builder/)

# Frontend Dev Guidelines:
Please read carefully and ask question for clarification. [Frontend Dev Guidelines](https://github.com/pixelstorm/Frontend-Development-Guidelines/)


#git 
1. Install git in the custom theme directory
1. Checkout a local feature branch when working on a new feature and merge into master when you are done.
1. Deploy your master branch through beanstalk

### We adhere to wordpress best practices broadly defined here:

http://codex.wordpress.org/working_with_wordpress  http://codex.wordpress.org/developer_documentation  

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
