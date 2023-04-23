# API Reference


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
The `App` constant, defined in the `index.php` file located in the root directory, serves as a security measure to prevent direct access to PHP files. To enforce this restriction, use the following syntax or an alternative method:

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
This method is the constructor.

```php
App::__construct( string $root ): void
```

**Parameters**:
 - `$root` (`string`) **required**: This is the installation directory passed as a parameter during the class initialization.

------

- **`App::_()`**:
This method serves as an alias for the `App::get_filter` method.

```php
App::_( mixed $value, string $callback = 'default', mixed ...$args ): mixed
```

**Parameters**:
 - `$value` (`mixed`) **required**: This is the value that will be processed by the filter.
 - `$callback` (`string`) **optional**: This is the filter action. By default, it is set to `default`.
 - `$args` (`mixed`) **optional**: These are the arguments passed to the function. The default value is empty.
------

- **`App::_l()`**:
This method is used to create an array, which can be either empty or pre-populated with values specified in the second parameter. The resulting array can then be filtered using the filter provided in the first parameter, allowing for customization of the array's contents.

```php
App::_l( string $callback, array $custom = array() ): array
```

**Parameters**:
 - `$callback` (`string`) **required**: This is the list filter action.
 - `$custom` (`array`) **optional**: This is the default lists passed. The default value is `array()`.

------

- **`App::log()`**:
This method is used to record a debug message to a log file, which can be accessed from the [`data`](/folder?id=data) directory.

```php
App::log( string $message, string $type = 'debug' ): bool
```

**Parameters**:
 - `$message` (`string`) **required**: This is the logging message.
 - `$type` (`string`) **optional**: This is the log type. The default value is `debug`.

------

- **`App::set()`**:
This method is used to store a pair of key and value to the [`site`](/database?id=database-default-structure) table in the database. The stored data can be accessed and retrieved later on as needed.

```php
App::set( mixed $value, string $index ): bool
```

**Parameters**:
 - `$value` (`mixed`) **required**: This is the value to be save.
 - `$index` (`string`) **required**: This is the key index of the value saved.

------

- **`App::unset()`**:
This method is used to remove/delete a value previously set using the `App::set` method by providing its index key as an argument.

```php
App::unset( string $index ): bool
```

**Parameters**:
 - `$index` (`string`) **required**: This is index key of the value to be removed.

------

- **`App::get()`**:
This method is used to retrieve a value from the `site` table in the database using the index key that was previously set using the `App::set` method.

```php
App::get( string $index ): mixed
```

**Parameters**:
 - `$index` (`string`) **required**: This is the index key of the value to be returned.

------

- **`App::url()`**:
This method returns the full site URL with the value of the `$location` parameter appended to it.

```php
App::url( string $location = '' ): string
```

**Parameters**:
 - `$location` (`string`) **optional**: This is the path to be appended to the end of the site url. The default value is ` `.

------

- **`App::admin_url()`**:
This method returns the URL for the admin panel, which can be customized by the admin for improved security. The URL includes the value of the `$location` parameter appended to it.  
If the `$abs` parameter is set to `true`, the return value will be an absolute URL, with the site URL prepended. Otherwise, it will be a relative URL.

```php
App::admin_url( string $location = '', bool $abs = false ): string
```

**Parameters**:
 - `$location` (`string`) **optional**: This is the path to be appended to the end of the admin url. The default value is ` `.
 - `$abs` (`bool`) **optional**: This is to return absolute admin url if passed as `true` or as relative url otherwise. The default value is `false`.

------

- **`App::root()`**:
This method is used to get a filename or directory name with the current working directory of the site prepended to it, making it a system filename.

```php
App::root( string $location ): string
```

**Parameters**:
 - `$location` (`string`) **required**: This is the path to be appended to the end of the current working directory.

------

- **`App::theme()`**:
This method is used to retrieve a file or directory name from the current theme directory. If the second parameter `$system` is set to `true`, the return value will be passed to the `App::root` method, which will return a system filename. If it is set to `false`, the return value will be passed to the `App::url` method, which will return an HTTP link URL.

```php
App::theme( string $location, bool $system = true ): string
```

