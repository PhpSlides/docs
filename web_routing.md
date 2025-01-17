# Web Routing

Routing on the web determines what is displayed on the web and decides actions based on routes.

Routes can be registered in the `web.php` file, which is already created. Each route includes the request URL, request method, and the action to take if the route matches the specified URL and method.

## View Route

A view route is used to render a view file directly on the web when a specific route URL is visited. To create a view route, edit the `web.php` file. If it is not included in the `render.php` file, include it using `include_once "web.php";` or write the route directly in `render.php`.

Example:

**web.php**
```php
<?php

use Phpslides\Router\Route;
use Phpslides\Router\view;

Route::view("/index", "::Index");
```
The `Route::view` function takes two parameters:
1. The request URL to use (e.g., `/index`).
2. The view file to render (e.g., `::Index`).

The view file follows the `::` pattern to include files in the views directory. For example, `::Index` represents the `Index.psl` file in the views directory.

Navigate to `http://localhost:2200/index` in the browser to see the output of the `Index.psl` file.
