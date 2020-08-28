This eBay SDK makes it easy for you to use [eBay API](https://developer.ebay.com/docs) in your PHP-based project.

This repository is not a hobby or a side-project, but a code maintained by a for-profit company that uses it in production. We promise to keep it open-source and maintain it for as long as we operate.

# About this repository

This repository is maintained by the company [GeekSeller.com](https://www.geekseller.com/), and it is a fork of another [eBay SDK repository](https://github.com/davidtsadler/ebay-sdk-php/). The original code has been developed by [David T. Sadler](https://github.com/davidtsadler), however, in February 2020, David archived the project and decided not to continue maintaining it. GeekSeller uses David’s SDK in the production, so we decided to create a fork of this SDK, maintain it as a separate project and offer it to the community.

Please note that GeekSeller is part of the eBay Developer Program and we have our eBay application listed in the [eBay Solution Directory](https://cgi6.ebay.com/ws/eBayISAPI.dll?SolutionsDirectory&page=details&solutionId=705084376), however, this SDK is not endorsed, sponsored or maintained by eBay.

## Support

This repository is updated on a regular basis. It may take time to have reported issues fixed, but we encourage you to submit tickets, contribute or contact us to request premium support.

## Documentation

The documentation for the eBay API can be found [here](https://developer.ebay.com/docs).

Some [examples](https://github.com/geekseller/ebay-sdk-examples) of using this SDK.

## Requirements

  - PHP 5.5 or greater with the following extensions:
      - cURL
      - libxml
  - 64 bit version of PHP recommended as there are some [issues when using the SDK with 32 bit](http://devbay.net/sdk/guides/getting-started/requirements.html#using-the-sdk-with-32-bit-systems).
  - SSL enabled on the cURL extension so that https requests can be made.

## Installation

The SDK can be installed with [Composer](http://getcomposer.org/). Please see the [Installation section of the User Guide](http://devbay.net/sdk/guides/getting-started/installation.html) to learn about installing through other means.

  1. Install Composer.

     ```
     curl -sS https://getcomposer.org/installer | php
     ```

  1. Install the SDK.

     ```
     php composer.phar require geekseller/ebay-sdk-php
     ```

  1. Require Composer's autoloader by adding the following line to your code.

     ```php
     require 'vendor/autoload.php';
     ```

## Example

### Get the official eBay time

```php
<?php

require 'vendor/autoload.php';

use \DTS\eBaySDK\Shopping\Services;
use \DTS\eBaySDK\Shopping\Types;

// Create the service object.
$service = new Services\ShoppingService();

// Create the request object.
$request = new Types\GeteBayTimeRequestType();

// Send the request to the service operation.
$response = $service->geteBayTime($request);

// Output the result of calling the service operation.
printf("The official eBay time is: %s\n", $response->Timestamp->format('H:i (\G\M\T) \o\n l jS Y'));
```
