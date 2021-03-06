# bpluser
An user registration, authentication and authorization module for ZF3 based on [saeven/zf3-circlical-user](https://github.com/Saeven/zf3-circlical-user/)

# Features
* User Registration
* Forgot password feature
* View helpers
* Zend Developers Toolbar extention

# Requirements
* [php: ^7.0.0](https://secure.php.net/)
* [zendframework/zend-captcha: ^2.6](https://github.com/zendframework/zend-captcha)
* [zendframework/zend-text: ^2.6](https://github.com/zendframework/zend-text)
* [zendframework/zend-filter: ^2.7](https://github.com/zendframework/zend-filter)
* [zendframework/zend-i18n: ^2.7](https://github.com/zendframework/zend-i18n)
* [phpmailer/phpmailer: ^5.2](https://github.com/PHPMailer/PHPMailer)
* [saeven/zf3-circlical-user: ^0.2.1](https://github.com/Saeven/zf3-circlical-user/)
    
# Installation
* Run following from project root directory 
```bash
    $ composer require bishwopl/bpluser
```
* Enable module in application.config.php
```php
<?php
return [
    'modules' => [
        // ...
        'CirclicalUser',
        'BplUser',
    ],
    // ...
];
```
* Follow configuration step
* Create database using following command 
```bash
    ./vendor/doctrine/doctrine-module/bin/doctrine-module orm:schema-tool:create
```
# Configuration

### bishwopl/bpluser & saeven/zf3-circlical-user
Copy [config/bpluser.local.php.dist](https://github.com/bishwopl/bpluser/blob/master/config/bpluser.local.php.dist) file to your configuration folder and remove .dist from its name. Module configuration required for [saeven/zf3-circlical-user](https://github.com/Saeven/zf3-circlical-user/) is also included in this config file so separate configuration for [saeven/zf3-circlical-user](https://github.com/Saeven/zf3-circlical-user/) is not necessary.

# Options

# Controller plugins
* Change Password
```php
    $this->bpluser()->changePassword(UserInterface $user, $newPassword);
```
* Change Email
```php
    $this->bpluser()->changeEmail(UserInterface $user, $newEmail);
```
* Is Email in use
```php
    $this->bpluser()->isEmailInUse($email);
```
* Verify password
```php
    $this->bpluser()->verifyPassword(UserInterface $user, $password);
```
* Save Profile
```php
    $this->bpluser()->saveProfile(UserInterface $user);
```
* Can access action
```php
    $this->bpluser()->isAllowedAction($controllerName, $action);
```
# To do 
* Add Remember Me feature
