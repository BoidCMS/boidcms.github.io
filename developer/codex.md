# Codex

## BoidCMS Version

```php
$version = $App->version;
```

## Installation dir
The Current Working Directory of the site.

```php
echo $App->root;
```

## Current Page
The current page user is on.

```php
echo $App->page;
```

## IP Address
The server ip address, From `$_SERVER` super global.

```php
echo $App->ip;
```

## Make value modifiable
Similar to WordPress `_()` function, `App::_()` method is used to make value modifiable.

```php
$value = $App->_( 'Default value', 'valid_callback' );
echo $value; // Default value

// Modifying using actions
$App->set_action( 'valid_callback', function( $arg ) {
  return str_replace( 'Default', 'Modified', $arg );
});

echo $value; // Modified value
```

## Debug logging
Log a debug message.     

```php
$type = 'DEBUG';
$message = 'Debug logging using App::log method.';
$App->log( $message, $type );
```

## Set to database
Set a single value to database.     

```php
$index = 'codex';
$value = 'Setting to database';
$App->set( $value, $index );
```

## Unset from database
Remove a value from database.     

```php
$App->unset( 'codex' );
```

## Get from database
Get value from database.     

```php
echo $App->get( 'codex' );
```

## Set a global alert
Set an alert.     

```php
$class = 'success';
$message = 'Saved Successfully';
$App->set_alert( $message, $class );

```

## Get all global alert
Get available alerts.    

```php
$App->alerts();
```
<!--
### With custom template

```php
$App->get_alert('<p class="%s">%s</p>');
```
-->

## Set action (hook/action)
Define a new callable function for modification.     

```php
// Debug a warning for every login failure
$App->set_action( 'login_error', function( string $username, string $password ): void {
  $this->log( sprintf( 'Suspicious login detected, Incorrect details: %s, %s', $username, $password ) );
});
``` 

## Unset action (hook/action)
Reset the action to empty.     

```php
$App->unset_action('action');
```

## Get action (hook/action)
Get action if available.     

```php
$App->get_action('action');
```

<!--
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
-->

## Plugins list
All plugins.     

```php
$plugins = $App->plugins;
```

## Themes list
All themes.      

```php
$themes = $App->themes;
```

## Get page info
Get page values.      

```php
$title = $App->page( 'title' );
$keywords = $App->page( 'keywords' );
$content = $App->page( 'content' );
$thumb = $App->page( 'thumb' );
$date = $App->page( 'date' );
$pub = $App->page( 'pub' );
```
<!--
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
-->

## Check admin login status

```php
$logged_in = $App->logged_in;
```


