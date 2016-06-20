# Laravel Firebase Sync
## Synchronize your Eloquent models with the Firebase realtime database

![image](http://img.shields.io/packagist/v/mpociot/laravel-firebase-sync.svg?style=flat)
![image](http://img.shields.io/packagist/l/mpociot/laravel-firebase-sync.svg?style=flat)
[![codecov.io](https://codecov.io/github/mpociot/laravel-firebase-sync/coverage.svg?branch=master)](https://codecov.io/github/mpociot/captainhook?branch=master)
[![Build Status](https://travis-ci.org/mpociot/laravel-firebase-sync.svg?branch=master)](https://travis-ci.org/mpociot/captainhook)

## Contents

- [Installation](#installation)
- [Usage](#usage)
- [License](#license)

<a name="installation" />
## Installation

In order to add Laravel Firebase Sync to your project, just add

    "mpociot/laravel-firebase-sync": "~1.0"

to your composer.json. Then run `composer install` or `composer update`.

Or run `composer require mpociot/laravel-firebase-sync ` if you prefer that.


<a name="usage" />
## Usage

### Configuration

This package requires you to add the following section to your `config/services.php` file:

```php
'firebase' => [
    'secret' => 'your-database-secret',
    'database_url' => 'https://your-database-at.firebaseio.com',
]
```

### Synchronizing models

To synchronize your Eloquent models with the Firebase realtime database, simply let the models that you want to synchronize with Firebase use the `Mpociot\Firebase\SyncsWithFirebase` trait.

```php
use Mpociot\Firebase\SyncsWithFirebase;

class User extends Model {

    use SyncsWithFirebase;

}
```

The data that will be synchronized is the array representation of your model. That means that you can modify the data using the existing Eloquent model attributes like `visible`, `hidden` or `appends`.

<a name="license" />
## License

Laravel Firebase Sync is free software distributed under the terms of the MIT license.