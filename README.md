Drupal Drush
===

## A Codeception module for running drupal drush commands.

_Drupal Drush_ is a [Codeception module](http://codeception.com/addons) for running drush commands on [Drupal](https://www.drupal.org/) sites.

It also allows the use of the following statements in tests:

```php
// Execute "drush cc all"
$I->getDrush("cc", array("all"))->mustRun();
```

## Install with Composer

```json
{
    "require": {
        "codeception/codeception": "~2.0.0",
        "ixis/codeception-drupal-drush": "~0.1"
    }
}
```

Drupal Drush minimally requires Codeception 2.0.* and PHP 5.4

## Example suite configuration

```yaml
class_name: AcceptanceTester
modules:
    enabled:
        - PhpBrowser
        - AcceptanceHelper
        - DrupalDrush
    config:
        PhpBrowser:
            url: 'http://localhost/myapp/'
        DrupalDrush:
            drush-alias: '@mysite.local' # The Drush alias to use (required).
```

### Required configuration

* `drush-alias` is required.
