# Plugin Basics
Plugins in BoidCMS reside in the `plugins` folder, and they have a predefined structure.


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
 * @license GPLV3
 * @version 1.0
*/

global $App;
$App->set_action( 'install', 'example_init' );
$App->set_action( 'uninstall', 'example_shut' );

/**
 * Log a debug message after installing
 * @param string $plugin
 * @return string
 */
function example_init( string $plugin ): void {
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
function example_shut( string $plugin ): void {
  global $App;
  if ( 'example' === $plugin ) {
    $msg = 'Example plugin uninstalled.';
    $App->log( $msg );
  }
}
?>
```
