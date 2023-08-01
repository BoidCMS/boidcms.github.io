# Database Default Structure
Below is an example of a formatted JSON representation of a newly created database:

```json
{
    "site": {
        "lang": "en",
        "title": "BoidCMS",
        "keywords": "BoidCMS, Keywords, for, seo",
        "subtitle": "Simple, fast, super extensible.",
        "descr": "Flat file CMS for building simple websites and blogs.",
        "url": "http:\/\/example.com\/",
        "email": "mail@example.com",
        "username": "admin",
        "password": "$2y$10$...",
        "footer": "Copyright &copy; 1970",
        "theme": "nimble",
        "admin": "admin",
        "blog": false
    },
    "pages": {
        "404": {
            "type": "page",
            "title": "Not Found",
            "descr": "404 Page Not Found",
            "keywords": "404",
            "content": "<p style="text-align:center">It looks like nothing was found at this location.<\/p>",
            "thumb": "",
            "date": "",
            "tpl": "",
            "pub": false
        },
        "home": {
            "type": "page",
            "title": "Home",
            "descr": "Setup your new site",
            "keywords": "BoidCMS, keywords, for, seo",
            "content": "<h2>Edit This Page<\/h2><p>Visit the <a href=\".\/admin\">admin panel<\/a> and login if not already, then Navigate to <b>Update<\/b> select <b>Home (home)<\/b> and click <b>Select<\/b>, Update the fields you want to change and click <b>Update<\/b> to save the changes.<\/p><h2>Enable Blog<\/h2><p>Navigate to <b>Settings<\/b> scroll to <b>Enable Blog<\/b> and select <b>Yes<\/b> then click <b>Save changes<\/b>.<\/p><h2>More Info<\/h2><p>You can find more information on how to setup your site in the <a href=\"https:\/\/boidcms.github.io\" target=\"_blank\" rel=\"nofollow\">documentation<\/a>.<\/p>",
            "thumb": "",
            "date": "",
            "tpl": "",
            "pub": true
        },
        "hello-world": {
            "type": "post",
            "title": "Welcome to BoidCMS!",
            "descr": "Welcome to your new website",
            "keywords": "BoidCMS, Keywords, for, seo",
            "content": "<h1>Welcome to BoidCMS!<\/h1><p>This is a sample post, login now to edit or delete it.<\/p><p>Have fun! :)<\/p>",
            "thumb": "",
            "date": "1970-01-01T00:00:00",
            "tpl": "",
            "pub": true
        }
    },
    "installed": {}
}
```

The database is composed of three tables: `site` for storing site configurations (settings), `pages` for storing all types of pages, and `installed` for keeping track of the installed plugins.


