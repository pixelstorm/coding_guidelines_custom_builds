# Best Practices and Coding Standards for custom builds
 
1. Develop using php 7.4
1. Use our [ git flow proceedure ](https://github.com/pixelstorm/git-flow)
1. Use [ Underscores ](https://underscores.me/) as the starter theme or if using timber https://github.com/timber/starter-theme. or if using webpack https://github.com/carrieforde/_s-with-webpack
1. Do what you have to do to Remain DRY - unless you feel its adding too much complication for too little gain.
1. Use svgs for icons and logos where posible.
3. Develop locally deploy to a NOFOLLOW staging url.
4. Develop with define('wp_debug', true); 
5. All text to be wrapped in either p, li or h1 to h3 tag. dont use divs to wrap text. use div for layout.
6. Build a hardcoded, fully responsive html templates with html / scss / twig / php first before implementing advanced custom fields and dynamic data functionality.
7. Use Advanced Custom fields, Gutenberg & Hookturn plugins to build custom content areas and fields 
8. Create an acf-json folder on your theme directory and keep changes to the acf field json under version control
https://www.advancedcustomfields.com/resources/local-json/
https://www.awesomeacf.com/how-to-avoid-conflicts-when-using-the-acf-local-json-feature/
1. Hide the custom fields option on the production site https://www.awesomeacf.com/snippets/hide-the-acf-admin-menu-item-on-selected-sites/
1. Create [ custom image sizes ](https://developer.wordpress.org/reference/functions/add_image_size/) for all components that use images.
1. use a srcset to output responsive images on the frontend for all responsive break points. see design seciton. https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images Please keep this inmind when choosing slideshow plugins https://www.metaslider.com/image-slide-demo/. the slideshows are to also utilise srcset

### Css
1. Use REMS for units and set the responsive scale on the html element.
2. Use css grid and flexbox
3. Use a BEM css metholodgy
4. Dont use id's for css selectors. Only use ids for js
5. When deploying to production, compress your css files into one minified file


### js
1. When deploying to production, Compress your js files into one minified file
 
### WordPress Setup
1. Choose a unique relavent username(not admin)
1. Ensure your local and staging site is set to no-follow

## Plugins – List of Approved Plugins for production site
Please discuss if when adding a plugin that is not part of this list.
 
And please, NEVER modify a plugin directly. Use functions.php in the theme or create a custom plugin.
 
1. Advanced Custom Fields Pro (we have a premium license)
1. Gravity Forms (we have a premium license)
1. Yoast
1. Woocommerce
1. db-migrate
1. query-monitor for local sites only
1. any plugins relating to specific functionaliy of the site that does not cause unwanted loadtime.


1. Prefix all functions with pxs_ and tables with a unique white_label prefix.
 
# Custom Coding
1. Prefix all functions with pxs_ and tables with a unique white_label prefix.
1. Provide comments for functions and templates.

### Design
1. Usually we design at the 1440px screen width.
1. Our points breaks, with mobile first standard:
   - 480px
   - 768px
   - 1024px
   - 1280px
   - 1440px
   - 1600px
   - 1920px
1. We need to export our design to Zeplin, so please use : Sketch / Adobe XD / Figma / Photoshop to design.


# Filestructure 
```
 theme (custom theme) 
  | dev  
    - package.json  
    |- node_modules (exclude from commits) 
    |- sass 
	 |- bourbon 
	 |- neat  
	 |- _custom.scss (main stylesheet)
	 |- _mixins.scss 
```

Keep all the compressed production ready css and js outside of the dev folder.

#git 
1. Install git in the custom theme directory
1. Checkout a local feature branch when working on a new feature and merge into master when you are done.
1. Deploy your master branch through beanstalk


# Testing in browser stack (login supplied)

1. Ios iphone6 and up, Ipad all versions 
1. Android S4 and up, Galaxy 3 and up, Galaxy SS mini 
1. Internet Explorer 11 and up 
1. latest versions of Firefox, Chrome and Safari 

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
