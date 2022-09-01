# Actions
The word `Actions` in BoidCMS represents both `Events` and `Filters`. 

BoidCMS has a lot of actions called within the core and the templates, And that makes it super extensible.     
Actions are used to extend and/or to implement something to the site, actions can be used in/by [Plugins](plugins/) and [Themes](themes/).       


Here is the list of all actions.

## Core

|         Action       |    Execute in    |               Parameters           |   Since  |
| :------------------: | :--------------: | :--------------------------------: | :------: |
|         `log`        |    `App::log`    |     `(string) $message, $type`     |  `1.0.0` |
|         `save`       |    `App::save`   |                                    |  `1.0.0` |
|      `create_page`   |`App::create_page`|  `(string) $slug, (array) $details`|  `1.0.0` |
|      `update_page`   |`App::update_page`| `(string) $slug, (string) $permalink, (array) $updates`|  `1.0.0` |
|      `delete_page`   |`App::delete_page`|           `(string) $slug`         |  `1.0.0` |
|      `media_mime`    |`App::upload_media`|                                   |  `1.0.0` |
|     `upload_media`   |`App::upload_media`|   `(?string) &$basename, &$msg`   |  `1.0.0` |
|     `delete_media`   |`App::delete_media`|         `(string) $media`         |  `1.0.0` |
|       `install`      |  `App::install`  |        `(string) $plugin`          |  `1.0.0` |
|      `uninstall`     | `App::uninstall` |        `(string) $plugin`          |  `1.0.0` |
|      `slug_taken`    |  `App::slugify`  |                                    |  `1.0.0` |
|          `go`        |     `App::go`    |       `(string) $location`         |  `1.0.0` |
|     `token_error`    |    `App::auth`   |         `(string) $token`          |  `1.0.0` |
|         `login`      |   `App::admin`   |                                    |  `1.0.0` |
|         `form`       |   `App::admin`   |                                    |  `1.0.0` |
|       `on_login`     |   `App::admin`   |                                    |  `1.0.0` |
|    `login_success`   |   `App::admin`   |                                    |  `1.0.0` |
|     `login_error`    |   `App::admin`   |  `(string) $username, $password`   |  `1.0.0` |
|        `admin`       |   `App::admin`   |                                    |  `1.0.0` |
|         `type`       |   `App::admin`   |                                    |  `1.0.0` |
|      `thumb_ext`     |   `App::admin`   |                                    |  `1.0.0` |
|      `on_create`     |   `App::admin`   |                                    |  `1.0.0` |
|    `create_success`  |   `App::admin`   |       `(string) $permalink`        |  `1.0.0` |
|     `create_error`   |   `App::admin`   |`(string) $permalink, (array) $_POST`|  `1.0.0` |
|      `on_delete`     |   `App::admin`   |                                    |  `1.0.0` |
|   `delete_success`   |   `App::admin`   |          `(string) $page`          |  `1.0.0` |
|    `delete_error`    |   `App::admin`   |          `(string) $page`          |  `1.0.0` |
|      `on_update`     |   `App::admin`   |                                    |  `1.0.0` |
|    `update_success`  |   `App::admin`   |         `(string) $action`         |  `1.0.0` |
|     `update_error`   |   `App::admin`   | `(string) $action, (array) $_POST` |  `1.0.0` |
|    `media_list_top`  |   `App::admin`   |          `(string) $media`         |  `1.0.0` |
|    `media_list_end`  |   `App::admin`   |          `(string) $media`         |  `1.0.0` |
|      `on_media`      |   `App::admin`   |                                    |  `1.0.0` |
|   `plugin_list_top`  |   `App::admin`   |         `(string) $plugin`         |  `1.0.0` |
|   `plugin_list_end`  |   `App::admin`   |         `(string) $plugin`         |  `1.0.0` |
|      `on_plugin`     |   `App::admin`   |                                    |  `1.0.0` |
|        `logout`      |   `App::admin`   |                                    |  `1.0.0` |
|     `on_settings`    |   `App::admin`   |                                    |  `1.0.0` |
|    `change_theme`    |   `App::admin`   |     `(string) $_POST[ 'theme' ]`   |  `1.0.0` |
|  `settings_success`  |   `App::admin`   |                                    |  `1.0.0` |
|   `settings_error`   |   `App::admin`   |          `(array) $data`           |  `1.0.0` |
|     `on_password`    |   `App::admin`   |                                    |  `1.0.0` |
|  `password_success`  |   `App::admin`   |                                    |  `1.0.0` |
|   `password_error`   |   `App::admin`   |                                    |  `1.0.0` |
|      `dashboard`     |   `App::admin`   |                                    |  `1.0.0` |
|       `render`       |   `App::render`  |                                    |  `1.0.0` |
|        `home`        |   `App::render`  |                                    |  `1.0.0` |
|   `{PAGE_TYPE}_type` |   `App::render`  |                                    |  `1.0.0` |
|         `404`        |   `App::render`  |          `(string) $page`          |  `1.0.0` |
|      `rendered`      |   `App::render`  |                                    |  `1.0.0` |


## Admin view

|       Action      |      Execute in     |  Parameters  |  Since  |
| :---------------: | :-----------------: | :----------: | :-----: |
|    `admin_head`   |   `app/layout.php`  |              | `1.0.0` |
|     `admin_top`   |   `app/layout.php`  |              | `1.0.0` |
|     `admin_nav`   |   `app/layout.php`  |              | `1.0.0` |
|   `admin_middle`  |   `app/layout.php`  |              | `1.0.0` |
|    `{PAGE}_top`   |   `app/layout.php`  |              | `1.0.0` |
|    `{PAGE}_end`   |   `app/layout.php`  |              | `1.0.0` |
|   `admin_footer`  |   `app/layout.php`  |              | `1.0.0` |
|     `admin_end`   |   `app/layout.php`  |              | `1.0.0` |


## Themes

|        Action       |      Execute in     |   Parameters   |  Since  |
| :-----------------: | :-----------------: | :------------: | :-----: |
|     `site_head`     |                     |                | `1.0.0` |
|      `site_top`     |                     |                | `1.0.0` |
|    `site_footer`    |                     |                | `1.0.0` |
|      `site_end`     |                     |                | `1.0.0` |
|`site_under_subtitle`|                     |                | `1.0.0` |
|      `home_top`     |                     |                | `1.0.0` |
|   `post_list_top`   |                     |`(string) $slug`| `1.0.0` |
|   `post_list_end`   |                     |`(string) $slug`| `1.0.0` |
|      `home_end`     |                     |                | `1.0.0` |
|      `post_top`     |                     |                | `1.0.0` |
| `site_under_title`  |                     |                | `1.0.0` |
| `post_content_top`  |                     |                | `1.0.0` |
| `post_content_end`  |                     |                | `1.0.0` |
|      `post_end`     |                     |                | `1.0.0` |
|      `home_end`     |                     |                | `1.0.0` |
|      `page_top`     |                     |                | `1.0.0` |
| `site_under_title`  |                     |                | `1.0.0` |
|      `page_end`     |                     |                | `1.0.0` |

?> Not all themes might support the actions listed above.




