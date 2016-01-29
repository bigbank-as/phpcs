# Custom Rule Set For PHP_CodeSniffer

[PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) is a PHP script that tokenizes PHP files to detect violations of a defined coding standard. It is an essential development tool that ensures your code remains clean and consistent. It can also help prevent some common semantic errors made by developers.

This is a custom PHP_CodeSniffer standard for [Bigbank](https://bigbank.eu), based on and compatible with [PSR-2](http://www.php-fig.org/psr/psr-2).

## Installing

### Standalone

Usage by IDE-s or manually from the CLI.

* Clone the repository
* Install Composer dependencies: `composer install`

You should now be able to run `phpcs` from the command line:

```
$ vendor/bin/phpcs --standard=src/CodeSniffer/Standards/Bigbank <target-file>
```

#### PhpStorm Integration

* Set the path to the `phpcs` executable: *File -> Settings -> PHP -> Code Sniffer*. Set it to `<this-repo>/vendor/bin/phpcs`
* Activate the `phpcs` inspection (per project): *File -> Settings -> Inspections -> PHP -> PHP Code Sniffer validation*. Tick the checkbox to activate the inspection. Set the coding standard as Custom and select the standard directory: `<this-repo>/src/CodeSniffer/Standards/Bigbank`.

PhpStorm will now automatically inspect your code and highlight the lines where errors are found. You can also run inspections on custom scopes by using *Code -> Inspect Code*.

### CI Server

Usage by automated tools such as Travis or Bamboo.

* Require `bigbank/phpcs` in your `composer.json` `require-dev` section
* Configure the CI server to run `phpcs` as part of its static analysis
 
## Suppressing Warnings

You can manually mark parts of the code as ignored by phpcs with annotations.

* `@codingStandardsIgnoreStart`
* `@codingStandardsIgnoreEnd`
* `@codingStandardsIgnoreFile` - marks the entire file as ignored

## Fixing Errors Automatically

It is possible to fix some errors (for example, no empty line at the end of the file) automatically, in bulk (for dozens of files). For more, read [Fixing Errors Automatically](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Fixing-Errors-Automatically).

# Links

* [PHP Code Sniffer Documentation](https://github.com/squizlabs/PHP_CodeSniffer/wiki)
* [PhpStorm: Using PHP Code Sniffer Tool](http://www.jetbrains.com/phpstorm/webhelp/using-php-code-sniffer-tool.html)

## Change log

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## License

PHP_CodeSniffer is developed and owned by [Squiz Labs](http://www.squizlabs.com).
This custom standard is licensed under the Apache 2.0 License (Apache-2.0). Please see [License File](LICENSE.md) for more information.