# Folder Structure

```tree
app/
data/
media/
plugins/
themes/
```

## `app/`
The BoidCMS's main folder, contains essential files such as the core file and admin view. It is recommended not to modify any of the files in this directory directly. Instead, it's best to create [custom plugins](/developer/plugin-basics) or add functionality to the current theme using a `functions.php` file. This approach will ensure that the system remains stable and can be easily updated without any conflicts arising from changes made to the core files.

## `data/`
When the website is first visited, this folder is automatically created to store the database file and debug log file. **This folder is protected** by default and should be used by developers for storing data. It is important to note that modifying or deleting any files within this folder can result in errors and data loss. Therefore, it's best to exercise caution and ensure that appropriate backups are in place before making any changes.

## `media/`
When the website is visited for the first time, this folder is automatically created to store all uploaded media files. This folder is essential for storing images, videos, audio files, and other media content that admin may upload to the website.

## `plugins/`
This folder contains all the plugins that are currently uploaded on the website.

## `themes/`
This folder contains all the themes that are currently uploaded on the website.
