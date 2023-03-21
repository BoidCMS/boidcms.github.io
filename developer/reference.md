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
This constant, defined in the `index.php` file in the root directory, is used to restrict direct access to PHP files. To implement this restriction, use the following syntax or an alternative: 

```php
defined( 'App' ) or die( 'Direct access to this file is restricted.' );
```

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

- **`App::__construct()`**:
This is the constructor method.

```php
App::__construct( string $root ): void
```

**Parameters**:
 - `$root` (`string`) **required**: This is the installation directory passed as a parameter during the class initialization.

------

- **`App::_()`**:

```php
App::_( mixed $value, string $callback = 'default', mixed ...$args ): mixed
```

**Parameters**:
 - `$value` (`mixed`) **required**: This is the value that will be processed by the filter.
 - `$callback` (`string`) **optional**: This is the filter action. By default, it is set to `default`.
 - `$args` (`mixed`) **optional**: These are the arguments passed to the function. The default value is empty.
------

- **`App::_l()`**:

```php
App::_l( string $callback, array $custom = array() ): array
```

**Parameters**:
 - `$callback` (`string`) **required**: This is the list filter action.
 - `$custom` (`array`) **optional**: This is the default lists passed. The default value is `array()`.

------

- **`App::log()`**:

```php
App::log( string $message, string $type = 'debug' ): bool
```

**Parameters**:
 - `$message` (`string`) **required**: This is logging message.
 - `$type` (`string`) **optional**: This is the log type. The default value is `debug`.

------

- **`App::set()`**:

```php
App::set( mixed $value, string $index ): bool
```

**Parameters**:
 - `$value` (`mixed`) **required**: This is the value to be save.
 - `$index` (`string`) **required**: This is the key index of the value saved.

------

- **`App::unset()`**:

```php
App::unset( string $index ): bool
```

**Parameters**:
 - `$index` (`string`) **required**: This is index key of the value to be removed.

------

- **`App::get()`**:

```php
App::get( string $index ): mixed
```

**Parameters**:
 - `$index` (`string`) **required**: This is the index key of the value to be returned.

------

- **`App::url()`**:

```php
App::url( string $location = '' ): string
```

**Parameters**:
 - `$location` (`string`) **optional**: This is the path to be appended to the end of the site url. The default value is ``.

------

- **`App::admin_url()`**:

```php
App::admin_url( string $location = '', bool $abs = false ): string
```

**Parameters**:
 - `$location` (`string`) **optional**: This is the path to be appended to the end of the admin url. The default value is ``.
 - `$abs` (`bool`) **optional**: This is to return absolute admin url if passed as `true` or as relative url otherwise. The default value is `false`.

------

- **`App::root()`**:

```php
App::root( string $location ): string
```

**Parameters**:
 - `$location` (`string`) **required**: This is the path to be appended to the end of the root directory.

------

- **`App::theme()`**:

```php
App::theme( string $location, bool $system = true ): string
```

**Parameters**:
 - `$location` (`string`) **required**: This is the path to be appended to the end of the current theme directory.
 - `$system` (`bool`) **optional**: This is to return a system file path if `true` or full site url with the theme file appended to it. The default value is `true`.

------

- **`App::save()`**:

```php
App::save( ?array $data = null ): bool
```

**Parameters**:
 - `$data` (`array|null`) **optional**: This is the modified database to be saved. The default value is `null`.

------

- **`App::data()`**:

```php
App::data( ?string $index = null ): array
```

**Parameters**:
 - `$index` (`string|null`) **optional**: This is the index key of the database table to be returned. The default value is `null`.

--------

- **`App::token()`**:

```php
App::token(): string
```

**Parameters**:

-------

- **`App::set_action()`**:

```php
App::set_action( string | array $action, callable $callback, int $priority = 10 ): void
```

**Parameters**:
 - `$action` (`string|array`) **required**: This is the action(s) to be registered.
 - `$callback` (`callable`) **required**: This is the callback function of the action(s).
 - `$priority` (`int`) **optional**: This is the priority order of the action, the number lower the number the more prioritised the action(s) gets. The default value is `10`.

------

- **`App::unset_action()`**:

```php
App::unset_action( string $action ): void
```

**Parameters**:
 - `$action` (`string`) **required**: This is the action to be removed.

------

- **`App::get_action()`**:

```php
App::get_action( string $action, mixed ...$args ): string
```

**Parameters**:
 - `$action` (`string`) **required**: This is the action to be triggered.
 - `$args` (`mixed`) **optional**: These are the arguments to be passed to the action's callback. The default value is empty.

--------

- **`App::get_filter()`**:

```php
App::get_filter( mixed $value, string $action, mixed ...$args ): mixed
```

