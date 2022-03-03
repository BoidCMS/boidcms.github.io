# Api
The BoidCMS API plugin is designed to provide an easy way to integrate other systems with BoidCMS powered sites.      
With this plugin, you can retrieve or update data from the database with a simple HTTP request.


## Install
Download the zip file of the plugin on this [repo](https://github.com/BoidCMS/Api).     
Follow this [steps](plugins/) to install.

## Developer

### Requests
The api request uri is: `{protocol}://{domain}/api/{endpoint}`.    
Eg, `http://example.com/api/settings`

|     Endpoint    |  Method  |
| :-------------: | :------: |
| `/api/settings` |   `GET`  |
| `/api/settings` |   `PUT`  |
|  `/api/medias`  |   `GET`  |
|  `/api/medias`  |  `POST`  |
|  `/api/medias`  | `DELETE` |
|   `/api/langs`  |   `GET`  |
|   `/api/pages`  |   `GET`  |
|   `/api/pages`  |   `PUT`  |
|   `/api/pages`  |  `POST`  |
|   `/api/pages`  | `DELETE` |

### Response
The response content format is `JSON`.

Default return values.     
|    Key    |   Type  |
| :-------: | :-----: |
|   `code`  |  `int`  |
|  `success`| `string`|
|  `message`| `string`|
|  `result` | `array` |
|   `error` | `array` |


### Used hooks/events

|       Hook/Event     |    Execute in   |   Parameters    |   Since   |
| :------------------: | :-------------: | :-------------: | :-------: |
|    `api_configure`   |`edit_plugin.php`|                 |  `1.0.0`  |
| `before_render_func` |  `App::render`  |                 |  `1.0.0`  |

### Created hooks/events

|     Hook/Event      |    Execute in   |    Parameters  | Since |
| :-----------------: | :-------------: | :------------: | :---: |
| `on_api_page_delete`| `Api::api_pages`|`(string) $page`|`1.0.0`|
|`on_api_media_delete`|`Api::api_medias`|`(string) $file`|`1.0.0`|
