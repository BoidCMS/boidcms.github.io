# `App::set()` Method
Set a pair of key value to database.       
Returns `true` on success, or `false` on failure.

Source: [app/app.php](https://github.com/BoidCMS/BoidCMS/blob/master/app/app.php)
```php
/**
 *
 */
public function set( mixed $value, string $index ): bool
```

## Parameters

### `$value`
Value to save.     

**Type**: `mixed ( required )`

### `$index`
Key as a name to name value.       

**Type**: `string ( required )`

## Related

### [`App::save()`](/developer/method/save)
