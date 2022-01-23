Plugins in BoidCMS reside in the `plugins` folder, and they have a predefined structure.     
Each plugin is an object in BoidCMS, with differents hooks/events (methods).

## Folder and Files Structure

```txt
plugins/
  {PLUGIN_NAME}/
    lang/
      en.json
      ...
    data.json
    {PLUGIN_NAME}.php
```

## Information

### Data
The data and information of the plugin is located in the `data.json` JSON file.

```json
{
    "name": "Plugin Name",
    "email": "boidcms@gmail.com",
    "author": "Shoaiyb Sysa",
    "website": "https:\/\/boidcms.github.io",
    "compatible": "1.0.0",
    "license": "GPLV3",
    "version": "1.0.0",
    "class": "PluginClass",
    "active": false,
    "notes": "Plugin notes <b>could be html<\/b> (To be displayed to the admin)",
    "repo": "@shoaiyb/plugin-boilerplate"
}
```

### Langs

```json
{
    "boilerplate": {
        "debug": "Plugin <b>Boilerplate<\/b> is installed."
    }
}
```

## Plugin Class
The Boilerplate plugin code below needs to be in the `boilerplate.php` file because `main` key isn't set at the data file.

```php
<?php
/**
 *
 * Plugin boilerplate
 *
 * @package SysaCMS
 * @subpackage Plugin_Boilerplate
 * @author Shoaiyb Sysa
 * @license GPLV3
 * @version 1.0
*/
class PluginClass extends App {
  /**
   * Debugging
   * @return string
  */
  public function debug() {
    return $this->get_lang('boilerplate->debug');
  }
}
?>
```
