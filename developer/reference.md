# Code Reference


## Global Variables
To access a global variable in your code, you need to first declare it as a global variable using the syntax `global $variable;`. 

- **`$App` (`object`)**:
This is the global instance of the `App` class.

### Admin Global Variables

- **`$page` (`string`)**:
This is the slug of the page being visited (current page) in the admin area.

- **`$action` (`string`)**:
This is a reserved variable that can be used as a sub-action slug.

- **`$layout` (`array`)**:
This variable contains the layout data for the admin panel.

## Constants

- **`App` (`bool`)**:
This constant, defined in the `index.php` file in the root directory, is used to restrict direct access to PHP files. To implement this restriction, use the following syntax or an alternative: `defined( 'App' ) or die( 'Direct access to this file is restricted.' );`  

## Properties

- **`App::root` (`string`)**:
This property holds the root directory of the BoidCMS installation.  

- **`App::page` (`string`)**:
This property stores the slug of the currently visited page.  

- **`App::medias` (`string`)**:
This property stores the filenames of all uploaded media files.  

- **`App::themes` (`array`)**:
This property stores the names of the installed themes.  

- **`App::plugins` (`array`)**:
This property stores the names of plugins located in the plugins directory.  

- **`App::version` (`string`)**:
This property contains the version number of the BoidCMS installation.  

- **`App::logged_in` (`bool`)**:
This property returns the current admin login status, indicating whether the admin is logged in or not.  

- **`App::actions` (`array`)**:
This is a **protected** property that stores the registered actions, which include both events and filters, along with their corresponding callbacks and priority values.  

- **`App::database` (`array`)**:
This is a **protected** property that stores the complete database data.  

## Methods

- **`App::__construct( string $root )` (`void`)**:
This method is the constructor.  

- **`App::_( mixed $value, string $callback = 'default', mixed ...$args )` (`mixed`)**:


- **`App::_l( string $callback, array $custom = array() )` (`array`)**:

- **`App::log( string $message, string $type = 'debug' )` (`bool`)**:

- **`App::set( mixed $value, string $index )` (`bool`)**:

- **`App::unset( string $index )` (`bool`)**:

- **`App::get( string $index )` (`mixed`)**:

- **`App::url( string $location = '' )` (`string`)**:

- **`App::admin_url( string $location = '', bool $abs = false )` (`string`)**:

- **`App::root( string $location )` (`string`)**:

- **`App::theme( string $location, bool $system = true )` (`string`)**:

- **`App::save( ?array $data = null )` (`bool`)**:

- **`App::data( ?string $index = null )` (`array`)**:

- **`App::token()` (`string`)**:

- **`App::set_action( string|array $action, callable $callback, int $priority = 10 )` (`void`)**:

- **`App::unset_action( string $action )` (`void`)**:

- **`App::get_action( string $action, mixed ...$args )` (`string`)**:

- **`App::get_filter( mixed $value, string $action, mixed ...$args )` (`mixed`)**:

- **`App::load_actions()` (`void`)**:

- **`App::alert( string $message, string $type = 'info' )` (`void`)**:

- **`App::alerts()` (`void`)**:

- **`App::page( string $index, ?string $page = null )` (`mixed`)**:

- **`App::create_page( string $slug, array $details )` (`bool`)**:

- **`App::update_page( string $slug, string $permalink, array $updates )` (`bool`)**:

- **`App::delete_page( string $slug )` (`bool`)**:

- **`App::is_page( string $page )` (`bool`)**:

- **`App::upload_media( ?string &$msg = null, ?string &$basename = null )` (`bool`)**:

- **`App::delete_media( string $media )` (`bool`)**:

- **`App::install( string $plugin )` (`bool`)**:

- **`App::uninstall( string $plugin )` (`bool`)**:

- **`App::installed( string $plugin )` (`bool`)**:

- **`App::slugify( string $title )` (`string`)**:

- **`App::go( string $location = '' )` (`void`)**:

- **`App::esc_slug( string $slug, string $alt = '' )` (`string`)**:

- **`App::esc( string|array|null $text, bool $trim = true )` (`string`)**:

- **`App::auth( ?string $location = null, bool $post = true )` (`void`)**:

- **`App::admin()` (`void`)**:

- **`App::render()` (`void`)**:


