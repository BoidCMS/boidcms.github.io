# Plugin Basics
Plugins in BoidCMS are essential to extend the functionality of the website and are organized in the [`plugins`](/folder?id=plugins) folder with a predefined structure.

Each plugin in BoidCMS follows a standardized structure, which includes a plugin main file. The plugin main file contains metadata about the plugin, such as the plugin name, version, and author. 


## Folder and Files Structure

```plain
plugins/
└── example/
    └── plugin.php
```


## Plugin code example
To properly add functionality to a plugin in BoidCMS, it's important to organize the code in a specific manner within the plugin's PHP file. The following code should be added to the `plugin.php` file of the example plugin:

```php
<?php defined( 'App' ) or die( 'BoidCMS' );
/**
 *
 * Plugin example that do nothing but log
 *
 * @package Plugin_Example
 * @author Author Name
 * @version 1.0.0
 */

// Ensure the plugin is installed properly
if ( 'example' !== basename( __DIR__ ) ) return;

global $App;
$App->set_action( 'install', 'example_install' );
$App->set_action( 'uninstall', 'example_uninstall' );

/**
 * Log a debug message while installing
 * @param string $plugin
 * @return void
 */
function example_install( string $plugin ): void {
  global $App;
  if ( 'example' === $plugin ) {
    $msg = '"Example" plugin installed.';
    $App->log( $msg );
  }
}

/**
 * Log a debug message before uninstalling
 * @param string $plugin
 * @return void
 */
function example_uninstall( string $plugin ): void {
  global $App;
  if ( 'example' === $plugin ) {
    $msg = '"Example" plugin uninstalled.';
    $App->log( $msg );
  }
}
?>
```

<!--
/**
 * Translate text (RegExp based)
 * @param array $l10n
 * @param string $lang
 * @param string $slug
 * @return array
 */
function example_translate( array $l10n, string $lang, string $slug ): array {
  // Return if the domain (slug) isn't "example"
  if ( 'example' !== $slug ) return [];
  
  $translation = array();
  
  // French
  $translation[ 'fr' ] = array();
  $translation[ 'fr' ][ '/"Example" plugin installed\./' ] = 'Plugin "Example" installé.';
  $translation[ 'fr' ][ '/"Example" plugin uninstalled\./' ] = 'Plugin "Example" désinstallé.';
  
  // Spanish
  $translation[ 'es' ] = array();
  $translation[ 'es' ][ '/"Example" plugin installed\./' ] = 'Complemento "Example" instalado.';
  $translation[ 'es' ][ '/"Example" plugin uninstalled\./' ] = 'Complemento "Example" desinstalado.';
  
  return ( $translation[ $lang ] ?? [] );
}
-->

In addition to the `install`, and `uninstall` <!--and `l10n_global`-->events, BoidCMS provides many other events or actions that can be listened to and acted upon by plugins. These actions provide opportunities for plugins to modify the behavior of the website or to respond to specific user interactions.

A comprehensive list of available [actions can be found in here](/developer/actions), which includes details on when each action is triggered and the parameters that are available for each action.
