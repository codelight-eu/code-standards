# Wordpress Development Guidelines

This document provides a set of rules for writing Wordpress themes & plugins.

## Syntax and Formatting
### General
- An [.editorconfig](http://editorconfig.org/) file MUST be present
- Use short PHP echo tags
```php
<?= get_field('front_title'); ?>
```
- Use spaces between PHP echo tags and code
```php
<?php // RIGHT ?>
<?= get_field('front_title'); ?>

<?php // WRONG ?>
<?=get_field('front_title');?>
```

### Theme development for themes based on [Sage](https://github.com/roots/sage)
- Follow [PSR-2](http://www.php-fig.org/psr/psr-2/)
- Use [PHP Code Sniffer](https://github.com/squizlabs/PHP_CodeSniffer)
- Follow the rules defined in Sage's [.editorconfig](https://github.com/roots/sage/blob/master/.editorconfig) file
- This means templates must use **2 spaces** for indentation. This is the only deviation from PSR-2.

### Plugin development
- Same as above
- Following the rules defined in Roots\Sage [.editorconfig](https://github.com/roots/sage/blob/master/.editorconfig) is optional. However, in this case you MUST have an .editorconfig file

### Wordpress-specific quirks
- Do not leave spaces between parenthesis and function arguments.

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

- The exception to this is the while statement in The Loop. It's okay to add the_post() call on the same line.
```php
<?php if (have_posts()): ?>
  <?php while (have_posts()): the_post(); ?>
```


## Development

### Organizing files
- Typically, you'll want to use OOP and classes to keep things readable and re-usable.
- Follow [PSR-4](http://www.php-fig.org/psr/psr-4/) autoloading standard
- todo: namespaces
- todo: autoloading example
- However, some very simple projects don't really need classes. In this case, divide your functions into separate files based on their purpose and domain. In most cases, multiple files that have juse one or two functions is better than a single big functions.php file.

- If code 
- When working on a Sage 8 or other legacy project, use your own judgement regarding whether adding PSR-4 is useful or not. However

### General
- Keep functionality out of the templates. Views should be stupid.
- Let functions inject data into templates. Views should be re-usable. todo: how to
- 

### Copy-pasting code from the Interwebz
- *Always* add the address where the code came from into a comment
- Rewrite parts of the code that don't follow this guide. This includes fixing formatting and stupid variable names.
- There is an exception to this rule: complex algorithms. For example, if you copy-paste a function that does multi-level recursive array diff, you usually shouldn't bother with cleaning it up.

### Very Simple Themes
When dealing with sites that are really super simple in terms of functionality and have no more than just a couple of re-usable components, it's okay to break most of the best practices detailed in this section. Sometimes you can leave functionality inside the templates, actually put stuff inside lib/extras.php file and not  separate (simple) functionality and views. But even then, put effort into keeping the code tidy and readable. Also keep in mind that there is *always* a chance that a project that started off as a super simple one-pager magically transforms into a not-that-simple two-pager at some point during the process.