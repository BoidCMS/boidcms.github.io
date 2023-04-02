## Installing BoidCMS from a zip file

- Get the latest version of BoidCMS from the [official repository](https://github.com/BoidCMS/BoidCMS).
- Extract the zip file and upload the contents to your server. You can upload the files to the root directory or to a subdirectory of your choice.
- Navigate to your domain. If you uploaded the files to the root directory, go to `http://example.com`. If you uploaded the files to a subdirectory, go to `http://example.com/{subdirectory}`.
- Use the admin panel to set up and customize your website.

## Default Login Credentials
The default login page for the administrator is located at `admin`. To access the login page, simply append `/admin` to the end of your website's URL. For example, if your site's URL is `http://example.com`, then the login page would be located at `http://example.com/admin`. If your website is located in a subdirectory, then you will need to include the subdirectory name before `/admin`.  

It's important to note that the default username and password are both set to `admin` and `password`, respectively. However, to ensure your site's security, it's highly recommended that you change these login details to something more unique and complex. 

## Run BoidCMS with PHP Built-In Web Server
BoidCMS can be quickly run through the command line using PHP's built-in web server.

```bash
git clone https://github.com/BoidCMS/BoidCMS boidcms
cd boidcms
```

To prepare `index.php` for use with the PHP Built-in web server, follow these steps:

- Add the following code before the `$App->render();` method:
```php
$App->page = ltrim( $_SERVER[ 'PATH_INFO' ] ?? '', '/' );
```

- Save the changes to `index.php`.

- Start the server by running the following command in your terminal:
```bash
php -S localhost:8080
```

Once the server is running, you can access BoidCMS by opening a web browser and navigating to `http://localhost:8080` in the address bar.


