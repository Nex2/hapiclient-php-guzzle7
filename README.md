# HAPI Client

An HTTP Client implementing the [HAL specification](https://tools.ietf.org/html/draft-kelly-json-hal-07).

## Requirements

- PHP 7.2 or higher
- Guzzle 7.x

## Installation

Using [Composer](https://getcomposer.org/):

```json
{
    "require": {
        "nex2/hapiclient-php-guzzle7": "^1.0.1"
    }
}
```

If you are not familiar with Composer, you can download a pre-built release from the original project:
https://github.com/SlimPay/hapiclient-php-guzzle7/releases

## About this fork

This fork is based on the original `slimpay/hapiclient-guzzle7` package.

The original package uses the deprecated function:

```php
GuzzleHttp\Psr7\stream_for()
```

This function was removed in `guzzlehttp/psr7` version 2.x, which is now required by recent versions of Guzzle 7.

This fork replaces deprecated calls with:

```php
GuzzleHttp\Psr7\Utils::streamFor()
```

allowing full compatibility with:

- `guzzlehttp/guzzle` 7.10+
- `guzzlehttp/psr7` 2.x
- modern Composer dependency trees

## Why this fork exists

Projects using recent versions of Guzzle may encounter the following error with the original package:

```txt
Fatal error: Uncaught Error:
Call to undefined function GuzzleHttp\Psr7\stream_for()
```

This fork fixes the compatibility issue while keeping the original API behavior unchanged.

## Original package

Original repository:
https://github.com/SlimPay/hapiclient-php-guzzle7

## Guzzle < 7

If you need compatibility with older PHP or older Guzzle versions, please use the previous HAPI Client:
https://github.com/SlimPay/hapiclient-php

## Use

Examples and full working snippets are available in the [HAPI Browser](https://dev.slimpay.com/hapi/browser).
