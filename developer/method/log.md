# `App::log()` Method


```php
/**
 * Log a debug message
 * @param string $message
 * @param string $type
 * @return bool
 */
public function log( string $message, string $type = 'debug' ): bool {
  $this->get_action( 'log', $message, $type );
  if ( ! $this->get( 'log' ) ) {
    return false;
  }
}
```

## Parameters

### `$message`
### `$type`
