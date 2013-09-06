A Better Plan API Symfony2 Bundle
========================

API Documentation /api/doc/

## Installation

Installation is a quick process:

1. Download AbpApiBundle using composer
2. Enable the Bundle
3. Configure the AbpApiBundle
4. Use the AbpApiBundle

### Step 1: Download FOSUserBundle using composer

Add AbpApiBundle in your composer.json:

```js
{
    "require": {
        "illuminadigital/dls-abp-api-bundle": "*@dev",
    }
}
```

```js
{
    "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/illuminadigital/dls-abp-api-bundle.git",
            "type": "git"
        }
    }
}
```

Now tell composer to download the bundle by running the command:

``` bash
$ php composer.phar update illuminadigital/dls-abp-api-bundle
```

Composer will install the bundle to your project's `vendor/illumina` directory.

### Step 2: Enable the bundle

Enable the bundle in the kernel:

``` php
<?php
// app/AppKernel.php

public function registerBundles()
{
    $bundles = array(
        // ...
        new Illumina\AbpApiBundle\IlluminaAbpApiBundle(),
    );
}
```

### Step 3: Configure the AbpApiBundle

``` js
// app/config/parameters.yml
parameters:
    illumina_abp_base_url: 'base-url-here'
    illumina_abp_key: 'api-key-here'
    illumina_abp_secret: 'secret-key-here'
```

### Step 3: Use the AbpApiBundle

In a controller

``` php
<?php

// Get all the user info
$this->get('illumina.abp.retriever')->getUserInfo(USER_TOKEN);

//Get the current time on the API server
$this->get('illumina.abp.retriever')->getTime();
```