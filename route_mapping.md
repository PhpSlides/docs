# Route Mapping

## Overview
Route mapping is the recommended modern approach for creating routes in web applications. The `map()` function is utilized to create new routes and append them to their respective actions.

## Basic Usage

### Route Map Function
The basic syntax for route mapping is:
```php
Route::map()
```

The map function accepts two parameters:
1. Request Method Parameter: Defines the HTTP request method for each instance
2. Route URL Parameter: Defines the actual route URL path

### Supported HTTP Methods
The following HTTP request methods are supported:
- GET
- POST
- PUT
- PATCH
- DELETE

Multiple methods can be defined for each route instance by separating them with '|':
```php
"GET|POST"  // This will match both GET and POST requests
```

## Pattern Matching Routes

### Using Custom Patterns
Route mapping supports custom pattern matching for request URIs. Patterns are declared using the following syntax:
```php
Route::map(GET, 'pattern: {{your_pattern}}')
```

### Pattern Syntax
- Must start with `pattern:` keyword
- Uses fnmatch() style pattern matching
- Common patterns:
  - `pattern: *` - Matches all request URIs
  - `pattern: /admin/*` - Matches any URI that starts with /admin/

Example:
```php
Route::map(GET, 'pattern: /users/*')->action(function() {
    // Handles any URI starting with /users/
});
```

## Nested Routes

### Mapping Routes to Base Route
You can map additional routes to a base route, creating a hierarchical structure:

```php
Route::map(GET, "/admin")->action()
    ->Route::route("/dashboard", function(Request $req, Closure $accept) {
        $accept(GET, fn($method) => "`$method` method is not allowed");
        return "Admin Dashboard";
    })
```

### Nested Route Parameters
1. First parameter: Request URI path
2. Second parameter: Closure or callable function
   - The closure receives two arguments:
     - `$req`: Request header information
     - `$accept`: Function to handle method acceptance

### Accept Function
- Used to specify allowed HTTP methods
- Takes two parameters:
  - Allowed method(s)
  - Fallback function for unallowed methods
- The fallback receives the actual request method as an argument

Example accessing nested route:
```
http://localhost:2200/admin/dashboard
```

## Case Sensitivity

### Route Case Sensitivity
By default, all routes are case insensitive. To make a route case sensitive, use the `caseSensitive()` method:

```php
Route::map(GET, "/Admin")->caseSensitive()->action(function() {
    // This route will only match exact case "/Admin"
});
```

### Default Behavior
- Case insensitive: `/admin` will match `/Admin`, `/ADMIN`, etc.
- With `caseSensitive()`: Only exact case matches will work

## Map Action Methods

### 1. file() Method
- Takes 1 parameter which specifies the view file path to be rendered
- Used for direct view file rendering
- Example:
```php
Route::map("GET", "/index")->file("::index");
```

### 2. use() Method
- Used in adding controller class methods
- Requires controller class name followed by double colon and method name
- Example:
```php
Route::map(GET, "/index")->use("UserController::index");
```
Note: When following the MVC pattern, you don't need to specify the controller namespace.

### 3. action() Method
- Called directly with the response to be rendered
- Supports multiple formats:

#### a. Using Controller Methods
```php
Route::map()->action([Controller::class, "method"]);
```

#### b. Using Closure Functions
```php
Route::map()->action(function(){ return "Hello"; });
```

#### c. Using Request Parameters
```php
Route::map()->action(function(Request $req) { ... });
```

#### d. Direct String Output
```php
Route::map()->action("Hello World");
```

## Special Cases

### Functional Arrays
You can call functional arrays using:
```php
Route::map()->action([Controller::class, "method"]);
```
This will execute the method function in that class and display it on the web.

### Default String Rendering
When a default string is passed as an argument in the parameter:
```php
Route::map()->action(view::render("::index"));
```
The view file will be the output when they navigate to the route.

### Simple String Output
For basic string output:
```php
Route::map()->action("Hello World");
```
This will display "Hello World" on the web page.

## Notes
- For each function called, the Request will be passed as the argument in the parameters if set
- By default, it will output any result it is given
- Views are typically rendered using the view function: `View::render("Folder::File")`