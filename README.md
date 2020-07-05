# Laravel style rules for PHP-CS-Fixer

These are the rules applied across all our projects.

## Installation

You can install using [composer](https://getcomposer.org/) from [Packagist](https://packagist.org/packages/bitvalencia/laravel-style-rules).

```
composer require bitvalencia/laravel-style-rules --dev
```

## Usage

In your `.php_cs` config file

```php
<?php

// specify the paths to fix

$finder = PhpCsFixer\Finder::create()
    ->notPath('bootstrap/*')
    ->notPath('storage/*')
    ->notPath('vendor')
    ->in([
        __DIR__ . '/app',
        __DIR__ . '/tests',
        __DIR__ . '/database',
    ])
    ->name('*.php')
    ->notName('*.blade.php')
    ->ignoreDotFiles(true)
    ->ignoreVCS(true);


// then call and return the following style function

return BitValencia\style_rules($finder);
```

## Running

Running the command

```sh
./vendor/bin/php-cs-fixer fix
```

Running in CI

```sh
./vendor/bin/php-cs-fixer fix --dry-run
```

## Resources

- Sharing PHP-CS-Fixer rules across projects and teams. [Laravel News Article](https://laravel-news.com/sharing-php-cs-fixer-rules-across-projects-and-teams)
- Laravel Shift Recommended Coding Ruleset. [Gist](https://gist.github.com/laravel-shift/cab527923ed2a109dda047b97d53c200) - [Shift](https://laravelshift.com/)

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
