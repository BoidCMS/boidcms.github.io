# API
This plugin enables API functionality on your sites, allowing you to manage your site using simple HTTP requests. With the power of APIs, you can easily control and manipulate various aspects of your site, making updates and modifications straightforward. Whether you want to retrieve data, update settings, create new pages, or perform other site management tasks, this plugin simplifies the process by leveraging the convenience of plain HTTP requests.


## Install
Download the zip file of the plugin on this [repo](https://github.com/BoidCMS/api).     
Follow this [steps](plugins/install) to install.


## Developer

### Requests

To make an API request to BoidCMS, use the following URL format:

```plain
{protocol}://{domain}/api/v{version}/{endpoint}
```

To customize the URL, replace the placeholder values with your website's specific information. For example, replace `{protocol}` with "http" or "https" depending on your website's configuration, and replace `{domain}` with your website's domain name. Also, replace `{version}` with the API version you plan to use and `{endpoint}` with the specific endpoint you want to access.   

Example: 
```plain
http://example.com/api/v1/settings
```

|       Endpoint     |  Method  |
| :----------------: | :------: |
| `/api/v1/settings` |   `GET`  |
| `/api/v1/settings` |   `PUT`  |
|  `/api/v1/medias`  |   `GET`  |
|  `/api/v1/medias`  |  `POST`  |
|  `/api/v1/medias`  | `DELETE` |
|  `/api/v1/pages`   |   `GET`  |
|  `/api/v1/pages`   |   `PUT`  |
|  `/api/v1/pages`   |  `POST`  |
|  `/api/v1/pages`   | `DELETE` |
|  `/api/v1/slugify` |   `GET`  |

### Response
The response content format is `JSON`.

Default return values.     

|    Field   |   Type  |
| :--------: | :-----: |
|   `code`   |  `int`  |
|  `success` |  `bool` |
|  `message` | `string`|
|   `data`   | `array` |


## Actions

### Used Actions

<!--
|         Action       |     Execute in    |     Parameters     |   Since   |
| :------------------: | :---------------: | :----------------: | :-------: |
|    `delete_media`    |    `api_medias`   | `(string) $media`  |  `0.1.0`  |
|     `delete_page`    |     `api_pages`   | `(string) $page`   |  `0.1.0`  |
|      `settings`      |   `App::admin`    |                    |  `0.1.0`  |
|       `render`       |   `App::render`   |                    |  `0.1.0`  |

-->
