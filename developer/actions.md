# Actions
In BoidCMS, the term `Actions` encompasses both [`Events`](/developer/plugin-api?id=event) and [`Filters`](/developer/plugin-api?id=filter).

Developers can extend the functionality of their site using a variety of actions offered by BoidCMS. These actions include those utilized in plugins and themes, as well as those integrated into the core itself.

Here is a list of all the actions.

## Core

|         Action       |    Execute in    |                     Parameters                   |   Type   |   Info   |   Since  |
| :------------------: | :--------------: | :----------------------------------------------: | :------: | :------: | :------: |
|         `log`        |    `App::log`    |  (`string`) `$message` <br> (`string`) `$type`   |  `Event` | This event is triggered every time a message is logged using the `App::log` method. |  `1.0.0` |
|         `save`       |    `App::save`   |                                                  |  `Event` | This event is triggered every time the database is saved. |  `1.0.0` |
|         `page`       |    `App::page`   |(`mixed`) `$content`, <br> (`string`) `$index`, <br> (`string`) `$page`, <br> (`array`) `$data` |`Filter`| This filter is used to dynamically modify the value of a specific key within a given page. | `1.0.0` |
|      `create_page`   |`App::create_page`|     (`string`) `$slug`, <br> (`array`) `$details`     |  `Event` | This event is triggered whenever a new page is created. |  `1.0.0` |
|      `update_page`   |`App::update_page`|(`string`) `$slug`, <br> (`string`) `$permalink`, <br> (`array`) `$updates`|`Event`| This event is triggered whenever a page is updated. |  `1.0.0` |
|      `delete_page`   |`App::delete_page`|           (`string`) `$slug`         |  `Event` | This event is triggered whenever a page is deleted. |  `1.0.0` |
|      `media_mime`    |`App::upload_media`|                                   | `Filter` | This filter is used to add custom MIME types that the website can recognize and accept. |  `1.0.0` |
|     `upload_media`   |`App::upload_media`|   (`string|null`) `&$basename`, <br> (`string|null`) `&$msg`   |  `Event` | This event is triggered whenever a file is uploaded. |  `1.0.0` |
|     `delete_media`   |`App::delete_media`|         (`string`) `$media`         |  `Event` | This event is triggered whenever a file is deleted. |  `1.0.0` |
|       `install`      |  `App::install`  |        (`string`) `$plugin`          |  `Event` | This event is triggered whenever a plugin is installed. |  `1.0.0` |
|      `uninstall`     | `App::uninstall` |        (`string`) `$plugin`          |  `Event` | This event is triggered whenever a plugin is uninstalled. |  `1.0.0` |
|      `slug_taken`    |  `App::slugify`  |                                    |  `Filter`| This filter is used to specify custom paths that are already taken and therefore not valid for creating new pages. |  `1.0.0` |
|          `go`        |     `App::go`    |       (`string`) `$location`         |  `Event` | This event is triggered whenever the `App::go` method is used to send a redirection. |  `1.0.0` |
|     `token_error`    |    `App::auth`   |         (`string`) `$token`          |  `Event` | This event is triggered whenever an invalid token is received in the admin panel. |  `1.0.0` |
|         `login`      |   `App::admin`   |                                    |  `Event` | This event is triggered when a user is not logged in and attempts to access the admin panel. |  `1.0.0` |
|         `form`       |   `App::admin`   |                                    |  `Filter`| This filter is used to add custom HTML to every form that is displayed in the admin panel, including the login page. It provides an opportunity to enhance the appearance and functionality of forms and add custom elements, such as buttons or fields, to the forms. |  `1.0.0` |
|       `on_login`     |   `App::admin`   |                                    |  `Event` | This event is triggered every time a login form is submitted. |  `1.0.0` |
|    `login_success`   |   `App::admin`   |                                    |  `Event` | This event is triggered when a login attempt is successful with valid credentials. |  `1.0.0` |
|     `login_error`    |   `App::admin`   |  (`string`) `$username`, <br> (`string`) `$password`   |  `Event` | This event is triggered when a login attempt is made with invalid credentials. |  `1.0.0` |
|        `admin`       |   `App::admin`   |                                    |  `Event` | This event is triggered on every admin panel page load when the admin is logged in. |  `1.0.0` |
|         `type`       |   `App::admin`   |                                    |  `Filter`| This filter is used to add custom page types to the list of available options. |  `1.0.0` |
|          `tpl`       |   `App::admin`   |                                    |  `Filter`| This filter is used to add custom page templates to the list of available options. |  `2.0.0` |
|      `thumb_ext`     |   `App::admin`   |                                    |  `Filter`| This filter is used to add custom image file extensions to be recognized as thumbnails in the media library. |  `1.0.0` |
|      `on_create`     |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form to create a new page is submitted. |  `1.0.0` |
|    `create_success`  |   `App::admin`   |       (`string`) `$permalink`        |  `Event` | This event is triggered when a form to create a new page is submitted and the page is successfully created. |  `1.0.0` |
|     `create_error`   |   `App::admin`   |(`string`) `$permalink`, <br> (`array`) `$_POST`| `Event` | This event is triggered when a form to create a new page is submitted, but the page creation process fails. |  `1.0.0` |
|      `on_delete`     |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form to delete a page is submitted. |  `1.0.0` |
|   `delete_success`   |   `App::admin`   |          (`string`) `$page`          |  `Event` | This event is triggered when a form to delete a page is submitted and the page is successfully deleted. |  `1.0.0` |
|    `delete_error`    |   `App::admin`   |          (`string`) `$page`          |  `Event` | This event is triggered when a form to delete a page is submitted, but the page fail to be deleted. |  `1.0.0` |
|      `on_update`     |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form to update a page is submitted. |  `1.0.0` |
|    `update_success`  |   `App::admin`   |         (`string`) `$action`         |  `Event` | This event is triggered when a form to update a page is submitted and the page is successfully updated. |  `1.0.0` |
|     `update_error`   |   `App::admin`   | (`string`) `$action`, <br> (`array`) `$_POST` |  `Event` | This event is triggered when a form to update a page is submitted, but the page update process fails. |  `1.0.0` |
|    `media_list_top`  |   `App::admin`   |          (`string`) `$media`         |  `Filter`| This filter can be used to add custom HTML to the top of each media file in the list. |  `1.0.0` |
|    `media_list_end`  |   `App::admin`   |          (`string`) `$media`         |  `Filter`| This filter is used to add custom HTML to the bottom of each media file in the list. |  `1.0.0` |
|      `on_media`      |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form on the file manager page is submitted. |  `1.0.0` |
|   `plugin_list_top`  |   `App::admin`   |         (`string`) `$plugin`         |  `Filter`| This filter is used to add custom HTML on top of each plugin in the list. |  `1.0.0` |
|   `plugin_list_end`  |   `App::admin`   |         (`string`) `$plugin`         |  `Filter`| This filter is used to add custom HTML below each plugin in the list. |  `1.0.0` |
|      `on_plugin`     |   `App::admin`   |                                    |  `Event` | This event is triggered every time a button to install a plugin is clicked. |  `1.0.0` |
|        `logout`      |   `App::admin`   |                                    |  `Event` | This event is triggered every time a logged-in admin visits the logout page. |  `1.0.0` |
|     `on_settings`    |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form to update the settings on the settings page is submitted. |  `1.0.0` |
|    `change_theme`    |   `App::admin`   |         (`string`) `$theme`          |  `Event` | This event is triggered whenever a theme is activated. |  `1.0.0` |
|  `settings_success`  |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form on the settings page is submitted and the settings are successfully saved. |  `1.0.0` |
|   `settings_error`   |   `App::admin`   |          (`array`) `$data`           |  `Event` | This event is triggered every time a form on the settings page is submitted, but the settings are not saved. |  `1.0.0` |
|     `on_password`    |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form to update the password on the settings page is submitted. |  `1.0.0` |
|  `password_success`  |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form to update the password on the settings page is submitted and the new password is successfully saved. |  `1.0.0` |
|   `password_error`   |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form to update the password on the settings page is submitted, but the new password is not saved because the old password provided is incorrect. |  `1.0.0` |
|      `dashboard`     |   `App::admin`   |                                    |  `Filter`| This filter can be used to add custom HTML content to the admin dashboard. |  `1.0.0` |
|       `render`       |   `App::render`  |                                    |  `Event` | This event is triggered on every page load as the first event. |  `1.0.0` |
|        `index`       |   `App::render`  |                                    |  `Filter`| This filter allows for dynamic customization of the homepage path. |  `1.0.0` |
|        `home`        |   `App::render`  |                                    |  `Event` | This event is triggered on every page load that is the homepage. |  `1.0.0` |
|   `{PAGE_TYPE}_type` |   `App::render`  |                                    |  `Event` | This event is triggered on every page load that is not the homepage. |  `1.0.0` |
|         `404`        |   `App::render`  |          (`string`) `$page`          |  `Event` | This event is triggered when the requested page does not exist. |  `1.0.0` |
|      `rendered`      |   `App::render`  |                                    |  `Event` | This event is triggered on every page load as the last event. |  `1.0.0` |


