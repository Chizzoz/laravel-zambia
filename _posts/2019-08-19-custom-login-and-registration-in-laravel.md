---
layout: post
published: false
title: Custom Login and Registration In Laravel Part 1
---
## Custom Login and Registration In Laravel

In this first part we are going to learn how to create Custom Login and Registration In Laravel.

## Technical Requirements
For this tutorial we’ll assume you already know or have the following:

- A Terminal (Command Line)
- Composer installed
- Are familiar with PHP
- Are familiar with Laravel (5+)
- You have an existing Laravel (5+) project
- You need to have Xampp or wamp installed [Download Xampp From here.](https://www.apachefriends.org/download.html)

Just in case you don’t have a Laravel project setup, this guide will help you to [create a new Laravel project locally.](https://laravel.com/docs/5.7#installing-laravel)

Now lets dive into our project. Am sure you have created your laravel project.

### Step 1

We are going to create our database  ```demologin``` am sure you are familier with xampp and phpmyadmin.

### Step 2

We are going to configur our ```.env``` to connect to the database ``.env`` is found in your Laravel Project.

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=demologin
DB_USERNAME=root
DB_PASSWORD=
```

## Step 3

in your laravel project Nervigate to ``` app > Providers ``` and open ``AppServiceProvider.php`` now past this in there

```php
<?php

namespace App\Providers;

use Illuminate\Support\ServiceProvider;
use Illuminate\Support\Facades\Schema;

class AppServiceProvider extends ServiceProvider
{
    /**
     * Register any application services.
     *
     * @return void
     */
    public function register()
    {
        //
    }

    /**
     * Bootstrap any application services.
     *
     * @return void
     */
    public function boot()
    {
        //
        Schema::defaultStringLength(191);
    }
}

```
### Step 4

In this step we are going to create the Auth system using ``artisan`` we will use our terminal to add that.
in your serminal nervigate to your project folder and type ``php artisan make:auth``

```console
$ cd blog
$ blog> php artisan make:auth
```
When its done nervigate to `` Resources > Views `` you will see that a new folder was created and contains some files in it. 

