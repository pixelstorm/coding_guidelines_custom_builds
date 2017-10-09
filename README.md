# Best Practices and Coding Standards for custom builds
 
1. No inline code in the wordpress text editor of custom fields, no code is to be exposed to the client in the backend. 

1. No “cowboy coding”. All code and design changes are carried out on a local testing server first before implementing on staging or live website.

1. Use inline svgs for icons and logos 

1. All code is to be modular and deployed to github for reuse. 

1. if its just a snippet of code for wp then upload it to the wp snippets repo. We also have a snippets repo for woocommerce and gravity form snippets.

1. Deploy to the client’s staging server  

1. If they do not have a staging server – use mysite.preparetolaunch.com.au 


### Css
1. Use bourbon and neat NOT BOOTSTRAP  
1. Use a BEM css metholodgy
1. Use 'container' class to set the content width 
1. Use 'wrapper' class  to surround an element that needs some padding, margins or background properties 
 
### Filestructure
 Use [sass globing](https://github.com/DennisBecker/grunt-sass-globbing) to pull in all the sass partials from the components directory. And we use [load-grunt-config](https://github.com/firstandthird/load-grunt-config) to seaprate the grunt file into individual files
```
 theme (custom theme) 
  | dev  
    - Gruntfile.js  
    - package.json  
    |- grunt  
	 - sass.js  
	 - sass-globbing.js  
	 - uglify.js  
	 - jshint.js  
	 - watch.js  
	 - aliases.yaml  
    |- node_modules (exclude from commits) 
    |- sass 
	 |- bourbon 
	 |- neat  
	 |- _custom.scss (main stylesheet)
	 |- _mixins.scss 
  |- components 
    |- custom_component (commit to github) 
	 |- php, scss and js files for the component 
    |- custom_component 
    |- custom_component 
```
 
### grunt modules we use
1. [uglify](https://github.com/gruntjs/grunt-contrib-uglify)
1. [sass](https://github.com/sindresorhus/grunt-sass) with [bourbon](http://bourbon.io/), [neat](http://neat.bourbon.io/)
1. [sass globing](https://github.com/DennisBecker/grunt-sass-globbing)
1. [load-grunt-config](https://github.com/firstandthird/load-grunt-config)
1. [watch](https://github.com/gruntjs/grunt-contrib-watch)
1. [jshint](https://github.com/gruntjs/grunt-contrib-jshint)

### wordpress setup
1. dont use admin as the username

## Plugins – List of Approved Plugins
Please seek approval when adding a plugin that is not part of this list. (*we will add and grow this list.)
 
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
1. Yoast
1. Woocommerce
 
# Custom Coding
1.   Prefix all functions with pxs_.
1.   Do provide comments for functions and templates.

### We adhere to wordpress best practices broadly defined here:

http://codex.wordpress.org/working_with_wordpress  http://codex.wordpress.org/developer_documentation  

1. all code should be compatible with the latest version of wordpress.

1. follow the wordpress coding standards.  http://codex.wordpress.org/wordpress_coding_standards

1. data must be validated and sanitized on input and escaped on output.

1. avoid direct calls to php scripts in your theme and do not try to load the wordpress environment on your own.
1. ensure code will be both backward-compatible and future-proof using the wordpress core apis.
1. encapsulate all code within a theme and plugins – do not scatter scripts or other assets in other locations.

1. use standard wordpress theme development practices. avoid overriding the native theming engine with a third party engine (e.g. mustache or smarty) or an unusual framework.

1. avoid modifying the server side page rendering based on visitor or other one off properties for unauthenticated visitors (this is imperative in environments with page caching enabled).

1. avoid interacting with cookies on the server side. client side interaction (javascript) is fine.

1. avoid direct interaction with database tables (sql queries). strongly avoid scripts that alter the database structure by, for example, adding or altering database fields, and creating new tables.

1. clean up after yourself: remove unused files and directories and any unused code fragments or debugging comments.

1. adhere to a consistent coding style.

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
