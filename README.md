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

## If custom theme website project is a [ Gutenberg Build ](https://github.com/pixelstorm/Custom-theme-with-gutenberg)


## if website project is using a [ ACF page builder ](https://github.com/pixelstorm/Custom-theme-with-ACF-Page-Builder/)

# Frontend Dev Guidelines
Please read carefully and ask question for clarification. [Frontend Dev Guidelines](https://github.com/pixelstorm/Frontend-Development-Guidelines/)


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
         ├── _normalize.scss
         ├── _slick-carousel.scss
         ├── _slick-dots.scss
         ├── blocks
         │   ├── _accordion.scss
         │   ├── _articles.scss
         │   ├── _blocks.scss
         │   ├── _box-slider.scss
         │   ├── _buttons.scss
         │   ├── _columns.scss
         │   ├── _contact-form.scss
         │   ├── _cta-with-form.scss
         │   ├── _groups.scss
         │   ├── _headings.scss
         │   ├── _hero.scss
         │   ├── _intro.scss
         │   ├── _latest-posts.scss
         │   ├── _list.scss
         │   ├── _location-box.scss
         │   ├── _location-detail.scss
         │   ├── _paragraphs.scss
         │   ├── _people-with-filters.scss
         │   ├── _quicklinks.scss
         │   ├── _quote.scss
         │   ├── _search.scss
         │   ├── _services.scss
         │   ├── _team-slider.scss
         │   ├── _team.scss
         │   ├── _testimonials-slider.scss
         │   ├── _text-with-gallery.scss
         │   ├── _text-with-image.scss
         │   ├── _youtube.scss
         │   └── includes
         │       ├── _featured-post.scss
         │       ├── _location-filters.scss
         │       ├── _post-filters.scss
         │       └── _post-meta.scss
         ├── elements
         │   ├── _elements.scss
         │   ├── _lists.scss
         │   └── _tables.scss
         ├── forms
         │   ├── _buttons.scss
         │   ├── _fields.scss
         │   ├── _forms.scss
         │   ├── _messages.scss
         │   ├── _post-filters.scss
         │   └── _select.scss
         ├── layout
         │   ├── _content-sidebar.scss
         │   ├── _no-sidebar.scss
         │   └── _sidebar-content.scss
         ├── media
         │   ├── _captions.scss
         │   ├── _galleries.scss
         │   └── _media.scss
         ├── mixins
         │   └── _mixins-master.scss
         ├── modules
         │   ├── _accessibility.scss
         │   ├── _alignments.scss
         │   ├── _clearings.scss
         │   └── _infinite-scroll.scss
         ├── navigation
         │   ├── _breadcrumbs.scss
         │   ├── _city-selector.scss
         │   ├── _links.scss
         │   ├── _main.scss
         │   ├── _mixins.scss
         │   ├── _mobile.scss
         │   ├── _navigation.scss
         │   ├── _pagination.scss
         │   ├── _post.scss
         │   └── _utility.scss
         ├── site
         │   ├── _editor.scss
         │   ├── _site.scss
         │   ├── primary
         │   │   ├── _comments.scss
         │   │   ├── _footer.scss
         │   │   ├── _header.scss
         │   │   └── _posts-and-pages.scss
         │   └── secondary
         │       └── _widgets.scss
         ├── style.scss
         ├── typography
         │   ├── _copy.scss
         │   ├── _headings.scss
         │   └── _typography.scss
         └── variables-site
             ├── _colors.scss
             ├── _columns.scss
             ├── _structure.scss
             ├── _typography.scss
             └── _variables-site.scss
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
