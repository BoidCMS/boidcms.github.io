# Actions
The word `Actions` in BoidCMS represents both the `Events` and the `Filters`. 

<!--BoidCMS has a lot of actions called within the core and the templates, And that makes it **super extensible**.     
Actions are used to extend and/or to implement something to the site, actions can be used in and by [Plugins](plugins/) or [Themes](themes/).    -->
BoidCMS offers a wide range of actions for developers to extend the functionality of their site. These include actions that are used in plugins and themes, as well as those that are implemented within the core itself.

Here are the list of all preserved actions.

## Core

|         Action       |    Execute in    |               Parameters           |   Type   |   Info   |   Since  |
| :------------------: | :--------------: | :--------------------------------: | :------: | :------: | :------: |
|         `log`        |    `App::log`    |     `(string) $message, $type`     |  `Event` |          |  `1.0.0` |
|         `save`       |    `App::save`   |                                    |  `Event` |          |  `1.0.0` |
|      `create_page`   |`App::create_page`|  `(string) $slug, (array) $details`|  `Event` |          |  `1.0.0` |
|      `update_page`   |`App::update_page`|`(string) $slug, (string) $permalink, (array) $updates`|`Event`|     |  `1.0.0` |
|      `delete_page`   |`App::delete_page`|           `(string) $slug`         |  `Event` |          |  `1.0.0` |
|      `media_mime`    |`App::upload_media`|                                   | `Filter` |          |  `1.0.0` |
|     `upload_media`   |`App::upload_media`|   `(?string) &$basename, &$msg`   |  `Event` |          |  `1.0.0` |
|     `delete_media`   |`App::delete_media`|         `(string) $media`         |  `Event` |          |  `1.0.0` |
|       `install`      |  `App::install`  |        `(string) $plugin`          |  `Event` |          |  `1.0.0` |
|      `uninstall`     | `App::uninstall` |        `(string) $plugin`          |  `Event` |          |  `1.0.0` |
|      `slug_taken`    |  `App::slugify`  |                                    |  `Event` |          |  `1.0.0` |
|          `go`        |     `App::go`    |       `(string) $location`         |  `Event` |          |  `1.0.0` |
|     `token_error`    |    `App::auth`   |         `(string) $token`          |  `Event` |          |  `1.0.0` |
|         `login`      |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|         `form`       |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|       `on_login`     |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|    `login_success`   |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|     `login_error`    |   `App::admin`   |  `(string) $username, $password`   |  `Event` |          |  `1.0.0` |
|        `admin`       |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|         `type`       |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|          `tpl`       |   `App::admin`   |                                    |  `Event` |          |  `2.0.0` |
|      `thumb_ext`     |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|      `on_create`     |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|    `create_success`  |   `App::admin`   |       `(string) $permalink`        |  `Event` |          |  `1.0.0` |
|     `create_error`   |   `App::admin`   |`(string) $permalink, (array) $_POST`| `Event` |          |  `1.0.0` |
|      `on_delete`     |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|   `delete_success`   |   `App::admin`   |          `(string) $page`          |  `Event` |          |  `1.0.0` |
|    `delete_error`    |   `App::admin`   |          `(string) $page`          |  `Event` |          |  `1.0.0` |
|      `on_update`     |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|    `update_success`  |   `App::admin`   |         `(string) $action`         |  `Event` |          |  `1.0.0` |
|     `update_error`   |   `App::admin`   | `(string) $action, (array) $_POST` |  `Event` |          |  `1.0.0` |
|    `media_list_top`  |   `App::admin`   |          `(string) $media`         |  `Event` |          |  `1.0.0` |
|    `media_list_end`  |   `App::admin`   |          `(string) $media`         |  `Event` |          |  `1.0.0` |
|      `on_media`      |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|   `plugin_list_top`  |   `App::admin`   |         `(string) $plugin`         |  `Event` |          |  `1.0.0` |
|   `plugin_list_end`  |   `App::admin`   |         `(string) $plugin`         |  `Event` |          |  `1.0.0` |
|      `on_plugin`     |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|        `logout`      |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|     `on_settings`    |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|    `change_theme`    |   `App::admin`   |     `(string) $_POST[ 'theme' ]`   |  `Event` |          |  `1.0.0` |
|  `settings_success`  |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|   `settings_error`   |   `App::admin`   |          `(array) $data`           |  `Event` |          |  `1.0.0` |
|     `on_password`    |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|  `password_success`  |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|   `password_error`   |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|      `dashboard`     |   `App::admin`   |                                    |  `Event` |          |  `1.0.0` |
|       `render`       |   `App::render`  |                                    |  `Event` |          |  `1.0.0` |
|        `home`        |   `App::render`  |                                    |  `Event` |          |  `1.0.0` |
|   `{PAGE_TYPE}_type` |   `App::render`  |                                    |  `Event` |          |  `1.0.0` |
|         `404`        |   `App::render`  |          `(string) $page`          |  `Event` |          |  `1.0.0` |
|      `rendered`      |   `App::render`  |                                    |  `Event` |          |  `1.0.0` |


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

?> Not all themes might support the actions listed above.




