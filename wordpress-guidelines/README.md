# Wordpress Development Guidelines

This document provides a set of rules for writing Wordpress themes & plugins.


## Editors
### PHPStorm configuration
- todo

### Sublime Text configuration
- todo


## Syntax and Formatting
### General
- An [.editorconfig](http://editorconfig.org/) file must be present in each theme and plugin.
- For displaying data, use short PHP echo tags:
```php
<?= get_field('front_title'); ?>
```
- There must be one space between PHP echo tags and code:
```php
<?php // RIGHT ?>
<?= get_field('front_title'); ?>

<?php // WRONG ?>
<?=get_field('front_title');?>
```

### Theme development for themes based on [Sage](https://github.com/roots/sage)
- Follow [PSR-2](http://www.php-fig.org/psr/psr-2/).
- Use [PHP Code Sniffer](https://github.com/squizlabs/PHP_CodeSniffer) to make sure you follow PSR-2 correctly.
- Follow the rules defined in Sage's [.editorconfig](https://github.com/roots/sage/blob/master/.editorconfig) file.
- This means templates must use **2 spaces** for indentation. This should be pretty much the only deviation from PSR-2.

### Plugin development
- Apply same rules as for theme development.
- Following the rules defined in Roots\Sage [.editorconfig](https://github.com/roots/sage/blob/master/.editorconfig) is optional. This means it's okay to use either 2 or 4 spaces in templates. Just don't forget the .editorconfig file.

### Wordpress-specific quirks
- Do not leave spaces between parenthesis and function arguments:

```php
<?php 
// RIGHT
add_filter('body_class', __NAMESPACE__ . '\\addUserRoleBodyClass');

// WRONG
add_filter( 'body_class', __NAMESPACE__ . '\\addUserRoleBodyClass' );
```

- In templates, each php control structure statement must be on a separate line.
```php
<?php if (get_field('front_title')): ?>
  <?= get_field('front_title'); ?>
<?php endif; ?>
```

- The only exception to this is the while statement in The Loop. It's okay to add the_post() call on the same line:
```php
<?php if (have_posts()): ?>
  <?php while (have_posts()): the_post(); ?>
```



## Development
The main goal is to keep your code *reusable* and *readable*.

### Organizing files
- Use classes.
- Use namespaces. Todo: description
- Follow [PSR-4](http://www.php-fig.org/psr/psr-4/) autoloading standard. Todo: autoloading example.
- When working on a Sage 8 or other legacy project, use your own judgement regarding whether adding PSR-4 is useful or not.

### General
- Keep functionality out of the templates. Views should be "dumb".
- Let functions inject data into templates. Views should be re-usable. todo: how to
- Apply [DRY principle](http://deviq.com/don-t-repeat-yourself/).
- Apply [SOLID principles](https://code.tutsplus.com/tutorials/solid-part-1-the-single-responsibility-principle--net-36074).
- Use [meaningful variable and function names](http://c2.com/cgi/wiki?GoodVariableNames).
- Use Yoda Conditions:
```php
<?php if (true === $the_force): ?>
```
- Use interpolation instead of concatenation. Always use curly braces when interpolating.
```php
<?php $status = "{$new_status}_{$post->post_type}";
```
- Functions should not output more than one simple line of HTML. For anything longer than that, use a template.

### Copy-pasting code from the Interwebz
- *Always* add the address where the code came from into a comment.
- Rewrite parts of the code that don't follow this guide. This includes fixing formatting and stupid variable names.
- There is an exception to this rule: complex algorithms. For example, if you copy-paste a function that does multi-level recursive array diff, you usually shouldn't bother with cleaning it up.

### Very Simple Themes
When dealing with sites that are really super simple in terms of functionality and have no more than just a couple of re-usable components, it's okay to break most of the best practices detailed in this section. Sometimes you can leave functionality inside the templates, actually put stuff inside lib/extras.php file and not separate (simple) functionality and views. But even then, put effort into keeping the code tidy and readable.

Also keep in mind that there is *always* a chance that a project that started off as a super simple one-pager magically transforms into a not-that-simple two-pager at some point during the process.


## Tools & plugins

### Working with Advanced Custom Fields
- todo

### Multilingual sites
- todo

### 


## Resources
- [PHP The Right Way](http://www.phptherightway.com/) describes some of the general best practices of PHP development.
- [Carl Alexander's blog](https://carlalexander.ca/) has some *really good* resources on Wordpress OOP.