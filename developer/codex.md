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
