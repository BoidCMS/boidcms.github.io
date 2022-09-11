# Plugins API
See [what actions are](developer/actions).

## Events

### Set
```php
<?php

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

$App->get_action( 'event_unique_id' );

?>
```


## Filter

### Set

```php
<?php

$App->set_action( 'filter_unique_id', 'my_filter_callback_function' );

function my_filter_callback_function( $value ) {
  // Do stuff, like
  $modified = str_replace( 'Default', 'Filtered', $value );

  // Must always return value
  return $modified;
}
?>
```

### Apply

```php
<?php

$filtered = $App->filter( 'Value', 'filter_unique_id' );
// Or just
$filtered = $App->_( 'Value' ); // Default unique id is "default"

?>
```
















