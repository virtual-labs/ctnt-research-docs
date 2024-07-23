# Usage of Rector Tool for PHP Code Refactoring

This document provides comprehensive instructions on the usage of Rector, a tool used for automated refactoring of PHP code specifically for upgrading PHP code from version 4 to version 8.

## Table of Contents

- [Usage of Rector Tool for PHP Code Refactoring](#usage-of-rector-tool-for-php-code-refactoring)
  - [Table of Contents](#table-of-contents)
  - [Need for Rector](#need-for-rector)
  - [Installation and Setup](#installation-and-setup)
  - [Configuration](#configuration)
  - [Previewing Changes](#previewing-changes)
  - [Applying Changes](#applying-changes)
  - [Additional References](#additional-references)

## Need for Rector

Rector is required to automate the refactoring of PHP code, particularly for upgrading older versions of PHP code to newer versions. The process of upgrading PHP code manually can be tedious and time-consuming. Rector simplifies this task by providing predefined rules for code refactoring.
does
## Installation and Setup

**1. Composer Installation**

Ensure that composer is installed on your system.

**2. Rector Installation**

In the directory with the code to be modified, run the following setup command:

```bash
$ composer require rector/rector --dev
```

**3. Generate Rector Configuration**

Run the following command to generate the `rector.php` configuration file in the current directory:

```bash
$ vendor/bin/rector
```

## Configuration

Replace the contents of the generated `rector.php` file with the following:

```php
<?php

declare(strict_types=1);

use Rector\Config\RectorConfig;
use Rector\Set\ValueObject\LevelSetList;

return static function (RectorConfig $rectorConfig): void {
    $rectorConfig->paths([
        __DIR__ . '/build/',
    ]);

    $rectorConfig->sets([LevelSetList::UP_TO_PHP_82]);
};
```

**Path:** Specifies the relative directory where the files to be modified are located. In this case `build/`

**Level Set:** Specifies the predefined rules for upgrading PHP code to version 8.2.

## Previewing Changes

Run the following command to preview all the changes that will be made:

```bash
$ vendor/bin/rector process --dry-run
```

Correct any syntax errors that may appear during the preview.

## Applying Changes

To apply the changes to the code, run the following command:

```bash
$ vendor/bin/rector process
```

## Additional References

- GitHub: https://github.com/rectorphp/rector
- Documentation: https://getrector.com/documentation