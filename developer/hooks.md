# Hooks / Events
BoidCMS has a lot of hooks/events called within the core, And that makes it even more easier to be extended by [Plugins](plugins).     
And here is the list of all.

## Core

|       Hook/Event     |    Execute in    |               Parameters           |   Since  |
| :------------------: | :--------------: | :--------------------------------: | :------: |
|   `before_log_func`  |    `App::log`    |     `(string) $message, $type`     |  `1.0.0` |
| `before_require_func`|  `App::require`  |       `(string) $filename`         |  `1.0.0` |
|   `on_require_func`  |  `App::require`  |        `(string) $buffer`          |  `1.0.0` |
|   `on_require_error` |  `App::require`  |       `(string) $filename`         |  `1.0.0` |
|  `before_parse_func` |   `App::parse`   |        `(string) $value`           |  `1.0.0` |
|   `on_parse_nomatch` |   `App::parse`   |       `(string) $match[0]`         |  `1.0.0` |
|     `on_page_func`   |    `App::page`   |`(string) $info, $parse, $permalink`|  `1.0.0` |
|      `on_get_lang`   |  `App::get_lang` |         `(string) $info`           |  `1.0.0` |
|  `on_installed_func` | `App::installed` |      `(string) $name, $type`       |  `1.0.0` |
|   `on_slugify_func`  |  `App::slugify`  |         `(string) $slug`           |  `1.0.0` |
|  `on_redirect_func`  |  `App::redirect` |    `(string) $to, (int) $code`     |  `1.0.0` |
| `before_login_func`  |    `App::login`   |                                    |  `1.0.0` |
|`on_login_token_error`|    `App::login`   |     `(string) $_POST['token']`     |  `1.0.0` |
|   `on_login_success` |    `App::login`   |                                    |  `1.0.0` |
|    `on_login_error`  |    `App::login`   |`(string) $_POST['username'], $_POST['password']`|  `1.0.0` |
| `before_logout_func` |    `App::logout`  |                                    |  `1.0.0` |
|  `on_logout_success` |    `App::logout`  |                                    |  `1.0.0` |
|`on_logout_token_error`|   `App::logout`  |      `(string) $_POST['token']`    |  `1.0.0` |
| `before_relogin_func`|    `App::relogin` |           `(bool) $force`          |  `1.0.0` |
|   `on_wysiwyg_func`  |    `App::wysiwyg` |          `(bool) $create`          |  `1.0.0` |
|    `wysiwyg_top`     |    `App::wysiwyg` |          `(bool) $create`          |  `1.0.0` |
|    `wysiwyg_end`     |    `App::wysiwyg` |          `(bool) $create`          |  `1.0.0` |
| `before_plugin_func` |    `App::plugin`  |                                    |  `1.0.0` |
|  `before_theme_func` |     `App::theme`  |                                    |  `1.0.0` |
|  `before_media_func` |     `App::media`  |                                    |  `1.0.0` |
|`before_settings_func`|   `App::settings` |                                    |  `1.0.0` |
|`before_dashboard_func`|  `App::dashboard` |                                    |  `1.0.0` |
| `before_create_func` |    `App::create`   |                                    |  `1.0.0` |
| `before_update_func` |    `App::update`   |                                    |  `1.0.0` |
| `before_delete_func` |    `App::delete`   |                                    |  `1.0.0` |
|    `on_delete_page`  |    `App::delete`   |     `(string) $_GET['delete']`     |  `1.0.0` |
|`on_page_delete_success`|  `App::delete`   |     `(string) $_GET['delete']`     |  `1.0.0` |
|`on_page_delete_error`|    `App::delete`  |     `(string) $_GET['delete']`     |  `1.0.0` |
|`on_page_delete_nomatch`|  `App::delete`   |     `(string) $_GET['delete']`     |  `1.0.0` |
|`before_debugging_func`| `App::debugging`  |                                    |  `1.0.0` | 
| `before_admin_func`  |    `App::admin`   |                                    |  `1.0.0` |
|  `before_admin_404`  |    `App::admin`   |                                    |  `1.0.0` |
|    `on_admin_func`   |    `App::admin`   |         `(string) $buffer`         |  `1.0.0` |
| `before_render_func` |   `App::render`   |                                    |  `1.0.0` |
|     `before_home`    |   `App::render`   |                                    |  `1.0.0` |
| `before_{PAGE_TYPE}` |   `App::render`   |                                    |  `1.0.0` |
|     `before_404`     |   `App::render`   |                                    |  `1.0.0` |
|   `on_render_func`   |   `App::render`   |         `(string) $buffer`         |  `1.0.0` |


## Admin theme
|     Hook/Event    |   Execute in   |  Parameters  |  Since  |
| :---------------: | :------------: | :----------: | :-----: |
|    `login_head`   |   `login.php`  |              | `1.0.0` |
|     `login_top`   |   `login.php`  |              | `1.0.0` |
|     `login_end`   |   `login.php`  |              | `1.0.0` |
|    `logout_head`  |  `logout.php`  |              | `1.0.0` |
|     `logout_top`  |  `logout.php`  |              | `1.0.0` |
|     `logout_end`  |  `logout.php`  |              | `1.0.0` |
|   `settings_head` | `settings.php` |              | `1.0.0` |
|    `settings_top` | `settings.php` |              | `1.0.0` |
|    `settings_end` | `settings.php` |              | `1.0.0` |
|  `dashboard_head` | `dashboard.php`|              | `1.0.0` |
|   `dashboard_top` | `dashboard.php`|              | `1.0.0` |
|   `dashboard_end` | `dashboard.php`|              | `1.0.0` |





