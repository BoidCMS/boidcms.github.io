## Installation from zip file
- Download the latest version from the [official repo](https://github.com/BoidCMS/BoidCMS).
- Extract the zip file.
- Upload the extracted content to your server or hosting. You can upload the files in the root directory, or in a subdirectory such as `/site/`.
- To upload the files, use an FTP client, WebFTP, or some tool provided by your hosting company.
- Visit your domain. If you uploaded the files in the root directory go to `http://example.com`, if you uploaded the files in a subdirectory `http://example.com/site/`.
- Follow the admin page to configure your new website.

## Default credentials
The default admin login page is `admin`, append `admin` at the end of your site URL to get to the login page. Eg, `http://example.com/admin`, or if your site is in a subdirectory `http://example.com/site/admin`.     
While the default username and password are `admin` and `password` respectively, **Changing the login details is highly encouraged** for additional security.

## PHP Built-In web server
You can run BoidCMS quickly via the command line with the PHP Built-in web server and the plugin [Localhost](https://github.com/BoidCMS/localhost).

```bash
git clone https://github.com/BoidCMS/BoidCMS boidcms
cd boidcms
php -S localhost:8080
```
