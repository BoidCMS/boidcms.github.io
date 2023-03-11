# Theme tags

## Site
The following values are retrieved from the `site` key in the database. See [database structure](/database).

### Language code
This is the language code for the main language of the website, which is used in the HTML `lang` attribute. 

```php
<?php echo $App->get( 'lang' ) ?>
```

### Title
The name of the website.

```php
<?php echo $App->get( 'title' ) ?>
```

### Keywords
This is the SEO keywords intended for the homepage of the website.

```php
<?php echo $App->get( 'keywords' ) ?>
```

### Subtitle
The subtitle or slogan of the website.

```php
<?php echo $App->get( 'subtitle' ) ?>
```

### Description
The homepage description of the website.

```php
<?php echo $App->get( 'descr' ) ?>
```

### URL
The website's host URL.

```php
<?php echo $App->get( 'url' ) ?>
```

### Email
The email address of the website's administrator.

```php
<?php echo $App->get( 'email' ) ?>
```

### Username
The security username used to access the website's admin panel.

```php
<?php echo $App->get( 'username' ) ?>
```

### Password
The encoded character combination utilized for securing the admin panel.

```php
<?php echo $App->get( 'password' ) ?>
```

### Footer
The website's footer could be copyright, HTML or combination of both.

```php
<?php echo $App->get( 'footer' ) ?>
```

### Theme
The name of the currently installed theme.

```php
<?php echo $App->get( 'theme' ) ?>
```

### Admin URL
The customized URL for the admin login page.

```php
<?php echo $App->get( 'admin' ) ?>
```


## Page
The values below are retrieved from every page in the database, irrespective of its type.

### Type
The page type.

```php
<?php echo $App->page( 'type' ) ?>
```

### Title
The name of the page.

```php
<?php echo $App->page( 'title' ) ?>
```

### Description
The description of the page.

```php
<?php echo $App->page( 'descr' ) ?>
```

### Keywords
The SEO keywords of the page.

```php
<?php echo $App->page( 'keywords' ) ?>
```

### Content
The HTML body of the page.

```php
<?php echo $App->page( 'content' ) ?>
```

### Thumbnail
The thumbnail of the page.

```php
<?php echo $App->page( 'thumb' ) ?>
```

### Publish
The page's status: whether it has been published or not.

```php
<?php $App->page( 'pub' ) ?>
```





