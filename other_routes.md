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
