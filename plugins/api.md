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
|  `success`|  `bool` |
|  `message`| `string`|
|  `result` | `array` |
|   `error` | `array` |


### Used hooks/events

|       Hook/Event     |     Execute in    |     Parameters     |   Since   |
| :------------------: | :---------------: | :----------------: | :-------: |
|        `delete`      |`App::delete_media`|  `(string) $file`  |  `1.0.0`  |
|        `delete`      |`App::delete_page` |  `(string) $slug`  |  `1.0.0`  |
|       `setting`      |   `App::admin`    |                    |  `1.0.0`  |
|        `render`      |   `App::render`   |                    |  `1.0.0`  |


