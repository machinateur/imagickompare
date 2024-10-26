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

## Tests

There are no tests for this library as of now.

I have used it in two of my projects ([the-printe](https://github.com/machinateur/the-printer), [php-qpdf-ffi](https://github.com/machinateur/php-qpdf-ffi))
 to assess PDF file differences in their tests.

## License

It's MIT.
