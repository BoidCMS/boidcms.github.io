<!--
---
title: Getting Started
date: 2021-09-15 00:42:34 -0700
slug: install
---
-->
## Installation from zip file
- Download the latest version from the official repo.
- Extract the zip file.
- Upload the extracted content to your server or hosting. You can upload the files in the root directory, or in a subdirectory such as /site/.
- If you uploaded it in a subdirectory you have to edit config.php file and change url to something like http://example.com/site/.
- To upload the files, use an FTP client, WebFTP, or some tool provided by your hosting company.
- Visit your domain. If you uploaded the files in the root directory go to http://example.com, if you uploaded the files in a subdirectory http://example.com/site/.
- Follow the admin page to configure your new website.


## PHP Built-In web server
You can run BoidCMS quickly via the command line with the PHP Built-in web server.

```bash
git clone https://github.com/BoidCMS/BoidCMS boidcms
cd boidcms
php -S localhost:8080
```
