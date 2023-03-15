# Admin Custom Panel

BoidCMS offers the ability to create custom pages for the admin panel via the [`admin`](/developer/actions) action. While [SysaCSS](https://sysacss.pages.dev/) is the default styling framework for BoidCMS, you can opt to use an alternative framework.


## Example code

```php
<?php

$App->set_action( 'admin', 'custom_admin_panel_page' );

/**
 * Custom HTML
 * @return void
 */
function custom_admin_panel_page(): void {
  global $App, $layout, $page;
  // Define the custom page path and check
  if ( 'custom-panel-page' === $page ) {
    // The page matches, modify the output
    $layout[ 'title' ] = 'Custom Admin Panel Page';
    $layout[ 'content' ] = '
    <h2 class="ss-monospace">Custom Admin Panel Page</h2>
    <p>This is the custom admin panel page.</p>';
    require_once $App->root( 'app/layout.php' );
  }
}
?>
```
