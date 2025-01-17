## Adding Parameters to Route Closures

The second parameter in a route, which is the closure function, can include parameters to access request details. Phpslides provides a `Request` object to get information about the current global request, such as query parameters.

Example:
```php
use PhpSlides\Router\Route;
use PhpSlides\Core\Http\Request;

Route::post("/add-data", function (Request $req) {
    $data = $req->post('key');
    return "Data Received: " . $data;
});
```
Here:
- `$req` is an instance of `Phpslides\Core\Http\Request`.
- You can use methods like `post()` to access post request data.

Learn more about [`Request`](/http_request.md) and its methods in the full documentation.
