# Codex

## Debug logging

```php
<?php
$type = 'DEBUG';
$message = 'Debug logging using App::log method.';
$App->log($message, $type);
?>
```

## Set to database

```php
<?php
$key = 'codex';
$value = 'Setting to database';
$App->set($value, $key);
?>
```

## Unset from database

```php
<?php
$App->unset('codex');
?>
```

## Get from database

```php
<?php
echo $App->get('codex');
?>
```

## Set action (hook/event)

```php
<?php
$event = 'on_login_error';
$callback = function($name, $pass) {
  global $App;
  $App->log('Trying to login using incorrect details! Username: ' . $name . ', Password: ' . $pass, 'debug');
};
$App->set_action($callback, $event);
?>
```

## Get action (hook/event)

```php
<?php
$App->get_action('action');
?>
```




