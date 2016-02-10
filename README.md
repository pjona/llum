# llum

Speed up you laravel development workflow illuminating packages with llum:

[![asciicast](https://asciinema.org/a/bym5od3j6qtqh5liv8uwx1qy4.png)](https://asciinema.org/a/bym5od3j6qtqh5liv8uwx1qy4?speed=2&theme=solarized-dark&loop=1&autoplay=1&size=medium)

<iframe src="http://showterm.io/7b5f8d42ba021511e627e" width="640" height="480"></iframe>

[![Total Downloads](https://poser.pugx.org/acacha/llum/downloads.png)](https://packagist.org/packages/acacha/llum)
[![Latest Stable Version](https://poser.pugx.org/acacha/llum/v/stable.png)](https://packagist.org/packages/acacha/llum)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/acacha/llum/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/acacha/adminlte-laravel/?branch=master)
[![Build Status](https://scrutinizer-ci.com/g/acacha/llum/badges/build.png?b=master)](https://scrutinizer-ci.com/g/acacha/adminlte-laravel/build-status/master)

# Install notes

```bash
composer global require "acacha/llum=~0.1"
```

# Requirements

Some commands use [GNU sed](https://www.gnu.org/software/sed/)

# Commands

## Sqlite

Once you've installed a new laravel project use sqlite command to active sqlite

```bash
laravel new larapp
cd larapp
llum sqlite
File database/database.sqlite created successfully
.env file updated successfully
```
And sqlite is ready to go:
 
```bash
php artisan migrate 
Migration table created successfully.
Migrated: 2014_10_12_000000_create_users_table
Migrated: 2014_10_12_100000_create_password_resets_table
```


#Packagist

https://packagist.org/packages/acacha/admin

# Working notes

Update value in .env file with sed:

```bash
sed -i '/^MAIL_DRIVER=/s/=.*/=log/' .env
```

Comment database entries:

```bash
sed -i 's/^DB_/#DB_/g' .env
```

Add sqlite before database entries:

```bash
sed 's/.*DB_HOST.*/DB_CONNECTION=sqlite\n&/' .env
```
