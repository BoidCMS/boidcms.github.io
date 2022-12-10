# Folder Structure

```plain
app/
data/
media/
plugins/
themes/
```

## `app/`
This is the BoidCMS's main folder, which stores core file and admin view. You should not edit any files in this folder; instead, write [custom plugins](/developer/plugin-api) or add to the current theme a `functions.php` file.

## `data/`
This folder is created during the first time visit to the website, used to store the database file and debug log file. **The folder is protected** by default; developers should use this folder for storing data.

## `media/`
This folder is created during the first time visit to the website, and it's used to store uploaded media files.        

## `plugins/`
All the plugins are stored inside this folder.

## `themes/`
All the themes are stored inside this folder.

