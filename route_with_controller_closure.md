## **Route Handling and Request Using Controller Closure**

### **Introduction**
In **PhpSlides** framework, routing helps in connecting HTTP requests to specific controller methods, enabling dynamic and organized request handling. This documentation demonstrates creating routes, utilizing controllers, and handling requests.

### **Creating a Controller**
Controllers are the backbone of handling logic for specific requests. To create a controller, follow these steps:

#### **1. Automatic Creation:**
Run the following command to generate a controller automatically:
```bash
phpslides make:controller UserController
```

#### **2. Manual Creation:**
Create a file manually in the `app/Http/Controller/` directory. Make sure the file and class names end with `Controller`. For example:
- File: `UserController.php`
- Class: `UserController`

---

### **Example of a Controller**
A typical controller looks like this:
```php
<?php
namespace App\Http\Controller;

use PhpSlides\Core\Http\Request;

final class UserController {
    public function index(Request $req) {
        return "Hello User";
    }
}
?>
```

---

### **Routing to a Controller Method**
Routes link specific HTTP methods and URLs to controller methods. You can define routes as follows:

#### **1. Basic Route Definition:**
Use the namespace directly:
```php
Route::get("add-item", [\App\Http\Controller\UserController::class, "index"]);
```

#### **2. With Namespace Declaration:**
Alternatively, add the namespace at the top of the file:
```php
<?php
use App\Http\Controller\UserController;

Route::get("add-item", [UserController::class, "index"]);
?>
```

---

### **Controller Method Convention**
By convention, specific methods in a controller correspond to standard HTTP requests:

1. **index()**  
   - Used for handling `GET` requests without URL parameters.  
   - Example: Fetching a list of items.

2. **show()**  
   - Handles `GET` requests with one or more URL parameters.  
   - Example: Viewing a specific item by ID.

3. **destroy()**  
   - Handles `DELETE` requests with one or more URL parameters.  
   - Example: Deleting a specific resource.

4. **store()**  
   - Handles `POST` requests.  
   - Example: Creating a new resource.

5. **update()**  
   - Handles `PUT` requests.  
   - Example: Updating an existing resource.

6. **patch()**  
   - Handles `PATCH` requests.  
   - Example: Partially updating a resource.

---

### **Conclusion**
By combining routing and controllers, handling requests becomes structured and scalable. The predefined methods (index, show, etc.) ensure uniformity across routes, simplifying development. Use these principles to enhance your application's functionality and maintainability.

--- 