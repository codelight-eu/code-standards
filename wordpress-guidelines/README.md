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

## Wordpress-specific quirks
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

- The exception to this is the while statement in The Loop
```php
<?php if (have_posts()): ?>
  <?php while (have_posts()): the_post(); ?>
```