**Parameters**:
 - `$location` (`string`) **required**: This is the path to be appended to the end of the current theme directory.
 - `$system` (`bool`) **optional**: This is to return a system file path if `true` or full site url with the theme file appended to it. The default value is `true`.

------

- **`App::save()`**:
This method is used to commit changes made to the database.

```php
App::save( ?array $data = null ): bool
```

**Parameters**:
 - `$data` (`array|null`) **optional**: This is the modified database to be saved. The default value is `null`.

------

- **`App::data()`**:
This method is used to retrieve the entire database or a specific table from it, if the `$index` parameter is not `null` and corresponds to a valid table in the database.

```php
App::data( ?string $index = null ): array
```

**Parameters**:
 - `$index` (`string|null`) **optional**: This is the index key of the database table to be returned. The default value is `null`.

--------

- **`App::token()`**:
This method is used to either generate a new CSRF token and store it in the session or retrieve an existing one from the session. The generated or retrieved token is then returned for use in CSRF protection.

```php
App::token(): string
```

**Parameters**:

-------

- **`App::set_action()`**:
This method is used to register an [action](/developer/actions?id=actions), which can either be an event or filter.

```php
App::set_action( string | array $action, callable $callback, int $priority = 10 ): void
```

**Parameters**:
 - `$action` (`string|array`) **required**: This is the action(s) to be registered.
 - `$callback` (`callable`) **required**: This is the callback function of the action(s).
 - `$priority` (`int`) **optional**: This is the priority order of the action, the lower the number the more prioritised the action(s) gets. The default value is `10`.

------

- **`App::unset_action()`**:
This method is used to unregister an action that was previously registered using the `App::set_action` method.

```php
App::unset_action( string $action ): void
```

**Parameters**:
 - `$action` (`string`) **required**: This is the action to be removed.

------

- **`App::get_action()`**:
This method is used to invoke or trigger an action previously registered as an [event](/developer/plugin-api?id=event).

```php
App::get_action( string $action, mixed ...$args ): string
```

**Parameters**:
 - `$action` (`string`) **required**: This is the action to be triggered.
 - `$args` (`mixed`) **optional**: These are the arguments to be passed to the action's callback. The default value is empty.

--------

- **`App::get_filter()`**:
This method is used to apply a [filter](/developer/plugin-api?id=filter) to a given value and return the filtered result.

```php
App::get_filter( mixed $value, string $action, mixed ...$args ): mixed
```

**Parameters**:
 - `$value` (`mixed`) **required**: This is the value to be filtered.
 - `$action` (`string`) **required**: This is the action to be used as the filter.
 - `$args` (`mixed`) **optional**: These are the arguments to be passed to the action's callback. The default value is empty.

--------

- **`App::load_actions()`**:
This method is used to load all plugins and the `functions.php` file from the current theme, if it exists.

```php
App::load_actions(): void
```

**Parameters**:

---------

- **`App::alert()`**:
This method is used to send an alert notification to the administrator.

```php
App::alert( string $message, string $type = 'info' ): void
```

**Parameters**:
 - `$message` (`string`) **required**: This is the alert message.
 - `$type` (`string`) **optional**: This is the alert type, could be `error`, `warning`, `info` and `success`. The default value is `info`.

-------

- **`App::alerts()`**:
This method is used to display all the alert notifications that were sent to the admin.

```php
App::alerts(): void
```

**Parameters**:

-------

- **`App::page()`**:
This method is used to retrieve the value of a specific field from a page.

```php
App::page( string $index, ?string $page = null ): mixed
```

**Parameters**:
 - `$index` (`string`) **required**: This is the index key of the page field to return.
 - `$page` (`string|null`) **optional**: This returns the data from the specified page, or current page if `null`. The default value is `null`.

--------

- **`App::create_page()`**:
This method is used to create a new page with specified properties and contents.

```php
App::create_page( string $slug, array $details ): bool
```

**Parameters**:
 - `$slug` (`string`) **required**: This is the slugified slug of the page to be created.
 - `$details` (`array`) **required**: This is the data containing all the fields required, to be saved as the page data.

-------

- **`App::update_page()`**:
This method is used to update specific fields of an existing page.

```php
App::update_page( string $slug, string $permalink, array $updates ): bool
```

