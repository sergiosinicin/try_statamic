## Laravel install ##

- ``composer global require laravel/installer``
- ``laravel new meetroom``
- ``npm install && npm run build
  composer run dev``

## Docker install ##

- ``composer require laravel/sail --dev``
- ``php artisan sail:install --with=none``
- to start ``./vendor/bin/sail up -d``

## Statamic install ##

 - ``php artisan config:clear``
 - add to composer.json :
``"scripts": { 
    "pre-update-cmd": [ 
        "Statamic\\Console\\Composer\\Scripts::preUpdateCmd" 
    ],  
    "post-autoload-dump": [ 
        "Illuminate\\Foundation\\ComposerScripts::postAutoloadDump",
        "@php artisan package:discover --ansi",
        "@php artisan statamic:install --ansi" 
    ], 
} ``
 - ``composer require statamic/cms --with-dependencies``
 - ``php please auth:migration``
