# Codex

## Current Page

```php
echo $App->page;
```

## IP Address

```php
echo $App->ip;
```

## Debug logging

```php

$type = 'DEBUG';
$message = 'Debug logging using App::log method.';
$App->log($message, $type);

```

## Set to database

```php

$key = 'codex';
$value = 'Setting to database';
$App->set($value, $key);

```

## Unset from database

```php

$App->unset('codex');

```

## Get from database

```php

echo $App->get('codex');

```

## Set a global alert

```php
$class = 'success';
$message = 'Saved Successfully';
$App->set_alert($message, $class);

```

## Set action (hook/event)

```php

$event = 'on_login_error';
$callback = function($name, $pass) {
  global $App;
  $App->log('Trying to login using incorrect details! Username: ' . $name . ', Password: ' . $pass, 'debug');
};
$App->set_action($callback, $event);

```

## Get action (hook/event)

```php

$App->get_action('action');

```

## Save data

```php
$dir = __DIR__;
$title = 'codex';
$value = 'Save data to the given dir data file';
$App->save($value, $title, $dir);
```

## Get data

```php
$App->data('codex', __DIR__);
```

## Post data

```php
$dir = __DIR__;
$data = array(
  'string': 'Data',
  'array': ['One', 'Two'],
  'bool': false,
  'int': 25
);
$App->post($data, $dir);
```

## Posts list

```php
$posts = $App->posts();
```

## Pages list

```php
$pages = $App->pages();
```

## Static pages

```php
$statics = $App->statics();
```

## Plugins list

```php
$plugins = $App->plugins();
```

## Themes list

```php
$themes = $App->themes();
```

## Get page info

```php
$page = $App->page;
$title = $App->page('title', false, $page);
$content = $App->page('content', true, $page);
```

## Parse text    
Regex: 
```regex
/\{\%\s([a-zA-Z0-9_-]+)\:([a-zA-Z0-9_>-]+)\s\%\}/
```

This: `{% this:info %}`     
Site: `{% site:info %}`     
Page: `{% page:info %}`     
Lang: `{% lang:in->fo %}`     

```php
$text = 'The website title is: {% site:title %}';
$parsed = $App->parse($text);
```




