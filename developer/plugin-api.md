# Plugins API
[Visit here](/developer/actions) to view the available actions in BoidCMS, which provides a comprehensive list of available actions or hooks that plugins can listen to and act upon to extend the functionality of the website.

## Event
When a particular event is triggered, certain actions are executed in response. These pre-defined actions are what we refer to as `events`.

### Set
```php
<?php

/**
 * Registers a callback function to be executed when the "my_event" event is triggered.
 *
 * @param object $App An instance of the App class.
 * @param callable $callback The callback function to execute.
 * @param int $priority The priority of the callback function.
 */
function register_my_event_callback( App $App, callable $callback, int $priority = 10 ): void {
  $App->set_action( 'my_event', $callback, $priority );
}

/**
 * Callback function for the "my_event" event.
 */
function my_event_callback_function(): void {
  // Do stuff...
  // Not necessary to return value
  echo 'My text.';
}

// Example usage:
register_my_event_callback( $App, 'my_event_callback_function' );

?>
```

### Get

```php
<?php

/**
 * Trigger the "my_event" event.
 *
 * @param string $action The name of the action to trigger.
 * @param mixed  ...$args Optional arguments to pass to the callback.
 * @return mixed The result of the action.
 */
$App->get_action( 'my_event' );

?>
```


## Filter
Filters enable dynamic modification of a variable's value through the use of specific actions.

### Set

```php
<?php

/**
 * Set a filter for a unique ID.
 *
 * @param string|array $action The name of the action to which the filter is hooked.
 * @param callable $callback The callback function to execute when the filter is applied.
 * @param int $priority Optional. The priority of the filter function. Default is 10.
 * @return void
 */
$App->set_action( 'my_filter', 'my_filter_callback_function' );

/**
 * Callback function for the filter.
 *
 * @param string $value The value to be filtered.
 * @return string The filtered value.
 */
function my_filter_callback_function( string $value ): string {
  // Do stuff, like
  $modified = str_ireplace( 'default', 'filtered', $value );

  // Must always return value
  return $modified;
}
```

### Apply

```php
<?php

/**
 * Gets the filtered value for a given action.
 *
 * @param mixed $value The value to filter.
 * @param string $action The name of the action to apply.
 * @param mixed ...$args Additional arguments to pass to the action.
 * @return mixed The filtered value.
 */
$filtered = $App->get_filter( 'My default value', 'my_filter' );

// Alternatively, use the shorthand method.
$filtered = $App->_( 'My default value', 'my_filter' );

?>
```
















