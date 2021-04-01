# Best Practices and Coding Standards for custom builds

Read this document before starting any new builds. This document will change and evolve overtime. This document requires your contribution. 
 
1. Develop using php 7.4
1. Use our [ git flow proceedure ](https://github.com/pixelstorm/git-flow)
1. Use [ Underscores ](https://underscores.me/) as the starter theme or if using timber https://github.com/timber/starter-theme. or if using webpack https://github.com/carrieforde/_s-with-webpack
1. Use https://developer.wordpress.org/reference/functions/get_template_part/ and pass in the $ARGS to Remain DRY.
1. Use svgs for icons and logos where posible.
3. Develop locally (i recommend "flywheel local" https://localwp.com/ ) deploy to a NOFOLLOW staging url.
4. Use Query Monitor as you develop, it will let you know of any errors; 
5. All text to be wrapped in either p, li or h1 to h3 tag. dont use divs to wrap text. use div for layout.
6. Develop the UI KIT first using existing and new gutenberg blocks and components.
  - buttons
  - titles
  - info cards
  - lists
  - slideshows
  - contact forms
  - header and footer
8. We build all website page components as self contained gutenberg blocks: ie testimonials block, contact form block, hero banner block, post slidershow block 
9. Use Gutenberg styled blocks and if needed Advanced Custom fields to build custom content areas and fields 
10. Only use gutenberg spacer block to add space between "variable content"
11. Use a styled gutenberg "group" object as a container for custom blocks.
12. Use https://codepen.io/MadeByMike/pen/vNrvdZ fluid typography - use it on more the just typography
13. Save your blocks as resusable blocks when they are complete. (We train the clients to use the reusable blocks)
14. Create an acf-json folder on your theme directory and keep changes to the acf field json under version control
https://www.advancedcustomfields.com/resources/local-json/
https://www.awesomeacf.com/how-to-avoid-conflicts-when-using-the-acf-local-json-feature/
1. Hide the custom fields option on the production site https://www.awesomeacf.com/snippets/hide-the-acf-admin-menu-item-on-selected-sites/
1. Create [ custom image sizes ](https://developer.wordpress.org/reference/functions/add_image_size/) for all components that use images.
1. use a srcset to output responsive images on the frontend for all responsive break points. see design seciton. https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images Please keep this inmind when choosing slideshow plugins https://www.metaslider.com/image-slide-demo/. the slideshows are to also utilise srcset

### Css
1. Use REMS for units and set the responsive scale on the html element.
3. Use CSS Grid and Flexbox for layout
4. Use a BEM CSS metholodgy - we use BEM to keep our html markup simple.
5. Dont use id's for css selectors. Only use ids for js
6. When deploying to production, compress your css files into one minified file
7. Avoid using inline css.
8. Create and use mixins to remain DRY.
9. Keep code organised by using Sass Maps for brand elements like typography and color. Use camelCasing for your sass map declarations.
10. Each Gutenberg block css lives in its own self contained file. the scss file is named the same as the block name. This includes existing gutenberg blocks ie: paragraph, heading etc 
11. Dont use !important if its not 100% nessary. When using BEM your css is modulized and therefore no need to use !important


### js
1. When deploying to production, Compress your js files into one minified file
 
### WordPress Setup
1. Choose a unique relavent username(not admin) for the main login username
2. Use stong password, store in lastpass and nowhere else.
3. Ensure your local and staging site is set to no-follow

## Responsiveness
This is the most critcal part of the developement. The problem can be that the design is often delivered to you at 1440px, but its viewed at 1920.
The design needs to look the same reguardless of what size its viewed at.

We have used https://codepen.io/MadeByMike/pen/vNrvdZ for responsive paddings and type.

1. Our points breaks, with mobile first standard:
   - 480px
   - 768px
   - 1024px
   - 1280px
   - 1440px
   - 1600px
   - 1920px



## Recommended file structures 
### using https://carrieforde.com/webpack-wordpress/ install
```
theme /
├── 404.php
├── LICENSE
├── README.md
├── acf-json
├── archive.php
├── comments.php
├── footer.php
├── functions.php
├── header.php
├── inc
    ├── acf.php
    ├── custom-gutenberg-editor-colors.php
    ├── custom-header.php
    ├── customizer.php
    ├── filter-posts.php
    ├── filter-team.php
    ├── gravity-forms.php
    ├── shortcode.php
    ├── template-functions.php
    ├── template-tags.php
    └── wpcom.php
├── index.php
├── languages
├── layouts
├── node_modules
├── package-lock.json
├── package.json
├── page.php
├── phpcs.xml.dist
├── public
├── readme.txt
├── report.20210225.150147.10790.001.json
├── rtl.css
├── screenshot.png
├── search.php
├── sidebar.php
├── single-team.php
├── single.php
├── src
    ├── images
    ├── index.js
    ├── js
    ├── libs
    └── sass
├── style-editor.css
├── style.css
├── template-parts
    ├── block
    ├── content-accordion.php
        ├── content-articles.php
        ├── content-box-slider.php
        ├── content-contact-form.php
        ├── content-cta-with-form.php
        ├── content-featured-post.php
        ├── content-hero.php
        ├── content-intro.php
        ├── content-latest-post-filters.php
        ├── content-latest-posts.php
        ├── content-location-box.php
        ├── content-location-detail.php
        ├── content-people-with-filter.php
        ├── content-quicklinks.php
        ├── content-services.php
        ├── content-team-details.php
        ├── content-team-slider-industry.php
        ├── content-team-slider.php
        ├── content-teamcard.php
        ├── content-testimonial.php
        ├── content-text-with-gallery.php
        └── content-text-with-image.php
        ├── content-location-filters.php
    ├── content-news.php
    ├── content-none.php
    ├── content-page-header.php
    ├── content-page.php
    ├── content-post.php
    ├── content-postcard.php
    ├── content-postmeta.php
    ├── content-posts-mobile.php
    ├── content-search.php
    ├── content-slick-buttons.php
    ├── content-teamarea-termlist.php
    ├── content.php
    └── includes
├── webpack.config.js
└── woocommerce.css
```
### Alternative file stucture using grunt
```
├── 404.php
├── LICENSE
├── README.md
├── acf-json
├── archive-project.php
├── archive.php
├── comments.php
├── composer.json
├── composer.lock
├── css
   ├── fancybox
   └── select2
├── dev
    ├── Gruntfile.js
    ├── js
    ├── node_modules
    ├── package-lock.json
    ├── package.json
    └── sass
├── fonts
├── footer.php
├── front-page.php
├── functions.php
├── header.php
├── home.php
├── images
├── inc
    ├── acf.php
    ├── custom-header.php
    ├── customizer.php
    ├── jetpack.php
    ├── template-functions.php
    ├── template-tags.php
    └── woocommerce.php
├── index.php
├── js
├── languages
├── package.json
├── page.php
├── phpcs.xml.dist
├── readme.txt
├── screenshot.png
├── search.php
├── sidebar.php
├── single-product.php
├── single-project.php
├── single.php
├── style-rtl.css
├── style.css
├── template-parts
├── vendor
└── woocommerce
```
## Plugins – List of Approved Plugins for production site
Please discuss when adding a plugin that is not part of this list.
 
And please, NEVER modify a plugin directly. Use functions.php in the theme or create a custom plugin.
 
1. Advanced Custom Fields Pro (we have a premium license)
1. Gravity Forms (we have a premium license)
1. Yoast
1. Woocommerce
1. db-migrate
1. query-monitor for local sites only
 
# Custom Coding
1. Prefix all functions with pxs_ and tables with a unique white_label prefix.
2. Provide comments for functions and templates.
- describe what the function does and why you are using it
- tell us what files use this function
- for templates tell us what the template does and why you are using it
3. Declare varibles at the top of the file where possible

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