## Preserved
|         Action       |    Execute in    |               Parameters           |    Type   |               Info               |   Since  |
| :------------------: | :--------------: | :--------------------------------: | :-------: | :------------------------------: | :------: |
|   `editable_pages`   |                  |                                    |  `Filter` | This filter is used to add admin panels that contain editable fields for WYSIWYG editors. |  `1.0.0` |



## Admin view

|       Action      |      Execute in     |  Parameters  |   Type  |  Info   |  Since  |
| :---------------: | :-----------------: | :----------: | :-----: | :-----: | :-----: |
|    `admin_head`   |   `app/layout.php`  |              | `Filter`| This filter is used to add custom HTML to the `<head>` section of the admin panel. | `1.0.0` |
|     `admin_top`   |   `app/layout.php`  |              | `Filter`| This filter is used to add custom HTML to the admin panel after the `<body>` tag. | `1.0.0` |
|     `admin_nav`   |   `app/layout.php`  |              | `Filter`| This filter is used to add custom HTML to the admin navigation menu. | `1.0.0` |
|   `admin_middle`  |   `app/layout.php`  |              | `Filter`| This filter is used to add custom HTML below the alerts section on the admin panel. | `1.0.0` |
|    `{$page}_top`   |   `app/layout.php`  |              | `Filter`| This filter is used to add custom HTML to the admin panel above the title of specific page. | `1.0.0` |
|    `{$page}_end`   |   `app/layout.php`  |              | `Filter`| This filter is used to add custom HTML to the admin panel below the content of specific page. | `1.0.0` |
|   `admin_footer`  |   `app/layout.php`  |              | `Filter`| This filter is used to add custom HTML to the footer section of the admin pages. | `1.0.0` |
|     `admin_end`   |   `app/layout.php`  |              | `Filter`| This filter is used to add custom HTML to the admin panel before the `</body>` tag. | `1.0.0` |


