# Plugins API


## Action

### Set
```php
<?php

$App->set_action( 'action', 'my_event_callback_function' );

function my_event_callback_function() {
  echo 'My text.';
}

?>
```

### Get

```php
<?php

$App->get_action( 'action' );

?>
```


## Filter


### Apply

```php
<?php

$filtered = $App->filter( 'Value', 'filter_unique_id' );
// Or just
$filtered = $App->_( 'Value' ); // Default unique id: default

?>
```

### Set

```php
<?php

$App->set_action( 'filter_unique_id', 'my_filter_callback_function' );

function my_filter_callback_function( $value ) {
  // Must always return value
  return str_replace( 'Default', 'Filtered', $value );
}
?>
```


















