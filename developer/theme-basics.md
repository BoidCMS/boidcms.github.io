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

Some files which aren't necessarily required includes `post.php` (Custom template for page with `post` type) and `blank.php` (Blank template).

## Theme code example

### blog.php

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

### theme.php

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

?> You can add more features to it, [Theme Tags](/themes/tags) and [Actions](/developer/actions?id=themes) are most needed.





