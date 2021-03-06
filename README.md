# Laravel Meta

[![Latest Version on Packagist](https://img.shields.io/packagist/v/appstract/laravel-meta.svg?style=flat-square)](https://packagist.org/packages/appstract/laravel-meta)
[![Total Downloads](https://img.shields.io/packagist/dt/appstract/laravel-meta.svg?style=flat-square)](https://packagist.org/packages/appstract/laravel-meta)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)
[![Build Status](https://img.shields.io/travis/appstract/laravel-meta/master.svg?style=flat-square)](https://travis-ci.org/appstract/laravel-meta)

Metadata for your Eloquent model

## Installation

You can install the package via composer:

```bash
composer require appstract/laravel-meta
```

### Provider

Then add the ServiceProvider to your `config/app.php` file:

```php
'providers' => [
    ...

    Appstract\Meta\MetaServiceProvider::class

    ...
]
```

### Publish, migrate

By running `php artisan vendor:publish --provider="Appstract\Meta\MetaServiceProvider"` in your project all files for this package will be published. For this package, it's only a migration. Run `php artisan migrate` to migrate the table. There will now be an `meta` table in your database.

## Usage

You can easily add Meta to an Eloquent model. Just add this to your model:

```php
use Appstract\Meta\Metable;

class Book extends Model
{
    use Metable;
}
```

Then you can get, add, update and delete meta to the model.

```php
$book = Book::find(1);

$book->addMeta('someKey', 'someValue');

$book->getMeta('someKey');

$book->updateMeta('someKey', 'anotherValue');

$book->deleteMeta('someKey');

$book->getAllMeta();

$book->deleteAllMeta();
```

## Testing

```bash
$ composer test
```

## Contributing

Contributions are welcome, [thanks to y'all](https://github.com/appstract/laravel-meta/graphs/contributors) :)

## About Appstract

Appstract is a small team from The Netherlands. <3 Laravel, Vue and other awesome tools.

## Buy Us A Beer

Would be awesome if you would [buy us a beer](https://www.paypal.me/teamappstract/10)! Or [a lot of beer](https://www.patreon.com/appstract) :)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
