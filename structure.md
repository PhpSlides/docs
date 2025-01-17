# PhpSlides Framework (Legacy)

## Project Directory Structure

PhpSlides follows the MVC (Model-View-Controller) architecture, where each folder and file serves a specific purpose. Below is the default project directory structure:

```
Project Directory
├── app
│   ├── Controller
│   ├── Forgery
│   ├── Http
│   │   ├── Guards
│   │   ├── Cors.php
│   │   ├── Jwt.php
│   │   └── Guard.php
├── src
│   ├── Configs
│   ├── Resources
│   └── Routes
├── vendor
├── .env
├── config.json
├── app.php
├── web.php
├── render.php
└── .htaccess
```

This structure includes critical directories for the logic, configuration, routes, and resources required to build your PhpSlides application.

---

## Explanation of Key Directories

### **`app` Directory**
The `app` directory contains subdirectories where the main logic code is written.

#### 1. **`app/Controller`**
This directory consists of Controller classes, which are used in routing.  
To create a new Controller class:
- You can create it manually and write the default code.
- Or use the `phpslides` command, which will automatically create the class with the default code.

Command to create a new Controller:
```bash
phpslides make:controller ClassName
```
- Replace `ClassName` with the desired name of the Controller.
- All generated Controller classes will end with `Controller` (e.g., `HomeController`).

#### 2. **`app/Forgery`**
The `Forgery` directory contains database structure files, which define the database schema.  
You can:
- Create these files manually, or
- Use the `phpslides` command.

View the **Database System Guide** for more details.

#### 3. **`app/Http`**
This directory contains HTTP-related logic, including API endpoints and guards.

- **`app/Http/Endpoint`**:  
  This directory consists of API Controller classes used in API routes.  
  To create an API endpoint:
  ```bash
  phpslides make:controller User
  ```
  - Replace `User` with the endpoint name.
  - The file and class name must end with `Endpoint` (e.g., `UserEndpoint`).

  The command automatically creates the endpoint in the `app/Http/Endpoint` directory with a template code similar to that of a regular Controller.

- **`app/Http/Guards`**:  
  This directory contains authentication logic for protecting routes. Guards can be created manually or using the command:
  ```bash
  phpslides make:guard AdminGuard
  ```
  - Replace `AdminGuard` with the desired guard name.

---

### **`src` Directory**
The `src` directory is responsible for handling configuration, resources, and routes.

#### 1. **`src/Configs`**
This directory contains configuration files for PhpSlides, including settings for:
- CORS
- JWT
- Guards

#### 2. **`src/Routes`**
This directory is used for route registration.  
- The main file for registering routes is `render.php`.  
- Sub-files include `web.php` for web routes and `api.php` for API routes.

You can register all routes inside `render.php` and call the `render` function.

#### 3. **`src/Resources`**
This directory contains files that are rendered on the client side.  
- It includes the `views` directory, where all view files must be stored.  
- Other subdirectories like `assets` can also be added for additional resources.

---

## Key Commands

### Creating a Controller
```bash
phpslides make:controller ClassName
```
- Creates a new Controller in `app/Controller`.

### Creating an API Endpoint
```bash
phpslides make:controller EndpointName
```
- Creates a new API endpoint in `app/Http/Endpoint`.

### Creating a Guard
```bash
phpslides make:guard GuardName
```
- Creates an authentication guard in `app/Http/Guards`.
