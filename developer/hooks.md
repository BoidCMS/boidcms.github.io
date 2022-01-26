# Hooks / Events
BoidCMS has a lot of hooks/events called within the core, Which makes it even more easier to be modified by [Plugins](plugins).     
And here is the list of all.

## Core

|       Hook/Event     |    Execute in   |               Parameters           |  Since |
| :------------------: | :-------------: | :--------------------------------: | :----: |
|   `before_log_func`  |      Core       |     `(string) $message, $type`     |  1.0.0 |
| `before_require_func`|      Core       |       `(string) $filename`         |  1.0.0 |
|   `on_require_func`  |      Core       |        `(string) $buffer`          |  1.0.0 |
|   `on_require_error` |      Core       |       `(string) $filename`         |  1.0.0 |
|  `before_parse_func` |      Core       |        `(string) $value`           |  1.0.0 |
|   `on_parse_nomatch` |      Core       |       `(string) $match[0]`         |  1.0.0 |
|     `on_page_func`   |      Core       |`(string) $info, $parse, $permalink`|  1.0.0 |
|      `on_get_lang`   |      Core       |         `(string) $info`           |  1.0.0 |
|  `on_installed_func` |      Core       |      `(string) $name, $type`       |  1.0.0 |
|   `on_slugify_func`  |      Core       |         `(string) $slug`           |  1.0.0 |
|  `on_redirect_func`  |      Core       |    `(string) $to, (int) $code`     |  1.0.0 |
| `before_login_func`  |      Core       |                                    |  1.0.0 |
|`on_login_token_error`|      Core       |     `(string) $_POST['token']`     |  1.0.0 |
|   `on_login_success` |      Core       |                                    |  1.0.0 |
|    `on_login_error`  |      Core       |`(string) $_POST['username'], $_POST['password']`|  1.0.0 |
| `before_logout_func` |      Core       |                                    |  1.0.0 |
|  `on_logout_success` |      Core       |                                    |  1.0.0 |
|`on_login_token_error`|      Core       |      `(string) $_POST['token']`    |  1.0.0 |
| `before_relogin_func`|      Core       |           `(bool) $force`          |  1.0.0 |
|   `on_wysiwyg_func`  |      Core       |          `(bool) $create`          |  1.0.0 |
|    `wysiwyg_top`     |      Core       |          `(bool) $create`          |  1.0.0 |
|    `wysiwyg_end`     |      Core       |          `(bool) $create`          |  1.0.0 |
| `before_plugin_func` |      Core       |                                    |  1.0.0 |
|  `before_theme_func` |      Core       |                                    |  1.0.0 |
|  `before_media_func` |      Core       |                                    |  1.0.0 |
|`before_settings_func`|      Core       |                                    |  1.0.0 |
|`before_dashboard_func`|     Core       |                                    |  1.0.0 |
| `before_create_func` |      Core       |                                    |  1.0.0 |
| `before_update_func` |      Core       |                                    |  1.0.0 |
| `before_delete_func` |      Core       |                                    |  1.0.0 |
|    `on_delete_page`  |      Core       |     `(string) $_GET['delete']`     |  1.0.0 |
|`on_page_delete_success`|    Core       |     `(string) $_GET['delete']`     |  1.0.0 |
|`on_page_delete_error`|      Core       |     `(string) $_GET['delete']`     |  1.0.0 |
|`on_page_delete_nomatch`|    Core       |     `(string) $_GET['delete']`     |  1.0.0 |
|`before_debugging_func`|     Core       |                                    |  1.0.0 | 
| `before_admin_func`  |      Core       |                                    |  1.0.0 |
|  `before_admin_404`  |      Core       |                                    |  1.0.0 |
|    `on_admin_func`   |      Core       |         `(string) $buffer`         |  1.0.0 |
| `before_render_func` |      Core       |                                    |  1.0.0 |
|     `before_home`    |      Core       |                                    |  1.0.0 |
| `before_{PAGE_TYPE}` |      Core       |                                    |  1.0.0 |
|     `before_404`     |      Core       |                                    |  1.0.0 |
|   `on_render_func`   |      Core       |         `(string) $buffer`         |  1.0.0 |


## Admin theme
|  Hook/Event  |  Execute in  |  Parameters  |  Since  |
| :----------: | :----------: | :----------: | :-----: |

