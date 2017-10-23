# Laravel Site

A simple package to use in a new Laravel installation (5.5+). It takes care of all things related to launching a simple website: catching all routes, getting the relevant page and site content from the database, launching the correct view, etc.

##### no additional programming involved
You don't have to program anything to get a website up & running! Just add a catch-all route definition, add your layout in the views and that's it...

##### use filters on page content
There are hooks to pass your page content through filters, before the data is send to the view. This way you can create default meta data, prefix content for all pages with extra content, etc.

##### use the laravel view system
You can have different views for different pages and a default view for the rest. The whole visual part of the website is 100% up to you...

##### use related pages
You can create pages with lists of other pages on it, like sitemaps or news overview pages. We call this 'related pages'.

##### including a skeleton website
The package comes with a skeleton website to get you started: a couple of example pages, some views, etc.


## Quick install
You can install the package with composer. See the extensive documentation for exact instructions to install the config files, the skeleton website (if needed), etc...

```
$ composer require redcenter/laravel-site

```

Publish the package:
```
$ php artisan vendor:publish --provider="LaravelSite\Providers\LaravelSiteServiceProvider" --force --tag=package
```

Laravel will use package-discovery to get the correct config files, use the correct migrations, etc. This will...

* create a config file (`laravel-site.php`) in the correct folder
* add package migrations to Laravel's migration list

Add catch-all route:

You only have to add one route to your route file to catch all incoming requests. Add to your routes file:

    /**
     * Catch all routes
     */
    Route::get('/{any}', '\LaravelSite\Controllers\PageController@showPage')->where('any', '.*');

    
    
# Check out the documentation on Bitbucket for all details!
https://bitbucket.org/redcenter/laravel-site
