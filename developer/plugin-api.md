# Plugins API

[Visit here](/developer/actions) to view the available actions in BoidCMS, which provides a comprehensive list of available actions or hooks that plugins can listen to and act upon to extend the functionality of the website.

## Event
When a particular event is triggered, certain actions are executed in response. These pre-defined actions are what we refer to as `events`.

### Hook
```php
<?php

/**
 * Registers a callback function to be executed when the "my_event" event is triggered.
 *
 * @param string|array $action The unique name(s) of the event.
 * @param callable $callback The callback function to execute.
 * @param int $priority Optional. The priority of the event function. Default is 10.
 * @return void
 */
$App->set_action( 'my_event', 'my_event_callback_function' );

/**
 * Callback function for the "my_event" event.
 *
 * @return void
 */
function my_event_callback_function(): void {
  // Do stuff...
  // Not necessary to return value
  echo 'My text.';
}

?>
```

### Trigger

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

### Prevent
Event prevention is not natively supported in BoidCMS. However, you can prevent a specific event by following the code snippet provided below:

```php
<?php

/**
 * Callback function for the "my_event" event.
 *
 * @return void
 */
function my_event_callback_function(): void {
  global $App;
  
  // Check if prevention criteria are met
  if ( ! $App->get( 'do_let_it_execute' ) ) {
    
    // Check if the event is triggered by the admin from the panel
    if ( $App->admin_url() === $App->page ) {
      
      // Redirect to the dashboard
      $App->go( $App->admin_url() );
      
    }
    
    // Otherwise, the event is triggered by a plugin or automation
    // In this case, exit with a response instead of redirecting
    $resp = array();
    $resp[ 'code' ] = 200;
    $resp[ 'status' ] = false;
    $resp[ 'message' ] = 'Event prevented';
    $resp[ 'data' ] = array( 'event' => 'my_event' );
    $json = json_encode( $resp );
    exit( $json );
  }
  
  // Handle the event as usual
  echo 'Performing my action for the event.';
}

?>
```
<!-- This code snippet demonstrates how to prevent the execution of an event by checking specific criteria. If the criteria are not met, the code either redirects to the admin dashboard if triggered by an admin or exits with a response if triggered by a plugin or automation. Otherwise, the event is handled as usual. -->  
?> Please note that you need to customize the code to fit your specific event and prevention conditions.

### Remove

```php
<?php

/**
 * Remove an action along with all of its associated hooked callbacks.
 *
 * @param string $action The name of the event to remove
 * @return void
 */
$App->unset_action( 'my_event' );

?>
```

?> Please note that by doing this, you will be removing all previously set callbacks.


## Filter
Filters enable dynamic modification of a value through the use of specific actions.

### Hook

```php
<?php

/**
 * Set a filter for a unique name.
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
 * @param mixed ...$args Optional arguments to pass to the callback.
 * @return mixed The filtered value.
 */
$filtered = $App->get_filter( 'My default value', 'my_filter' );

// Alternatively, use the shorthand method.
$filtered = $App->_( 'My default value', 'my_filter' );

?>
```

### Remove

```php
<?php

/**
 * Remove an action along with all of its associated hooked callbacks.
 *
 * @param string $action The name of the filter to remove
 * @return void
 */
$App->unset_action( 'my_filter' );

?>
```

?> Please note that by doing this, you will be removing all previously set callbacks.















