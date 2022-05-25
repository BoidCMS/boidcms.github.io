# Actions
BoidCMS has a lot of actions called within the core, And that makes it even more easier to be extended by [Plugins](plugins).     
And here is the list of all.

## Core

|         Action       |    Execute in    |               Parameters           |   Since  |
| :------------------: | :--------------: | :--------------------------------: | :------: |
|         `log`        |    `App::log`    |     `(string) $message, $type`     |  `1.0.0` |
|         `save`       |    `App::save`   |                                    |  `1.0.0` |
|         `page`       |    `App::page`   |      `(string) $index, $page`      |  `1.0.0` |
|        `create`      |`App::create_page`| `(string) $slug, (array) $details` |  `1.0.0` |
|        `delete`      |`App::delete_page`|         `(string) $slug`           |  `1.0.0` |
|       `install`      |  `App::install`  |        `(string) $plugin`          |  `1.0.0` |
|      `uninstall`     | `App::uninstall` |        `(string) $plugin`          |  `1.0.0` |
|          `go`        |     `App::go`    |       `(string) $location`         |  `1.0.0` |
|     `token_error`    |  `App::validate` |       `(string) $location`         |  `1.0.0` |
|         `form`       |   `App::admin`   |                                    |  `1.0.0` |
|       `on_login`     |   `App::admin`   |                                    |  `1.0.0` |
|    `login_success`   |   `App::admin`   |                                    |  `1.0.0` |
|     `login_error`    |   `App::admin`   |  `(string) $username, $password`   |  `1.0.0` |
|      `page_type`     |   `App::admin`   |                                    |  `1.0.0` |
|         `form`       |   `App::admin`   |                                    |  `1.0.0` |
|      `on_create`     |   `App::admin`   |                                    |  `1.0.0` |
|    `create_success`  |   `App::admin`   |       `(string) $permalink`        |  `1.0.0` |
|     `create_error`   |   `App::admin`   |`(string) $permalink, (array) $_POST`|  `1.0.0` |
|        `logout`      |   `App::admin`   |                                    |  `1.0.0` |
|    `media_upload`    |   `App::admin`   |                                    |  `1.0.0` |
|   `create_success`   |   `App::admin`   |                                    |  `1.0.0` |
|    `create_error`    |   `App::admin`   |     `(string) $slug, (array) $_POST`     |  `1.0.0` |
|   `delete_success`   |   `App::admin`   |         `(string) $custom`         |  `1.0.0` |
|    `delete_error`    |   `App::admin`   |         `(string) $action`         |  `1.0.0` |
|      `dashboard`     |   `App::render`  |                                    |  `1.0.0` |
|       `render`       |   `App::render`  |                                    |  `1.0.0` |
|        `admin`       |   `App::render`  |                                    |  `1.0.0` |
|         `home`       |   `App::render`  |                                    |  `1.0.0` |
|     `{PAGE_TYPE}`    |   `App::render`  |                                    |  `1.0.0` |
|         `404`        |   `App::render`  |                                    |  `1.0.0` |
|      `rendered`      |   `App::render`  |                                    |  `1.0.0` |


## Admin theme

|       Action      |      Execute in     |  Parameters  |  Since  |
| :---------------: | :-----------------: | :----------: | :-----: |
|    `admin_head`   |   `app/layout.php`  |              | `1.0.0` |
|     `admin_top`   |   `app/layout.php`  |              | `1.0.0` |
|     `admin_nav`   |   `app/layout.php`  |              | `1.0.0` |
|  `admin_middle`   |   `app/layout.php`  |              | `1.0.0` |
|    `{PAGE}_top`   |   `app/layout.php`  |              | `1.0.0` |
|    '{PAGE}_end`   |   `app/layout.php`  |              | `1.0.0` |
|     `admin_end`   |   `app/layout.php`  |              | `1.0.0` |




