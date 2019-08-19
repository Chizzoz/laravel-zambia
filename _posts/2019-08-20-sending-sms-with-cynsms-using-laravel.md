---
layout: post
published: false
title: Sending Sms with Cynsms Using laravel
---
## Sending Sms with Cynsms Using laravel

Cyn SMS API is build for Cyn SMS - Bulk SMS Application For Marketing

## Technical Requirements
For this tutorial we’ll assume you already know or have the following:

- A Terminal (Command Line)
- Composer installed
- Are familiar with PHP
- Are familiar with Laravel (5+)
- You have an existing Laravel (5+) project
- You have a Cynsns account and your credentials ready

Just in case you don’t have a Laravel project setup, this guide will help you to [create a new Laravel project locally.](https://laravel.com/docs/5.7#installing-laravel)

### Install and Configure the Cynsms SDK
The first thing we need to do is install the Cynsms SDK which will provide the needed functions to get our SMS app started. We’ll use the command line to achieve that. So in the command line type:

# Cyn SMS API


### Prerequisites

To run Cyn SMS API you have to install Cyn SMS Application on your server. 
For more details please visit: [Cyn SMS](https://cynsms.online/)
```
php >=5.6
Cyn SMS - Bulk SMS Application For Markting
```
### Installing
Via Composer
```
composer require cynojine/cynsms-api 
```

And Via Bash

```
git clone https://github.com/cynojine/cynsms-api.git
```

## Usage


 ### Step 1:
If install Cyn SMS API using Git Clone then load your Cyn SMS API Class file and Use namespace. 
```php
require_once 'src/Class_Cyn_SMS_API.php';
use CynSMS\CynSMSAPI;
```
If install Cyn SMS API using Composer then Require/Include autoload.php file in the index.php of your project or whatever file you need to use **Cyn SMS API** classes:. 
```php
require 'vendor/autoload.php';
use CynSMS\CynSMSAPI;
```
### Step 2:
set your API_KEY from `https://mywebhost.com/sms-api/info` (your application install url)
```php
$api_key = 'YWRtaW46YWRtaW4ucGFzc3dvcmQ=';
```
### Step 3:
Change the from number below. It can be a valid phone number or a String
```php
$from = '2699655847554';
```

### Step 4:
the number we are sending to - Any phone number
```php
$destination = '8801810000000';
```
You have to must include Country code at beginning of the phone number.  

### Step 5:
Replace your Install URL like `https://mywebhost.com/sms/api` with `https://cynsms.online/`
`sms/api` is mandatory on your install url

