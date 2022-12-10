# Theme tags

## Site
The following are values from the key "site" in the database.

### Language code
This is the short name for the main language of the website used in the HTML "lang" attribute.

```php
<?php echo $App->get( 'lang' ) ?>
```

### Title
The name of the website.

```php
<?php echo $App->get( 'title' ) ?>
```

### Keywords
The SEO keywords for the website homepage.

```php
<?php echo $App->get( 'keywords' ) ?>
```

### Subtitle
The website subtitle/slogan.

```php
<?php echo $App->get( 'subtitle' ) ?>
```

### Description
The description of the website's homepage.

```php
<?php echo $App->get( 'descr' ) ?>
```

### URL
The website's host URL.

```php
<?php echo $App->get( 'url' ) ?>
```

### Email
The website's admin email address.

```php
<?php echo $App->get( 'email' ) ?>
```

### Username
The name used as a security name which is required to access the website's admin panel.

```php
<?php echo $App->get( 'username' ) ?>
```

### Password
The encoded combination of characters used as a way of securing the admin panel.

```php
<?php echo $App->get( 'password' ) ?>
```

### Footer
The website's footer could be copyright, HTML or combination of both.

```php
<?php echo $App->get( 'footer' ) ?>
```

### Theme
The name of the current installed theme.

```php
<?php echo $App->get( 'theme' ) ?>
```

### Admin URL
The user-customized admin login page URL.

```php
<?php echo $App->get( 'admin' ) ?>
```


## Page
The following are values from each page in the database, regardless of the type.

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
The status of the page, published or not.

```php
<?php $App->page( 'pub' ) ?>
```





