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

?> You can add more features to it, [Actions](https://boidcms.github.io/#/developer/actions?id=themes) are most needed.





