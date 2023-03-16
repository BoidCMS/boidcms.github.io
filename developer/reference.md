# Code Reference


## Constants

#### [`App`](developer/constant/app)

## Global Variables
To access a global variable in your code, you need to first declare it as a global variable using the syntax `global $variable`. 

- **`$App` (`object`)**:
This is the global instance of the `App` class.

### Admin Global Variables

- **`$page` (`string`)**:
This is the slug of the page being visited (current page) in the admin area.

- **`$action` (`string`)**:
This is a reserved variable that can be used as a sub-action slug.

- **`$layout` (`array`)**:
This variable contains the layout data for the admin panel.

## Properties

#### [`App::root`](developer/property/root)
#### [`App::page`](developer/property/page)
#### [`App::medias`](developer/property/medias)
#### [`App::themes`](developer/property/themes)
#### [`App::plugins`](developer/property/plugins)
#### [`App::version`](developer/property/version)
#### [`App::logged_in`](developer/property/logged_in)
#### [`App::actions`](developer/property/actions)
#### [`App::database`](developer/property/database)

## Methods

#### [`App::__construct()`](developer/method/__construct)
#### [`App::_()`](developer/method/_)
#### [`App::_l()`](developer/method/_l)
#### [`App::log()`](developer/method/log)
#### [`App::set()`](developer/method/set)
#### [`App::unset()`](developer/method/unset)
#### [`App::get()`](developer/method/get)
#### [`App::url()`](developer/method/url)
#### [`App::admin_url()`](developer/method/admin_url)
#### [`App::root()`](developer/method/root)
#### [`App::theme()`](developer/method/theme)
#### [`App::save()`](developer/method/save)
#### [`App::data()`](developer/method/data)
#### [`App::token()`](developer/method/token)
#### [`App::set_action()`](developer/method/set_action)
#### [`App::unset_action()`](developer/method/unset_action)
#### [`App::get_action()`](developer/method/get_action)
#### [`App::get_filter()`](developer/method/get_filter)
#### [`App::load_actions()`](developer/method/load_actions)
#### [`App::alert()`](developer/method/alert)
#### [`App::alerts()`](developer/method/alerts)
#### [`App::page()`](developer/method/page)
#### [`App::create_page()`](developer/method/create_page)
#### [`App::update_page()`](developer/method/update_page)
#### [`App::delete_page()`](developer/method/delete_page)
#### [`App::upload_media()`](developer/method/upload_media)
#### [`App::delete_media()`](developer/method/delete_media)
#### [`App::install()`](developer/method/install)
#### [`App::uninstall()`](developer/method/uninstall)
#### [`App::installed()`](developer/method/installed)
#### [`App::slugify()`](developer/method/slugify)
#### [`App::go()`](developer/method/go)
#### [`App::esc_slug()`](developer/method/esc_slug)
#### [`App::esc()`](developer/method/esc)
#### [`App::auth()`](developer/method/auth)
#### [`App::admin()`](developer/method/admin)
#### [`App::render()`](developer/method/render)

