#CSS Coding Guidelines

This document provides a basic set of rules for writing easily maintainable, readable and scalable CSS.
Codelight's naming conventions are based on BEM methodology.
Many of the ideas, concepts and conventions described in this document are derived from the following articles:
- http://cssguidelin.es/
- https://github.com/gilbox/css-bliss/blob/master/README.md
- http://csswizardry.com/2015/03/more-transparent-ui-code-with-namespaces/
- http://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/
- http://www.stubbornella.org/content/2010/06/25/the-media-object-saves-hundreds-of-lines-of-code/
- http://codeguide.co/
- https://css-tricks.com/bem-101/
- http://www.smashingmagazine.com/2014/07/bem-methodology-for-small-projects/
- https://github.com/rstacruz/rscss
- https://en.bem.info/method/definitions/#naming-for-independent-css-classes
- http://bensmithett.github.io/element-queries-preso/
- http://www.sitepoint.com/beyond-media-queries-time-get-elemental/
- http://codepen.io/wesruv/post/adventures-in-bem-responsive
- http://www.smashingmagazine.com/2012/04/a-new-front-end-methodology-bem/

It is highly recommended to read these articles before commencing.

##Syntax and Formatting

###Basics
- two (2) space indents, no tabs;
- 80 character wide columns;
- multi-line CSS;
- meaningful use of whitespace;

###Ruleset formatting
- related selectors on the same line; unrelated selectors on new lines;
- a space before our opening brace ({);
- properties and values on the same line;
- a space after our property–value delimiting colon (:);
- each declaration on its own new line;
- the opening brace ({) on the same line as our last selector;
- our first declaration on a new line after our opening brace ({);
- our closing brace (}) on its own new line;
- each declaration indented by two (2) spaces;
- a trailing semi-colon (;) on our last declaration.

For example:

    .foo, .foo--bar,
    .baz {
      display: block;
      background-color: green;
      color: red;
    }

CSS should be written on multiple lines. Exceptions to this rule are rulesets that only carry one declaration each, for example:

    .icon {
      display: inline-block;
      width:  16px;
      height: 16px;
      background-image: url(/img/sprite.svg);
    }

    .icon--home     { background-position:   0     0  ; }
    .icon--person   { background-position: -16px   0  ; }
    .icon--files    { background-position:   0   -16px; }
    .icon--settings { background-position: -16px -16px; }
    
#### Nesting
Avoid nesting CSS selectors whenever possible.

Avoid indenting whole rulesets.

#### Whitespace
- Add one (1) empty line between closely related rulesets.
- Add two (2) empty lines between loosely related rulesets.
- Add five (5) empty lines between entirely new sections.

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
to safely remove some of them if they are no longer needed.

### HTML
Follow these guidelines, except the selector grouping: http://cssguidelin.es/#html

### Commenting
Follow these guidelines: http://cssguidelin.es/#commenting

## Naming Conventions
TODO:
read these
- https://github.com/gilbox/css-bliss/blob/master/README.md
- http://csswizardry.com/2015/03/more-transparent-ui-code-with-namespaces/
- http://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/
- http://www.stubbornella.org/content/2010/06/25/the-media-object-saves-hundreds-of-lines-of-code/

Explain what BEM is and how and why it works.

Explain BEM naming concepts

Examples of BEM and examples of what not to do

Codelight's BEM syntax