**Parameters**:
 - `$value` (`mixed`) **required**: This is the value to be filtered.
 - `$action` (`string`) **required**: This is the action to be used as the filter.
 - `$args` (`mixed`) **optional**: These are the arguments to be passed to the action's callback. The default value is empty.

--------

- **`App::load_actions()`**:

```php
App::load_actions(): void
```

**Parameters**:

---------

- **`App::alert()`**:

```php
App::alert( string $message, string $type = 'info' ): void
```

**Parameters**:
 - `$message` (`string`) **required**: This is the alert message.
 - `$type` (`string`) **optional**: This is the alert type, could be `error`, `warning`, `info` and `success`. The default value is `info`.

-------

- **`App::alerts()` (`void`)**:

```php
App::alerts(): void
```

**Parameters**:

-------

- **`App::page()`**:

```php
App::page( string $index, ?string $page = null ): mixed
```

**Parameters**:
 - `$index` (`string`) **required**: This is the index key of the page field to return.
 - `$page` (`string|null`) **optional**: This returns the data from the specified page, or current page if `null`. The default value is `null`.

--------

- **`App::create_page()`**:

```php
App::create_page( string $slug, array $details ): bool
```

**Parameters**:
 - `$slug` (`string`) **required**: This is the slugified slug of the page to be created.
 - `$details` (`array`) **required**: This is the data containing all the fields required, to be saved as the page data.

-------

- **`App::update_page()`**:

```php
App::update_page( string $slug, string $permalink, array $updates ): bool
```

**Parameters**:
 - `$slug` (`string`) **required**: This is the old slug of the page to be updated.
 - `$permalink` (`string`) **required**: This is the new slug for the page, the old one could be used if not changing it.
 - `$updates` (`array`) **required**: This is the updated page data.

-------

- **`App::delete_page()`**:

```php
App::delete_page( string $slug ): bool
```

**Parameters**:
 - `$slug` (`string`) **required**: This is the slug of the page to be deleted.

-------

- **`App::is_page()`**:

```php
App::is_page( string $page ): bool
```

**Parameters**:
 - `$page` (`string`) **required**: This is the slug of the page to be checked.

--------

- **`App::upload_media()`**:

```php
App::upload_media( ?string &$msg = null, ?string &$basename = null ): bool
```

**Parameters**:
 - `$msg` (`string|null`) **optional**: This is the reference variable that stores the uploading response. The default value is `null`.
 - `$basename` (`string|null`) **optional**: This is the reference variable that stores the uploaded file basename. The default value is `null`.

-------

- **`App::delete_media()`**:

```php
App::delete_media( string $media ): bool
```

**Parameters**:
 - `$media` (`string`) **required**: This is the basename of the media file to be deleted.

--------

- **`App::install()`**:

```php
App::install( string $plugin ): bool
```

**Parameters**:
 - `$plugin` (`string`) **required**: This is the directory name of the plugin to be installed.

--------

- **`App::uninstall()`**:

```php
App::uninstall( string $plugin ): bool
```

**Parameters**:
 - `$plugin` (`string`) **required**: This is the directory name of the plugin to be uninstalled.

--------

- **`App::installed()`**:

```php
App::installed( string $plugin ): bool
```

**Parameters**:
 - `$plugin` (`string`) **required**: This is the directory name of the plugin to check.

---------

- **`App::slugify()`**:

```php
App::slugify( string $title ): string
```

**Parameters**:
 - `$title` (`string`) **required**: This is the text parameter to be slugified.

-------

- **`App::go()`**:

```php
App::go( string $location = '' ): void
```

**Parameters**:
 - `$location` (`string`) **optional**: This is the internal path to redirect to. The default value is ``.

--------

- **`App::esc_slug()`**:

```php
App::esc_slug( string $slug, string $alt = '' ): string
```

**Parameters**:
 - `$slug` (`string`) **required**: This is slug to be escaped.
 - `$alt` (`string`) **optional**: This is an alternate slug to return when `$slug` parameter is considered empty. The default value is ``.

--------

- **`App::esc()`**:

```php
App::esc( string | array | null $text, bool $trim = true ): string
```

**Parameters**:
 - `$text` (`string|array|null`) **required**: This is the text to be escaped.
 - `$trim` (`bool`) **optional**: This indicates whether the escaped text should be trimmed. The default value is `true`.

--------

- **`App::auth()`**:

```php
App::auth( ?string $location = null, bool $post = true ): void
```

**Parameters**:
 - `$location` (`string|null`) **optional**: This is the internal path to redirect when authentication fails.
 - `$post` (`bool`) **optional**: This indicates whether the request should be treated as `post` if passed as `true` or `get` otherwise. The default value is `true`.

--------

- **`App::admin()`**:

```php
App::admin(): void
```

**Parameters**:

--------

- **`App::render()`**:

```php
App::render(): void
```

**Parameters**:

