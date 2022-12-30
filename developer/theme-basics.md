# Theme Basics
All themes reside in the `themes` folder, And they have a predefined structure.


## Folder and Files Structure
This is the folder and the most required files structure for themes.     

```plain
themes/
└── example/
    ├── blog.php
    └── theme.php
```

Some files which aren't necessarily required includes `post.php` (Custom template for page with `post` type) and `blank.php` (Blank template for plugins that creates dynamic pages).

## Theme code example

### blog.php **(required)**
Use this template to create a listing of published posts.

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
      <?php if ( 'post' === $page[ 'type' ] ): ?>
        <?php if ( $page[ 'pub' ] ): ?>
        <section>
          <h2><a href="<?= $slug ?>"><?= $page[ 'title' ] ?></a></h2>
          <p><?= $page[ 'descr' ] ?></p>
        </section>
        <?php endif ?>
      <?php endif ?>
    <?php endforeach ?>
    <footer><?= $App->get( 'footer' ) ?></footer>
  </body>
</html>
```

### theme.php **(required)**
Use this template to create a normal **static page** design.

```php
<?php global $App ?>
<!DOCTYPE html>
<html lang="<?= $App->get( 'lang' ) ?>">
  <head>
    <title><?= $App->page( 'title' ) ?></title>
  </head>
  <body>
    <h1><?= $App->page( 'title' ) ?></h1>
    <div><?= $App->page( 'content' ) ?></div>
    <footer><?= $App->get( 'footer' ) ?></footer>
  </body>
</html>
```

### post.php **(not required)**
Use this template to create a **post page** design.

```php
<?php global $App ?>
<!DOCTYPE html>
<html lang="<?= $App->get( 'lang' ) ?>">
  <head>
    <title><?= $App->page( 'title' ) ?></title>
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
Use this template to create a layout of a normal **static page**.

```php
<?php global $App ?>
<!DOCTYPE html>
<html lang="<?= $App->get( 'lang' ) ?>">
  <head>
    <title><?= $layout[ 'title' ] ?></title>
  </head>
  <body>
    <h1><?= $layout[ 'title' ] ?></h1>
    <div><?= $layout[ 'content' ] ?></div>
    <footer><?= $App->get( 'footer' ) ?></footer>
  </body>
</html>
```

?> You can add more features to it, [Theme Tags](/themes/tags) and [Actions](/developer/actions?id=themes) are most needed.





