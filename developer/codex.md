# Codex

## BoidCMS Info

```php
$name = $App->name;
$version = $App->version;
```

## Installation dir

```php
echo $App->root;
```

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

## Get all global alert

### With default template
```php
$App->get_alert();
```

### With custom template

```php
$App->get_alert('<p class="%s">%s</p>');
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

## Unset action (hook/event)

```php
$App->unset_action('action');
```

## Get action (hook/event)

```php

$App->get_action('action');

```


## Save data

```php
$dir = __DIR__;
$title = 'codex';
$value = 'Save value to the given dir data file';
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
$status = $App->page('published', false, $page);
$id = $App->page('id', false, $page);
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
Action: `{% action:info %}`     

```php
$text = 'Site title: {% site:title %}';
$parsed = $App->parse($text);
```

## Validate user input
Validate user inputs and make text unparsable by `App::parse` method.
```php
$xss = $_GET['xss']; 
echo $xss; // <script>alert(document.cookie)</script>
echo $App->parse($xss); // 

$parsable = $_GET['input']; // {% site:password %}
echo $App->parse($parsable); // $2y$10$...
echo $App->unparse($parsable); // site:password

```

## Check admin login status

```php
$status = $App->logged_in();
```