**Parameters**:
 - `$slug` (`string`) **required**: This is the old slug of the page to be updated.
 - `$permalink` (`string`) **required**: This is the new slug for the page, the old one could be used if not changing it.
 - `$updates` (`array`) **required**: This is the updated page data.

-------

- **`App::delete_page()`**:
This method is used to delete an existing page.

```php
App::delete_page( string $slug ): bool
```

**Parameters**:
 - `$slug` (`string`) **required**: This is the slug of the page to be deleted.

-------

- **`App::is_page()`**:
This method checks whether a page exists or not.  
!> Note that this method is available starting from version `v2.0.0`.

```php
App::is_page( string $page ): bool
```

**Parameters**:
 - `$page` (`string`) **required**: This is the slug of the page to check.

--------

- **`App::upload_media()`**:
This method is used to accept file submissions.  
?> Note that only a single file can be uploaded at a time.

```php
App::upload_media( ?string &$msg = null, ?string &$basename = null ): bool
```

**Parameters**:
 - `$msg` (`string|null`) **optional**: This is the reference variable that stores the uploading response. The default value is `null`.
 - `$basename` (`string|null`) **optional**: This is the reference variable that stores the uploaded file basename. The default value is `null`.

-------

- **`App::delete_media()`**:
This method is used to delete a previously uploaded file.

```php
App::delete_media( string $media ): bool
```

**Parameters**:
 - `$media` (`string`) **required**: This is the basename of the file to be deleted.

--------

- **`App::install()`**:
This method is used to install a plugin.

```php
App::install( string $plugin ): bool
```

**Parameters**:
 - `$plugin` (`string`) **required**: This is the directory name of the plugin to be installed.

--------

- **`App::uninstall()`**:
This method is used to uninstall a plugin.

```php
App::uninstall( string $plugin ): bool
```

**Parameters**:
 - `$plugin` (`string`) **required**: This is the directory name of the plugin to be uninstalled.

--------

- **`App::installed()`**:
This method is used to check whether a plugin is installed or not.

```php
App::installed( string $plugin ): bool
```

**Parameters**:
 - `$plugin` (`string`) **required**: This is the directory name of the plugin to check.

---------

- **`App::slugify()`**:
This method is used to convert a text to a URL-friendly slug.

```php
App::slugify( string $title ): string
```

**Parameters**:
 - `$title` (`string`) **required**: This is the text parameter to be slugified.

-------

- **`App::go()`**:
This method is used to perform an internal site redirect.

```php
App::go( string $location = '' ): void
```

**Parameters**:
 - `$location` (`string`) **optional**: This is the internal path to redirect to. The default value is ` `.

--------

- **`App::esc_slug()`**:
This method is used to filter and remove unwanted characters from a text, to convert it into a slug. Unlike the `App::slugify` method, which also slugifies the text, this method only performs filtering and removal of unwanted characters.

```php
App::esc_slug( string $slug, string $alt = '' ): string
```

**Parameters**:
 - `$slug` (`string`) **required**: This is slug to be escaped.
 - `$alt` (`string`) **optional**: This is an alternate slug to return when `$slug` parameter is considered empty. The default value is ` `.

--------

- **`App::esc()`**:
This method is used to encode HTML entities from a text to make it safe to display on a web page and prevent Cross-Site Scripting (XSS) attacks.

```php
App::esc( string | array | null $text, bool $trim = true ): string
```

**Parameters**:
 - `$text` (`string|array|null`) **required**: This is the text to be escaped.
 - `$trim` (`bool`) **optional**: This indicates whether the escaped text should be trimmed. The default value is `true`.

--------

- **`App::auth()`**:
This method is used to validate the authenticity of a CSRF token and authenticate an admin action.

```php
App::auth( ?string $location = null, bool $post = true ): void
```

**Parameters**:
 - `$location` (`string|null`) **optional**: This is the internal path to redirect when authentication fails.
 - `$post` (`bool`) **optional**: This indicates whether the request should be treated as `POST` if passed as `true` or `GET` otherwise. The default value is `true`.

--------

- **`App::admin()`**:
This method is used to render the admin panel.

```php
App::admin(): void
```

**Parameters**:

--------

- **`App::render()`**:
This method is used to generate and send the output to the browser for rendering.

```php
App::render(): void
```

**Parameters**:

