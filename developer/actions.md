# Actions
In BoidCMS, the term `Actions` encompasses both [`Events`](/developer/plugin-api?id=event) and [`Filters`](/developer/plugin-api?id=filter).

Developers can extend the functionality of their site using a variety of actions offered by BoidCMS. These actions include those utilized in plugins and themes, as well as those integrated into the core itself.

Here is a list of all the actions.

## Core

|         Action       |    Execute in    |               Parameters           |   Type   |   Info   |   Since  |
| :------------------: | :--------------: | :--------------------------------: | :------: | :------: | :------: |
|         `log`        |    `App::log`    |     `(string) $message, $type`     |  `Event` | This event is triggered every time a message is logged using the `App::log` method. |  `1.0.0` |
|         `save`       |    `App::save`   |                                    |  `Event` | This event is triggered every time the database is saved. |  `1.0.0` |
|      `create_page`   |`App::create_page`|  `(string) $slug, (array) $details`|  `Event` | This event is triggered whenever a new page is created. |  `1.0.0` |
|      `update_page`   |`App::update_page`|`(string) $slug, (string) $permalink, (array) $updates`|`Event`| This event is triggered whenever a page is updated. |  `1.0.0` |
|      `delete_page`   |`App::delete_page`|           `(string) $slug`         |  `Event` | This event is triggered whenever a page is deleted. |  `1.0.0` |
|      `media_mime`    |`App::upload_media`|                                   | `Filter` |          |  `1.0.0` |
|     `upload_media`   |`App::upload_media`|   `(?string) &$basename, &$msg`   |  `Event` | This event is triggered whenever a file is uploaded. |  `1.0.0` |
|     `delete_media`   |`App::delete_media`|         `(string) $media`         |  `Event` | This event is triggered whenever a file is deleted. |  `1.0.0` |
|       `install`      |  `App::install`  |        `(string) $plugin`          |  `Event` | This event is triggered whenever a plugin is installed. |  `1.0.0` |
|      `uninstall`     | `App::uninstall` |        `(string) $plugin`          |  `Event` | This event is triggered whenever a plugin is uninstalled. |  `1.0.0` |
|      `slug_taken`    |  `App::slugify`  |                                    |  `Filter`|          |  `1.0.0` |
|          `go`        |     `App::go`    |       `(string) $location`         |  `Event` | This event is triggered whenever the App:go method is used to send a redirection. |  `1.0.0` |
|     `token_error`    |    `App::auth`   |         `(string) $token`          |  `Event` | This event is triggered whenever an invalid token is received in the admin panel. |  `1.0.0` |
|         `login`      |   `App::admin`   |                                    |  `Event` | This event is triggered when a user is not logged in and attempts to access the admin panel. |  `1.0.0` |
|         `form`       |   `App::admin`   |                                    |  `Filter`|          |  `1.0.0` |
|       `on_login`     |   `App::admin`   |                                    |  `Event` | This event is triggered every time a login form is submitted. |  `1.0.0` |
|    `login_success`   |   `App::admin`   |                                    |  `Event` | This event is triggered when a login attempt is successful with valid credentials. |  `1.0.0` |
|     `login_error`    |   `App::admin`   |  `(string) $username, $password`   |  `Event` | This event is triggered when a login attempt is made with invalid credentials. |  `1.0.0` |
|        `admin`       |   `App::admin`   |                                    |  `Event` | This event is triggered on every admin panel page load when the admin is logged in. |  `1.0.0` |
|         `type`       |   `App::admin`   |                                    |  `Filter`|          |  `1.0.0` |
|          `tpl`       |   `App::admin`   |                                    |  `Filter`|          |  `2.0.0` |
|      `thumb_ext`     |   `App::admin`   |                                    |  `Filter`|          |  `1.0.0` |
|      `on_create`     |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form to create a new page is submitted. |  `1.0.0` |
|    `create_success`  |   `App::admin`   |       `(string) $permalink`        |  `Event` | This event is triggered when a form to create a new page is submitted and the page is successfully created. |  `1.0.0` |
|     `create_error`   |   `App::admin`   |`(string) $permalink, (array) $_POST`| `Event` | This event is triggered when a form to create a new page is submitted, but the page creation process fails. |  `1.0.0` |
|      `on_delete`     |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form to delete a page is submitted. |  `1.0.0` |
|   `delete_success`   |   `App::admin`   |          `(string) $page`          |  `Event` | This event is triggered when a form to delete a page is submitted and the page(s) are successfully deleted. |  `1.0.0` |
|    `delete_error`    |   `App::admin`   |          `(string) $page`          |  `Event` | This event is triggered when a form to delete a page is submitted, but the page(s) fail to be deleted. |  `1.0.0` |
|      `on_update`     |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form to update a page is submitted. |  `1.0.0` |
|    `update_success`  |   `App::admin`   |         `(string) $action`         |  `Event` | This event is triggered when a form to update a page is submitted and the page is successfully updated. |  `1.0.0` |
|     `update_error`   |   `App::admin`   | `(string) $action, (array) $_POST` |  `Event` | This event is triggered when a form to update a page is submitted, but the page update process fails. |  `1.0.0` |
|    `media_list_top`  |   `App::admin`   |          `(string) $media`         |  `Filter`|          |  `1.0.0` |
|    `media_list_end`  |   `App::admin`   |          `(string) $media`         |  `Filter`|          |  `1.0.0` |
|      `on_media`      |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form on the file manager page is submitted. |  `1.0.0` |
|   `plugin_list_top`  |   `App::admin`   |         `(string) $plugin`         |  `Filter`|          |  `1.0.0` |
|   `plugin_list_end`  |   `App::admin`   |         `(string) $plugin`         |  `Filter`|          |  `1.0.0` |
|      `on_plugin`     |   `App::admin`   |                                    |  `Event` | This event is triggered every time a button to install a plugin is clicked. |  `1.0.0` |
|        `logout`      |   `App::admin`   |                                    |  `Event` | This event is triggered every time a logged-in admin visits the logout page. |  `1.0.0` |
|     `on_settings`    |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form to update the settings on the settings page is submitted. |  `1.0.0` |
|    `change_theme`    |   `App::admin`   |     `(string) $_POST[ 'theme' ]`   |  `Event` | This event is triggered every time a form to update the settings on the settings page is submitted, specifically to check if the theme has been changed or not. |  `1.0.0` |
|  `settings_success`  |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form on the settings page is submitted and the settings are successfully saved. |  `1.0.0` |
|   `settings_error`   |   `App::admin`   |          `(array) $data`           |  `Event` | This event is triggered every time a form on the settings page is submitted, but the settings are not saved. |  `1.0.0` |
|     `on_password`    |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form to update the password on the settings page is submitted. |  `1.0.0` |
|  `password_success`  |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form to update the password on the settings page is submitted and the new password is successfully saved. |  `1.0.0` |
|   `password_error`   |   `App::admin`   |                                    |  `Event` | This event is triggered every time a form to update the password on the settings page is submitted, but the new password is not saved because the old password provided is incorrect. |  `1.0.0` |
|      `dashboard`     |   `App::admin`   |                                    |  `Filter`|          |  `1.0.0` |
|       `render`       |   `App::render`  |                                    |  `Event` |          |  `1.0.0` |
|        `index`       |   `App::render`  |                                    |  `Filter`|          |  `1.0.0` |
|        `home`        |   `App::render`  |                                    |  `Event` |          |  `1.0.0` |
|   `{PAGE_TYPE}_type` |   `App::render`  |                                    |  `Event` |          |  `1.0.0` |
|         `404`        |   `App::render`  |          `(string) $page`          |  `Event` |          |  `1.0.0` |
|      `rendered`      |   `App::render`  |                                    |  `Event` |          |  `1.0.0` |


