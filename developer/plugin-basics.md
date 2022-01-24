# Plugin Basics
Plugins in BoidCMS reside in the `plugins` folder, and they have a predefined structure.


## Folder and Files Structure

```bash
plugins/
└── {PLUGIN_NAME}/
    ├── lang/
    │   ├── en.json
    │   └── es.json
    ├── data.json
    └── {PLUGIN_NAME}.php
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

### Languages
Each plugin should have a folder `lang`, Inside this folder you can create many different language files for each language.

#### English
`en.json`
```json
{
    "boilerplate": {
        "debug": "The plugin <b>Boilerplate<\/b> is installed."
    }
}
```

#### Spanish
`es.json`
```json
{
    "boilerplate": {
        "debug": "El complemento <b>Boilerplate<\/b> está instalado."
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
