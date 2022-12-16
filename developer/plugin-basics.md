# Plugin Basics
Plugins in BoidCMS are organized in the [`plugins`](/folders?id=plugins) folder and have a predefined structure.

## Folder and Files Structure

```plain
plugins/
└── example/
    └── plugin.php
```


## Plugin code
The Example plugin code below must be in the `plugin.php` file.     

```php
<?php defined( 'App' ) or die( 'BoidCMS' );
/**
 *
 * Plugin example
 *
 * @package BoidCMS
 * @subpackage Plugin_Example
 * @author Author Name
 * @version 1.0.0
 */

global $App;
$App->set_action( 'install', 'example_install' );
$App->set_action( 'uninstall', 'example_uninstall' );

/**
 * Log a debug message while installing
 * @param string $plugin
 * @return string
 */
function example_install( string $plugin ): void {
  global $App;
  if ( 'example' === $plugin ) {
    $msg = 'Example plugin installed.';
    $App->log( $msg );
  }
}

/**
 * Log a debug message before uninstalling
 * @param string $plugin
 * @return string
 */
function example_uninstall( string $plugin ): void {
  global $App;
  if ( 'example' === $plugin ) {
    $msg = 'Example plugin uninstalled.';
    $App->log( $msg );
  }
}
?>
```

Besides `install` and `uninstall`, there are many events (actions) to listen to. They can be found [here](/developer/actions).
