# Folder Structure

```plain
app/
data/
media/
plugins/
themes/
```

## `app/`
This is the main folder of the BoidCMS, it stores the core file of the system and admin view.      
You should not edit any file in this folder, write custom plugin or add `functions.php` to the current theme instead.     


## `data/`
This folder is created during the first time visit to the website, it is used to store the database file `database.json` and `debug.log` file.      
This folder is protected by default, plugins can use this folder to store sensitive data.     


## `media/`
This folder is created during the first time visit to the website, it is used to store uploaded media files.        


## `plugins/`
All the plugins reside inside this folder.     


## `themes/`
All the themes should be uploaded inside this folder.



