# Admin Custom Panel

BoidCMS offers the ability to create custom pages for the admin panel via the [`admin`](/developer/actions) action. While [SysaCSS](https://sysacss.pages.dev/) is the default styling framework for BoidCMS, you can opt to use an alternative framework.


## Example code
The following code generates an admin panel page with the slug `custom-admin-panel-page-slug`.

```php
<?php

$App->set_action( 'admin', 'custom_admin_panel_page' );

/**
 * Custom admin view
 * @return void
 */
function custom_admin_panel_page(): void {
  global $App, $layout, $page;
  
  // Define the custom page path and check
  // if the page matches, then modify the output
  if ( 'custom-panel-page-slug' === $page ) {
    
    // Set custom title
    $layout[ 'title' ] = 'Custom Admin Panel Page';
    
    // Set the HTML view content
    $layout[ 'content' ] = '<p>This is the custom admin panel page <b>HTML</b> content.</p>';
    
    // Include the template file
    require_once $App->root( 'app/layout.php' );
  }
}
?>
```

### Add link to navigation menu
The following code adds a link to the admin navigation menu.

```php
<?php

$App->set_action( 'admin_nav', 'custom_admin_panel_page_nav' );

/**
 * Custom admin view link
 * @return string
 */
function custom_admin_panel_page_nav(): string {
  global $App, $page;
  $slug = $App->admin_url( '?page=custom-panel-page-slug' );
  $active = ( 'custom-panel-page-slug' === $page ? ' ss-dotted' : '' );
  return '<a href="' . $slug . '" class="ss-btn ss-inverted ss-bd-none ss-white' . $active . '">Custom Page</a>';
}
?>
```



