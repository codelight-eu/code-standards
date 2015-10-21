#CSS Coding Guidelines

This document provides a basic set of rules for writing easily maintainable, readable and scalable CSS.
Codelight's naming conventions are based on BEM methodology.
Many of the ideas, concepts and conventions described in this document are derived from the following articles:
- http://cssguidelin.es/
- https://github.com/gilbox/css-bliss/blob/master/README.md
- https://gist.github.com/fat/a47b882eb5f84293c4ed#file-gistfile1-md
- http://csswizardry.com/2015/03/more-transparent-ui-code-with-namespaces/
- http://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/
- http://www.stubbornella.org/content/2010/06/25/the-media-object-saves-hundreds-of-lines-of-code/

It is highly recommended to read these articles before commencing.

##Syntax and Formatting

###Basics
- two (2) space indents, no tabs;
- 80 character wide columns;
- multi-line CSS;
- meaningful use of whitespace;

###Ruleset formatting

###Separate files
Each BEM block should be in a separate file and the file name should match the block's class name. All the other
styles should reside in separate files as well and those files should be named accordingly. If done correctly, the main SASS or LESS file, where all the other componets are included, will serve as a table of contents. For example:
    
    @import "common/_variables";                         // Custom variables

    // Automatically injected Bower dependencies via wiredep (never manually edit this block)
    // bower:scss
    @import "../../bower_components/bootstrap-sass/assets/stylesheets/_bootstrap.scss";
    // endbower

    @import "common/_global";                             // Site wide styles
    @import "components/_buttons";                        // Buttons
    @import "components/_comments";                       // WP comments
    @import "components/_forms";                          // Basic forms
    @import "components/_grid";                           // Grid overrides and custom grids 
    @import "components/_wp-classes";                     // WP specific styles
    @import "components/_square";                         // .square styles
    @import "components/_logos";                          // Brand logos
    @import "components/_singlePost";                     // .singlePost styles
    @import "components/_contentCircle";                  // .conentCircle styles
    @import "components/_basicPage";                      // .basicPage styles
    @import "components/_menus";                          // Main and footer menu styles
    @import "components/_prompt";                         // Prompt modal styles
    
It makes specific stylesheets easy to find and modify. Since all the BEM blocks are in separate files, it's also easy
to safely remove some them if for some reason they are no longer needed.

##Nesting
Avoid nesting CSS selectors whenever possible
