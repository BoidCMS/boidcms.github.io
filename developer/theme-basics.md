# Theme Basics
All themes reside in the `themes` folder, And they have a predefined structure.


## Folder and Files Structure
This is the folder and the most required files structure for themes.

```bash
themes/
└── {THEME_NAME}/
    ├── lang/
    │   └── en.json
    ├── data.json
    ├── home.php
    ├── page.php
    ├── post.php
    └── static.php
```

## Name and Description
The translated name, description, and data of the theme is stored in the `lang/en.json` JSON file.

```json
{
    "{THEME_NAME}": {
        "name": "Theme name",
        "description": "To change the appearance of your site."
    }
}
```

## Information
The basic information about the theme is stored in the `data.json` JSON file.

```json
{
    "name": "Theme Name",
    "email": "shoaiybsysa@gmail.com",
    "author": "Shoaiyb Sysa",
    "website": "https:\/\/boidcms.github.io",
    "compatible": "1.0.0",
    "license": "GPLV3",
    "version": "1.0.0",
    "active": false,
    "notes": "Theme notes <b>could be html<\/b> (To be displayed to the admin)",
    "repo": "@shoaiyb/theme-boilerplate"
}
```


