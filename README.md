# Ghostscript PHP

Yet another Ghostscript PHP wrapper for converting PDFs to images. This library passes strings to and from stdin and stdout rather than using input and output files.

## Installation

```
composer require robgridley/ghostscript:dev-master
```

## Usage Example

```php
use RobGridley\Ghostscript\Devices;
use RobGridley\Ghostscript\Ghostscript;

$device = new Devices\Png24;
$device->setDownScaleFactor(2);

$gs = new Ghostscript($device);
$gs->setPageBox('trim');
$gs->setResolution(144);

$pdf = file_get_contents('test.pdf');
$image = $gs->convert($pdf);
```