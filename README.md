# sitemap-crawler
Sitemap crawler/generator. For given URL it will return sitemap XML file.

Fork of ivebe/sitemap-crawler with some crazy helping hacks :)

## Install
```sh
composer require ivebe/sitemap-crawler
```

## Example

```php
<?php

require_once __DIR__ . '/vendor/autoload.php';

use Ivebe\SitemapCrawler\Crawler;
use Ivebe\SitemapCrawler\SitemapService;
use Ivebe\SitemapCrawler\LinkCollection;

$config = require "src/config.php";
$url = "http://www.google.com";

$crawler    = new Crawler($config);
$collection = new LinkCollection();
$provider   = new SitemapService($crawler, $collection);

$links = $provider->crawl($url);
$provider->export('monthly');
```
