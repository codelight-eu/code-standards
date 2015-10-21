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
styles should reside in separate files as well and those files should be named accordingly. For example:
    
    @import "common/_variables";

    // Automatically injected Bower dependencies via wiredep (never manually edit this block)
    // bower:scss
    @import "../../bower_components/bootstrap-sass/assets/stylesheets/_bootstrap.scss";
    // endbower

    @import "common/_global";
    @import "components/_buttons";
    @import "components/_comments";
    @import "components/_forms";
    @import "components/_grid";
    @import "components/_wp-classes";
    @import "components/_square";
    @import "components/_logos";
    @import "components/_singlePost";
    @import "components/_contentCircle";
    @import "components/_basicPage";
    @import "components/_menus";
    @import "components/_prompt";
    

##Nesting
Avoid nesting CSS selectors whenever possible
