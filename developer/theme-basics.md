# Theme Basics
The `themes` folder contains all of the themes, which adhere to a predefined structure.

## Folder and Files Structure
The following folder and file structure is essential for themes.

```plain
themes/
└── example/
    ├── blog.php
    └── theme.php
```

While not strictly necessary, some useful files to include in your theme are `post.php` (a custom template for pages with `post` types) and `blank.php` (a blank template for plugins that create dynamic pages).

?> To use custom template files as custom page templates in the admin panel, you must first register them using the [`tpl`](/developer/actions) action. This action allows the admin panel to recognize and make use of your custom templates. Remember to register each custom template file you add before expecting it to be available for use.

## Theme code example

### blog.php **(required)**
To create a **list of published posts**, use the following template as a starting point.

!> Please note that this file only works starting from `v2.0.0`, use `home.php` for `v1.*` or create both for compatibility.

```php
<?php global $App ?>
<!DOCTYPE html>
<html lang="<?= $App->get( 'lang' ) ?>">
  <head>
    <title><?= $App->get( 'title' ) ?></title>
  </head>
  <body>
    <h1>Published Posts</h1>
    <?php foreach ( $App->data()[ 'pages' ] as $slug => $page ): ?>
      <?php if ( 'post' === $page[ 'type' ] && $page[ 'pub' ] ): ?>
        <section>
          <h2><a href="<?= $slug ?>"><?= $page[ 'title' ] ?></a></h2>
          <p><?= $page[ 'descr' ] ?></p>
        </section>
      <?php endif ?>
    <?php endforeach ?>
    <footer><?= $App->get( 'footer' ) ?></footer>
  </body>
</html>
```

### theme.php **(required)**
To create a **static page** design, use this template as a starting point.

```php
<?php global $App ?>
<!DOCTYPE html>
<html lang="<?= $App->get( 'lang' ) ?>">
  <head>
    <title><?= $App->page( 'title' ) ?> - <?= $App->get( 'title' ) ?></title>
  </head>
  <body>
    <h1><?= $App->page( 'title' ) ?></h1>
    <div><?= $App->page( 'content' ) ?></div>
    <footer><?= $App->get( 'footer' ) ?></footer>
  </body>
</html>
```

### post.php **(not required)**
To create a design for a **post page**, use this template as a starting point.

```php
<?php global $App ?>
<!DOCTYPE html>
<html lang="<?= $App->get( 'lang' ) ?>">
  <head>
    <title><?= $App->page( 'title' ) ?> - <?= $App->get( 'title' ) ?></title>
  </head>
  <body>
    <h1><?= $App->page( 'title' ) ?></h1>
    <p>Written by <b>John Doe</b> in category <b>Post</b></p>
    <div><?= $App->page( 'content' ) ?></div>
    <footer><?= $App->get( 'footer' ) ?></footer>
  </body>
</html>
```

### blank.php **(not required)**
To create a layout for a normal **static page**, use this template as a starting point.

```php
<?php global $App, $layout ?>
<!DOCTYPE html>
<html lang="<?= $App->get( 'lang' ) ?>">
  <head>
    <title><?= $layout[ 'title' ] ?> - <?= $App->get( 'title' ) ?></title>
  </head>
  <body>
    <h1><?= $layout[ 'title' ] ?></h1>
    <div><?= $layout[ 'content' ] ?></div>
    <footer><?= $App->get( 'footer' ) ?></footer>
  </body>
</html>
```

?> To enhance your theme's functionality, consider adding additional features such as [theme tags](/themes/tags) and [actions](/developer/actions?id=themes). These are particularly useful and highly recommended.

Take a look at [Nimble](https://github.com/BoidCMS/nimble), to see how easier it is to build a theme.


