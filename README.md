# machinateur/imagickompare

A little PHP function that can compare PDFs and images using the Imagick PHP extension.

## Requirements

- At least PHP `>=7.4` is required
  - Extension `ext-imagick` is required

## Installation

```bash
composer require machinateur/imagickompare
```

## Usage

```php
<?php

require_once __DIR__ . '/vendor/autoload.php';

// simply compare two files (pdf, png, etc.)
$diffPercentage = \compare_with_imagick('/path/to/control-file', '/path/to/compare-file');
// or define a resolution
$diffPercentage = \compare_with_imagick('/path/to/control-file', '/path/to/compare-file', [100, 100]);
// and define a fuzziness for diff metrics
$diffPercentage = \compare_with_imagick('/path/to/control-file', '/path/to/compare-file', fuzziness: 5);
// the merged file can be saved as well, when passing an open file handle
$diffPercentage = \compare_with_imagick('/path/to/control-file', '/path/to/compare-file', fh: $fh = \fopen('php://temp'));
```

## License

It's MIT.
