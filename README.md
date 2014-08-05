# PHP Code Sniffer

PHP_CodeSniffer is a PHP5 script that tokenises PHP files to detect violations of a defined coding standard. It is an essential development tool that ensures your code remains clean and consistent. It can also help prevent some common semantic errors made by developers.

This is a custom phpcs standard for BIGBANK. The primary use case is in tandem with PhpStorm as an automated inspection.

## Installing

* Clone the repository
* Install Composer dependencies: `composer install`

You should now be able to run phpcs from the command line:

```
$ vendor/bin/phpcs --standard=src/CodeSniffer/Standards/Bigbank <target-file>
```

### PhpStorm Integration

* Set the path to the phpcs executable: *File -> Settings -> PHP -> Code Sniffer*. Set it to *<this-repo>/vendor/bin/phpcs*
* Activate the phpcs inspection (per project): *File -> Settings -> Inspections -> PHP -> PHP Code Sniffer validation*. Tick the checkbox to activate the inspection. Set the coding standard as Custom and select the standard directory: *<this-repo>/src/CodeSniffer/Standards/Bigbank*.

PhpStorm will now automatically inspect your code and highlight the lines where errors are found. You can also run inspections on custom scopes by using *Code -> Inspect Code*.

## Example Usage From The CLI

```bash
➜  middleware git:(develop) ✗ pwd
/var/www/api/middleware
➜  middleware git:(develop) ✗ /home/ando/Projects/phpcs/vendor/bin/phpcs --standard=/home/ando/Projects/phpcs/src/CodeSniffer/Standards/Bigbank -s --report=full Middleware
```

Default script output format will be as follows:

```
FILE: ...middleware/library/BB/API/Middleware/Version/v1/Controller/Defaultc.php
--------------------------------------------------------------------------------
FOUND 3 ERROR(S) AFFECTING 2 LINE(S)
--------------------------------------------------------------------------------
 36 | ERROR | Arguments with default values must be at the end of the argument
    |       | list (PEAR.Functions.ValidDefaultValue.NotAtEnd)
 41 | ERROR | Expected 1 newline at end of file; 0 found
    |       | (PSR2.Files.EndFileNewline.NoneFound)
 41 | ERROR | The closing brace for the class must go on the next line after
    |       | the body (PSR2.Classes.ClassDeclaration.CloseBraceAfterBody)
--------------------------------------------------------------------------------
```

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