# Plugins API


## Action

### Set
```php
<?php

$App->set_action( 'action', 'my_callback_action' );

function my_callback_action() {
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

$filtered = $App->_( 'Value' );

?>
```

### Set

```php
<?php

$App->set_action( 'action', 'my_filter_action' );

function my_filter_action( $value ) {
  return str_replace( 'Default', 'Filtered', $value );
}
?>
```


















