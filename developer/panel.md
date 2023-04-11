# Admin Custom Panel

BoidCMS offers the ability to create custom pages for the admin panel via the [`admin`](/developer/actions) action. While [SysaCSS](https://sysacss.pages.dev/) is the default styling framework for BoidCMS, you can opt to use an alternative framework.

?> It is important to note that default admin panels already exist in the system. Therefore, when creating a custom panel, it is crucial to ensure that you do not use the same slug as the default panel, as this may result in overriding the default panel.

Here are the default admin panel slugs:
- ` ` (empty) - this is the default dashboard page
- `settings` - this panel is used for site settings and configurations
- `create` - use this panel to create new pages or posts
- `update` - use this panel to update existing pages or posts
- `delete` - use this panel to delete existing pages or posts
- `media` - use this panel to manage media files such as images and videos
- `plugins` - this panel is used to manage installed plugins
- `themes` - this panel is used to manage installed themes
- `logout` - this panel logs the user out of the admin panel and back to the site

Be sure to choose unique and specific slugs for your custom admin panels to avoid any potential conflicts with the default panels.


## Example code
The following code generates an admin panel page with the slug `custom-admin-panel-page-slug`.

```php
<?php
/**
 * Registers a callback function to execute when the "admin" event is triggered.
 *
 * @param string|array $action The name of the action to which the event is hooked.
 * @param callable $callback The callback function to execute when the event is triggered.
 * @param int $priority Optional. The priority of the callback function. Default is 10.
 * @return void
 */
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
/**
 * Registers a callback function to execute when the "admin_nav" filter is applied.
 *
 * @param string|array $action The name of the action to which the filter is hooked.
 * @param callable $callback The callback function to execute when the filter is applied.
 * @param int $priority Optional. The priority of the filter function. Default is 10.
 * @return void
 */
$App->set_action( 'admin_nav', 'custom_admin_panel_page_nav' );

/**
 * Custom admin view link
 * @return string
 */
function custom_admin_panel_page_nav(): string {
  global $App, $page;
  $slug = $App->admin_url( '?page=custom-panel-page-slug' );
  $active = ( 'custom-panel-page-slug' === $page ? ' ss-dotted' : '' );
  return "<a href=\"$slug\" class=\"ss-btn ss-inverted ss-bd-none ss-white$active\">Custom Page</a>";
}
?>
```



