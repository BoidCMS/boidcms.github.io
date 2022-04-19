# Plugin Basics
Plugins in BoidCMS reside in the `plugins` folder, and they have a predefined structure.


## Folder and Files Structure

```bash
plugins/
└── example/
    └── example.php
```

<!--
```bash
plugins/
└── example/
    ├── lang/
    │   ├── en.json
    │   └── es.json
    ├── data.json
    └── example.php
```


## Information


### Data
The data and information of the plugin is located in the `data.json` JSON file.

```json
{
    "name": "Example",
    "email": "boidcms@gmail.com",
    "author": "Shoaiyb Sysa",
    "website": "https:\/\/boidcms.github.io",
    "compatible": "1.0.0",
    "license": "GPLV3",
    "version": "1.0.0",
    "class": "Example",
    "active": false,
    "notes": "Plugin notes <b>could be html<\/b> (To be displayed to the admin)",
    "repo": "@shoaiyb/example"
}
```

### Languages
Each plugin is recommended to have a folder `lang`, Inside this folder you can create many different language files for each language.

#### English
`en.json`
```json
{
    "example": {
        "debug": "The plugin <b>Example<\/b> is installed."
    }
}
```

#### Spanish
`es.json`
```json
{
    "example": {
        "debug": "El complemento <b>Example<\/b> está instalado."
    }
}
```

## Plugin Class
The Example plugin code below needs to be in the `example.php` file because `main` key isn't set at the data file.

```php
<?php
/**
 *
 * Plugin example
 *
 * @package BoidCMS
 * @subpackage Plugin_Example
 * @author Shoaiyb Sysa
 * @license GPLV3
 * @version 1.0
*/
class Example extends App {
  /**
   * Debugging
   * @return string
  */
  public function debug() {
    return $this->get_lang('example->debug');
  }
}
?>
```
-->
