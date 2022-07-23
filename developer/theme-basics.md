# Theme Basics
All themes reside in the `themes` folder, And they have a predefined structure.


## Folder and Files Structure
This is the folder and the most required files structure for themes.     

```plain
themes/
└── example/
    ├── home.php
    └── theme.php
```


## Theme code example

### home.php

```
<?php global $App ?>
<!DOCTYPE html>
<html lang="<?= $App->get( 'lang' ) ?>">
  <head>
    <title><?= $App->get( 'title' ) ?></title>
  </head>
  <body>
    <h1>Posts</h1>
    <?php foreach ( $App->data()[ 'pages' ] as $page ): ?>
      <?php if ( 'post' === $page[ 'type' ] ): ?>
        <section>
          <h2><?= $page[ 'title' ] ?></h2>
          <p><?= $page[ 'descr' ] ?></p>
        </section>
      <?php endif ?>
    <?php endforeach ?>
  </body>
</html>
```

### theme.php

```
<?php global $App ?>
<!DOCTYPE html>
<html lang="<?= $App->get( 'lang' ) ?>">
  <head>
    <title><?= $App->page( 'title' ) ?></title>
  </head>
  <body>
    <h1><?= $App->page( 'title' ) ?></h1>
    <div><?= $App->page( 'content' ) ?></div>
  </body>
</html>
```







