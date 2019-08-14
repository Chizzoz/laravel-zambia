---
layout: post
published: true
title: How to Send Bulk SMS with Twilio and Laravel PHP
---
## How to Send Bulk SMS with Twilio and Laravel PHP

There are times when you have a large number of users and you need to update or notify them simultaneously via SMS. Maybe you run a membership site or personal blog. Whatever the case this tutorial will provide an efficient and easy way to achieve sending bulk SMS via your web app.

## Technical Requirements
For this tutorial we’ll assume you already know or have the following:

- A Terminal (Command Line)
- Composer installed
- Are familiar with PHP
- Are familiar with Laravel (5+)
- You have an existing Laravel (5+) project
- You have a Twilio account and your credentials ready

Just in case you don’t have a Laravel project setup, this guide will help you to [create a new Laravel project locally.](https://laravel.com/docs/5.7#installing-laravel)

### Install and Configure the Twilio Laravel SDK
The first thing we need to do is install the Twilio Laravel SDK which will provide the needed functions to get our bulk SMS app started. We’ll use the command line to achieve that. So in the command line type:

```console
$ composer require twilio/sdk
```
Now that we have the SDK installed, we need to configure it to recognize our Twilio account. Open up your .env file and paste in the following code. Be sure to replace the variables with your Twilio credentials. TWILIO_FROM is your Twilio Number.

```php
TWILIO_SID=ACXXXXXXXXXXXXXXXXXXX
TWILIO_TOKEN=XXXXXXXXXXXXXXXXXXXXX
TWILIO_FROM=APXXXXXXXXXXXXXXXXXXX
```
###Setup the Controller and View

We need a controller specially for our BulkSMS app, so paste in the command below to create a controller using Laravel’s artisan console.

```console
$ php artisan make:controller BulkSmsController
```
Open the controller and include the Twilio class at the top:

```php
namespace App\Http\Controllers;

use Illuminate\Http\Request;
use Twilio\Rest\Client;
use Validator;
```

Next we will create a view file called bulksms.blade.php to make an HTML form to create the necessary fields for our bulk SMS app.

```console
$ touch resources/views/bulksms.blade.php
```
Open up the newly created file located at resources/views/bulksms.blade.php and paste in the code below:

```html
<html>
      <body>
         <form action='' method='post'>
              @csrf
                      @if($errors->any())
              <ul>
             @foreach($errors->all() as $error)
            <li> {{ $error }} </li>
             @endforeach
        @endif

        @if( session( 'success' ) )
             {{ session( 'success' ) }}
        @endif

             <label>Phone numbers (seperate with a comma [,])</label>
             <input type='text' name='numbers' />

            <label>Message</label>
            <textarea name='message'></textarea>

            <button type='submit'>Send!</button>
      </form>
    </body>
</html>
  ```



















