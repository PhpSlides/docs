# Web Routing

Routing on the web determines what is displayed on the web and decides actions based on routes.

Routes can be registered in the `web.php` file, which is already created. Each route includes the request URL, request method, and the action to take if the route matches the specified URL and method.


## View Route

A view route is used to render a view file directly on the web when a specific route URL is visited. To create a view route, edit the `web.php` file. If it is not included in the `render.php` file, include it using `include_once "web.php";` or write the route directly in `render.php`.

Example:

**web.php**
```php
<?php

use PhpSlides\Router\Route;
use PhpSlides\Router\view;

Route::view("/index", "::Index");
```
The `Route::view` function takes two parameters:
1. The request URL to use (e.g., `/index`).
2. The view file to render (e.g., `::Index`).

The view file follows the `::` pattern to include files in the views directory. For example, `::Index` represents the `Index.psl` file in the views directory.

Navigate to `http://localhost:2200/index` in the browser to see the output of the `Index.psl` file.


## GET Route with Closure

A GET route can be registered to handle GET request methods. Example:

**web.php**
```php
Route::get("/index", function () {
    return "Index Page";
});
```
Here:
1. The first parameter is the request URI (`/index`).
2. The second parameter is a closure function that handles the request.

When a user navigates to `/index`, the string "Index Page" is returned.


## POST Route with Closure

A POST route can be registered to handle POST request methods, usually for form submissions.

Example:
```php web.php
Route::post("/submit", function () {
    return "Form Submitted";
});
```


## PUT Route with Closure

A PUT route is usually used to update information in a database. Example:

```php
Route::put("/update", function () {
    return "Update Successful";
});
```


## PATCH Route with Closure

A PATCH route is used for partial updates. Example:

```php
Route::patch("/partial-update", function () {
    return "Partial Update Successful";
});
```


## DELETE Route with Closure

A DELETE route is used to remove information from a database or destroy sessions. Example:

```php
Route::delete("/delete-user", function () {
    return "User Deleted";
});
```