# Plugins API
See [what actions are](developer/actions) in BoidCMS.

## Event
Events are actions that are executed when a specified event occurs.

### Set
```php
<?php

/**
 * public function set_action( string | array $action, callable $callback, int $priority = 10 ): void;
 */
$App->set_action( 'event_unique_id', 'my_event_callback_function' );

function my_event_callback_function() {
  // Do stuff...
  // Not necessary to return value
  echo 'My text.';
}

?>
```

### Get

```php
<?php

/**
 * public function get_action( string $action, mixed ...$args ): mixed;
 */
$App->get_action( 'event_unique_id' );

?>
```


## Filter
Filters are actions that can be used to modify the value of a variable dynamically.

### Set

```php
<?php

/**
 * public function set_action( string | array $action, callable $callback, int $priority = 10 ): void;
 */
$App->set_action( 'filter_unique_id', 'my_filter_callback_function' );

function my_filter_callback_function( $value ) {
  // Do stuff, like
  $modified = str_replace( 'default', 'filtered', $value );

  // Must always return value
  return $modified;
}
?>
```

### Apply

```php
<?php

/**
 * public function get_filter( mixed $value, string $action, mixed ... $args ): void;
 */
$filtered = $App->get_filter( 'My default value', 'filter_unique_id' );

// Or just

/**
 * public function _( mixed $value, string $action = 'default', mixed ...$args ): void;
 */
$filtered = $App->_( 'My default value' );

?>
```
















