# Hooks / Actions
BoidCMS has a lot of hooks/actions called within the core, And that makes it even more easier to be extended by [Plugins](plugins).     
And here is the list of all.

## Core

|       Hook/Event     |    Execute in    |               Parameters           |   Since  |
| :------------------: | :--------------: | :--------------------------------: | :------: |
|         `log`        |    `App::log`    |     `(string) $message, $type`     |  `1.0.0` |
|         `page`       |    `App::page`   |`(string) $info, $parse, $permalink`|  `1.0.0` |
|       `slugify`      |  `App::slugify`  |         `(string) $slug`           |  `1.0.0` |
|       `redirect`     |  `App::redirect` |    `(string) $to, (int) $code`     |  `1.0.0` |
|    `login_success`   |   `App::admin`   |                                    |  `1.0.0` |
|     `login_error`    |   `App::admin`   |`(string) $_POST['username'], $_POST['password']`|  `1.0.0` |
|   `logout_success`   |   `App::admin`   |                                    |  `1.0.0` |
|     `token_error`    |   `App::admin`   |      `(string) $_POST['token']`    |  `1.0.0` |
|    `media_upload`    |    `App::admin`  |                                    |  `1.0.0` |
|   `create_success`   |   `App::admin`  |                                    |  `1.0.0` |
|    `create_error`    |   `App::admin`  |     `(string) $_GET['delete']`     |  `1.0.0` |
|   `delete_success`   |   `App::admin`  |     `(string) $_GET['delete']`     |  `1.0.0` |
|    `delete_error`    |   `App::admin`  |     `(string) $_GET['delete']`     |  `1.0.0` |
|   `delete_nomatch`   |   `App::admin`  |     `(string) $_GET['delete']`     |  `1.0.0` |                                    |  `1.0.0` |
|     `{PAGE_TYPE}`    |   `App::render`  |                                    |  `1.0.0` |
|     `before_404`     |   `App::render`  |                                    |  `1.0.0` |
|       `render`       |   `App::render`  |         `(string) $buffer`         |  `1.0.0` |


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