## Themes

|        Action       |      Execute in     |      Parameters    |   Type  |  Info   |  Since  |
| :-----------------: | :-----------------: | :----------------: | :-----: | :-----: | :-----: |
|       `favicon`     |                     | (`string`) `$link` | `Filter`| This filter is used to add custom HTML `favicon` tags to the website. | `1.0.0` |
|      `site_nav`     |                     |(`string`) `$format`| `Filter`| This filter allows adding a custom menu item to the site's navigation menu. The `$format` parameter is a `sprintf()`-compatible format that includes two placeholders for swapping - the link URL and link text. | `1.0.0` |
|     `site_head`     |                     |                    | `Filter`| This filter is used to add custom HTML to the `<head>` section of the site, such as meta tags or scripts. | `1.0.0` |
|      `site_top`     |                     |                    | `Filter`| This filter is used to add custom HTML immediately after the opening `<body>` tag. | `1.0.0` |
|    `site_footer`    |                     |                    | `Filter`| This filter is used to add custom HTML to the site footer, which appears at the bottom of every page. | `1.0.0` |
|      `site_end`     |                     |                    | `Filter`| This filter is used to add custom HTML immediately before the closing `</body>` tag. | `1.0.0` |
|`site_under_subtitle`|                     |                    | `Filter`| This filter is used to add custom HTML below the site subtitle, in a specific section of the site determined by the theme or page template. | `1.0.0` |
|      `home_top`     |                     |                    | `Filter`| This filter is used to add custom HTML to the top of the blog homepage, which usually displays a selection of recent posts. | `1.0.0` |
|   `post_list_top`   |                     | (`string`) `$slug` | `Filter`| This filter is used to add custom HTML to the top of each post in the list of articles. | `1.0.0` |
|   `post_list_end`   |                     | (`string`) `$slug` | `Filter`| This filter is used to add custom HTML to the bottom of each post in the list of articles. | `1.0.0` |
|      `home_end`     |                     |                    | `Filter`| This filter is used to add custom HTML to the bottom of the blog homepage, which usually displays a selection of recent posts. | `1.0.0` |
|      `post_top`     |                     |                    | `Filter`| This filter is used to add custom HTML at the beginning of each blog post, before the title and content. | `1.0.0` |
| `site_under_title`  |                     |                    | `Filter`| This filter is used to add custom HTML below the title of each page. | `1.0.0` |
| `post_content_top`  |                     |                    | `Filter`| This filter is used to add custom HTML immediately before the post content, such as buttons for sharing on social media. | `1.0.0` |
| `post_content_end`  |                     |                    | `Filter`| This filter is used to add custom HTML immediately after the post content, for example, comments. | `1.0.0` |
|      `post_end`     |                     |                    | `Filter`| This filter is used to add custom HTML to the bottom of each blog post page, such as related posts or author information. | `1.0.0` |
|      `page_top`     |                     |                    | `Filter`| This filter is used to add custom HTML to the top of each static page. | `1.0.0` |
|      `page_end`     |                     |                    | `Filter`| This filter is used to add custom HTML to the bottom of each static page. | `1.0.0` |

?> It's possible that not all themes will support the actions listed above.



