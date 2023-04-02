# API
The BoidCMS API plugin streamlines integration between BoidCMS and other systems. By making HTTP requests, you can easily retrieve or update data from the database without needing to access the admin panel. Whether you're building a custom front-end, integrating with a third-party service, or automating your workflow, the BoidCMS API plugin simplifies the process.  


## Install
Download the zip file of the plugin on this [repo](https://github.com/BoidCMS/api).     
Follow this [steps](plugins/) to install.


## Developer

### Requests

To make an API request to BoidCMS, use the following URL format:

```plain
{protocol}://{domain}/api/v{version}/{endpoint}
```

To customize the URL, replace the placeholder values with your website's specific information. For example, replace `{protocol}` with "http" or "https" depending on your website's configuration, and replace `{domain}` with your website's domain name. Also, replace `{version}` with the API version you plan to use and `{endpoint}` with the specific endpoint you want to access.   

Example: 
```plain
http://api.example.com/api/v1/settings/
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

|         Action       |     Execute in    |     Parameters     |   Since   |
| :------------------: | :---------------: | :----------------: | :-------: |
|    `delete_media`    |    `api_medias`   | `(string) $media`  |  `0.1.0`  |
|     `delete_page`    |     `api_pages`   |  `(string) $page`  |  `0.1.0`  |
|       `setting`      |   `App::admin`    |                    |  `0.1.0`  |
|        `render`      |   `App::render`   |                    |  `0.1.0`  |


