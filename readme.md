# Bigcommerce for Laravel

A wrapper package for the [Bigcommerce PHP API](https://github.com/bigcommerce/bigcommerce-api-php).

## Package Installation

Add the following line to your composer.json file:

```javascript
"kalley/laravel-bigcommerce": "dev-master"
```

or run `composer require kalley/laravel-bigcommerce:dev-master` from the command line

Add this line of code to the ```providers``` array located in your ```app/config/app.php``` file:
```php
'Kalley\LaravelBigcommerce\LaravelBigcommerceServiceProvider',
```

And this lines to the ```aliases``` array:
```php
'Bigcommerce' => 'Kalley\LaravelBigcommerce\Client',
```

### Configuration

In order to use the Bigcommerce API, publish its configuration first

```php
php artisan config:publish kalley/laravel-bigcommerce
```

Afterwards edit the file ```app/config/packages/kalley/laravel-bigcommerce/bigcommerce.php``` to suit your needs.

### Migrations

This package comes with all the migrations you need to run a full featured oauth2 server. Run:

```php
php artisan bigcommerce:migrations
```

Then you're ready to go! Look at the [Bigcommerce PHP API](https://github.com/bigcommerce/bigcommerce-api-php) for specifics on how to use the library.

## Extensions

This library extends Bigcommerce\Api\Client with the following methods:

```php
Bigcommerce::createCustomerAddress($customer_id, $object);
```

This will create an address in the customer's address book in your store. Required fields are as followed:

*   `first_name`
*   `last_name`
*   `phone`
*   `street_1`
*   `city`
*   `state`
*   `zip`
*   `country`

## Support

Bugs and feature request are tracked on [GitHub](https://github.com/kalley/laravel-bigcommerce/issues)

## License

This package is released under the MIT License.