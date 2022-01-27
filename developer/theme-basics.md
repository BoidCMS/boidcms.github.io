# Theme Basics
All themes reside in the `themes` folder, And they have a predefined structure.


## Folder and Files Structure
This is the folder and the most required files structure for themes.     
Let's pretend the theme name is `Pure`.
```bash
themes/
└── pure/
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
    "pure": {
        "name": "Pure",
        "description": "To change the appearance of your site with pure style."
    }
}
```

## Information
The basic information about the theme is stored in the `data.json` JSON file.

```json
{
    "name": "Pure",
    "email": "boidcms@gmail.com",
    "author": "Shoaiyb Sysa",
    "website": "https:\/\/boidcms.github.io",
    "compatible": "1.0.0",
    "license": "GPLV3",
    "version": "1.0.0",
    "notes": "Theme notes <b>could be html<\/b> (To be displayed to the admin)",
    "repo": "@github/repo"
}
```


