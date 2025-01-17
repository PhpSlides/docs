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
```php
Route::post("/submit", function () {
    return "Form Submitted";
});
```
