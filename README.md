# Buildotter Maker Standalone

[![Tests](https://github.com/buildotter/php-maker-standalone-src/actions/workflows/tests.yml/badge.svg?branch=main)](https://github.com/buildotter/php-maker-standalone-src/actions?workflow=tests)
[![License](https://img.shields.io/github/license/buildotter/php-maker-standalone)](/LICENSE)
[![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/buildotter/php-maker-standalone)](https://github.com/buildotter/php-maker-standalone/releases/latest)
[![Conventional Commits](https://img.shields.io/badge/Conventional%20Commits-1.0.0-blue.svg?style=flat)](https://conventionalcommits.org)

Generate test data builder based on [Buildotter Core](https://github.com/buildotter/php-core).

This "standalone maker" tries to be agnostic of the framework you are using or not.

If you want to know more about Buildotter, check [Buildotter Core](https://github.com/buildotter/php-core).

## Installation

```bash
composer require --dev buildotter/php-maker-standalone
```

## Usage

To generate a builder and the functions following [Buildotter Core](https://github.com/buildotter/php-core), let yourself be carried by the interactive command:

```bash
php vendor/bin/buildotter-maker-standalone
```

You'll have some editing to do after the generation.

> Note that the generated code may not comply with your project's coding standards.
> We work on the assumption that you have a tool that fixes the code style automatically.

## The default behavior is opinionated.

For instance, we like to use functions like `anElephant()` instead of `ElephantBuilder::random()`
or `someElephants()` instead of `RandomMultiple::from(ElephantBuilder::class, $numberOfItems)`.
So default behavior is to generate these functions.
Disable the data builders' functions generation by using `--no-generated-functions` option.

Another example is the presence of the global function `random()` using [fakerphp/faker](https://github.com/FakerPHP/Faker).
Default behavior is to generate this function if it does not already exist.
Disable the "random" function's generation by using the `--no-generated-random-function` option.

To check all the options check the help:

```bash
php vendor/bin/buildotter-maker-standalone --help
```

## Contributing

Contribution mainly happens on the source code repository at https://github.com/buildotter/php-maker-standalone-src.

[Issues](https://github.com/buildotter/php-maker-standalone-src/issues) are tracked there.

This repository contains only the phar distribution.

Still, you may contribute here with the documentation for instance!
