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
 - `$root` (`string`) **required**: This is the installation directory passed during initiation.

------

- **`App::_()`**:
```php
App::_( mixed $value, string $callback = 'default', mixed ...$args ): mixed
```

- **`App::_l()`**:

```php
App::_l( string $callback, array $custom = array() ): array
```

- **`App::log()`**:

```php
App::log( string $message, string $type = 'debug' ): bool
```

- **`App::set()`**:

```php
App::( mixed $value, string $index ): bool
```

- **`App::unset()`**:

```php
App::( string $index ): bool
```

- **`App::get()`**:

```php
App::get( string $index ): mixed
```

- **`App::url()`**:

```php
App:url( string $location = '' ): string
```

- **`App::admin_url()`**:

```php
App::admin_url( string $location = '', bool $abs = false ): string
```

- **`App::root()`**:

```php
App::root( string $location ): string
```

- **`App::theme()`**:

```php
App::theme( string $location, bool $system = true ): string
```

- **`App::save()`**:

```php
App::save( ?array $data = null ): bool
```

- **`App::data()`**:

```php
App::data( ?string $index = null ): array
```

- **`App::token()`**:

```php
App::token(): string
```

- **`App::set_action()`**:

```php
App::set_action( string|array $action, callable $callback, int $priority = 10 ): void
```

- **`App::unset_action()`**:

```php
App::unset_action( string $action ): void
```

- **`App::get_action()`**:

```php
App::get_action( string $action, mixed ...$args ): string
```

- **`App::get_filter()`**:

```php
App::get_filter( mixed $value, string $action, mixed ...$args ): mixed
```

- **`App::load_actions()`**:

```php
App::load_actions(): void
```

- **`App::alert()`**:

```php
App::alert( string $message, string $type = 'info' ): void
```

- **`App::alerts()` (`void`)**:

```php
App::alerts(): void
```

- **`App::page()`**:

```php
App::page( string $index, ?string $page = null ): mixed
```

- **`App::create_page()`**:

```php
App::create_page( string $slug, array $details ): bool
```

- **`App::update_page()`**:

```php
App::update_page( string $slug, string $permalink, array $updates ): bool
```

- **`App::delete_page()`**:

```php
App::delete_page( string $slug ): bool
```

- **`App::is_page()`**:

```php
App::is_page( string $page ): bool
```

- **`App::upload_media()`**:

```php
App::upload_media( ?string &$msg = null, ?string &$basename = null ): bool
```

- **`App::delete_media()`**:

```php
App::delete_media( string $media ): bool
```

- **`App::install()`**:

```php
App::install( string $plugin ): bool
```

- **`App::uninstall()`**:

```php
App::uninstall( string $plugin ): bool
```

- **`App::installed()`**:

```php
App::installed( string $plugin ): bool
```

- **`App::slugify()`**:

```php
App::slugify( string $title ): string
```

- **`App::go()`**:

```php
App::go( string $location = '' ): void
```

- **`App::esc_slug()`**:

```php
App::esc_slug( string $slug, string $alt = '' ): string
```

- **`App::esc()`**:

```php
App::esc( string|array|null $text, bool $trim = true ): string
```

- **`App::auth()`**:

```php
App::auth( ?string $location = null, bool $post = true ): void
```

- **`App::admin()`**:

```php
App::admin(): void
```

- **`App::render()`**:

```php
App::render(): void
```

