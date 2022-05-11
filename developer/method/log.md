# `App::log()` Method
Message debugging.     

```php
/**
 * Log a debug message
 * @param string $message
 * @param string $type
 * @return bool
 */
public function log( string $message, string $type = 'debug' ): bool
```

## Parameters

### `$message`
Text message to debug.       
**Type**: `string ( required )`

### `$type`
The type of debugging, eg `warning`, `fatal`.      
**Type**: `string ( optional )`


## Related

### [`App::get_action()`](/developer/method/get_action)