## Preserved
|         Action       |    Execute in    |               Parameters           |    Type   |   Info   |   Since  |
| :------------------: | :--------------: | :--------------------------------: | :-------: | :------: | :------: |
|   `editable_pages`   |                  |                                    |  `Filter` |          |  `1.0.0` |



## Admin view

|       Action      |      Execute in     |  Parameters  |   Type  |  Info   |  Since  |
| :---------------: | :-----------------: | :----------: | :-----: | :-----: | :-----: |
|    `admin_head`   |   `app/layout.php`  |              | `Filter`|         | `1.0.0` |
|     `admin_top`   |   `app/layout.php`  |              | `Filter`|         | `1.0.0` |
|     `admin_nav`   |   `app/layout.php`  |              | `Filter`|         | `1.0.0` |
|   `admin_middle`  |   `app/layout.php`  |              | `Filter`|         | `1.0.0` |
|    `{PAGE}_top`   |   `app/layout.php`  |              | `Filter`|         | `1.0.0` |
|    `{PAGE}_end`   |   `app/layout.php`  |              | `Filter`|         | `1.0.0` |
|   `admin_footer`  |   `app/layout.php`  |              | `Filter`|         | `1.0.0` |
|     `admin_end`   |   `app/layout.php`  |              | `Filter`|         | `1.0.0` |


## Themes

|        Action       |      Execute in     |   Parameters   |   Type  |  Info   |  Since  |
| :-----------------: | :-----------------: | :------------: | :-----: | :-----: | :-----: |
|       `favicon`     |                     |                | `Filter`|         | `1.0.0` |
|      `site_nav`     |                     |                | `Filter`|         | `1.0.0` |
|     `site_head`     |                     |                | `Filter`|         | `1.0.0` |
|      `site_top`     |                     |                | `Filter`|         | `1.0.0` |
|    `site_footer`    |                     |                | `Filter`|         | `1.0.0` |
|      `site_end`     |                     |                | `Filter`|         | `1.0.0` |
|`site_under_subtitle`|                     |                | `Filter`|         | `1.0.0` |
|      `home_top`     |                     |                | `Filter`|         | `1.0.0` |
|   `post_list_top`   |                     |`(string) $slug`| `Filter`|         | `1.0.0` |
|   `post_list_end`   |                     |`(string) $slug`| `Filter`|         | `1.0.0` |
|      `home_end`     |                     |                | `Filter`|         | `1.0.0` |
|      `post_top`     |                     |                | `Filter`|         | `1.0.0` |
| `site_under_title`  |                     |                | `Filter`|         | `1.0.0` |
| `post_content_top`  |                     |                | `Filter`|         | `1.0.0` |
| `post_content_end`  |                     |                | `Filter`|         | `1.0.0` |
|      `post_end`     |                     |                | `Filter`|         | `1.0.0` |
|      `home_end`     |                     |                | `Filter`|         | `1.0.0` |
|      `page_top`     |                     |                | `Filter`|         | `1.0.0` |
|      `page_end`     |                     |                | `Filter`|         | `1.0.0` |

?> It's possible that not all themes will support the actions listed above.



