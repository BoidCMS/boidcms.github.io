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

- **`App::__construct()` (`void`)**:

- **`App::_()` (`mixex`)**:

- **`App::_l()` (`array`)**:

- **`App::log()` (`bool`)**:

- **`App::set()` (`bool`)**:

- **`App::unset()` (`bool`)**:

- **`App::get()` (`mixed`)**:

- **`App::url()` (`string`)**:

- **`App::admin_url()` (`string`)**:

- **`App::root()` (`string`)**:

- **`App::theme()` (`string`)**:

- **`App::save()` (`bool`)**:

- **`App::data()` (`array`)**:

- **`App::token()` (`string`)**:

- **`App::set_action()` (`void`)**:

- **`App::unset_action()` (`void`)**:

- **`App::get_action()` (`string`)**:

- **`App::get_filter()` (`mixed`)**:

- **`App::load_actions()` (`void`)**:

- **`App::alert()` (`void`)**:

- **`App::alerts()` (`void`)**:

- **`App::page()` (`mixed`)**:

- **`App::create_page()` (`bool`)**:

- **`App::update_page()` (`bool`)**:

- **`App::delete_page()` (`bool`)**:

- **`App::upload_media()` (`bool`)**:

- **`App::delete_media()` (`bool`)**:

- **`App::install()` (`bool`)**:

- **`App::uninstall()` (`bool`)**:

- **`App::installed()` (`bool`)**:

- **`App::slugify()` (`string`)**:

- **`App::go()` (`void`)**:

- **`App::esc_slug()` (`string`)**:

- **`App::esc()` (`string`)**:

- **`App::auth()` (`void`)**:

- **`App::admin()` (`void`)**:

- **`App::render()` (`void`)**:


