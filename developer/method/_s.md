# `App::_s()` Method
A way of serializing and passing data.       
If there is no data passed, an empty array is returned.

Source: [app/app.php](https://github.com/BoidCMS/BoidCMS/blob/master/app/app.php)
```php
/**
 * Serialization from actions
 * @param string $callback
 * @param string $expl
 * @return array
 */
public function _s( string $callback, string $expl = ',' ): array
```

## Parameters

### `$callback`
Unique callback for retrieving data.     

**Type**: `string ( required )`

### `$expl`
Character for dividing data.       

**Type**: `string ( optional )`


## Related

### [`App::_()`](/developer/method/_)



