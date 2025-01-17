## Installation Guide

### Requirements
- PHP version >= 8.2
- Composer installed for development purposes
- Apache/Nginx for production

### Installation Methods

#### Method 1: Using Composer
```bash
composer create-project phpslides/phpslides ProjectName
```
Replace "ProjectName" with your desired project name (this will also be used as the directory name).

#### Method 2: Using PhpSlides CLI
1. First, install the PhpSlides CLI tool:
```bash
composer global require phpslide/cli
```

2. Verify installation:
```bash
phpslides --help
```

3. Create a new project:
```bash
phpslides create ProjectName
```

#### Method 3: Manual Installation
1. Clone the repository directly from GitHub:
```bash
git clone https://github.com/phpslides/phpslides.git
```

2. If no terminal is available, you can download the template directly from GitHub:
   - Visit: https://github.com/phpslides/phpslides
   - Follow the phpslides URL on GitHub

### Post-Installation
After installation, rename the `.env.example` file to `.env` before starting your development server.

## Project Structure

### Directory Overview
PhpSlides follows MVC architecture where you need to understand every aspect of each files and folder.

```
project-root/
├── app/
│   ├── Forgery/
│   ├── Http/
│   │   ├── Controller/
│   │   └── Endpoint/
│   └── Guards/
├── src/
│   ├── configs/
│   ├── resources/
│   └── routes/
├── vendor/
├── .env
├── .htaccess
└── configs.json
```

### Core Directories

#### 1. App Directory
The `app` directory contains your main application logic:

##### Controllers
- Houses controller classes for web routing
- Each controller must end with "Controller" suffix
- Create new controllers using:
```bash
phpslides make:controller ClassName
```

##### Forgery
- Contains database structure definitions
- Used for creating and managing database tables
- Can be created manually or via CLI commands
- View complete guide on creating database system in the database section

##### Http/Endpoint
- Contains API controllers used for endpoints
- All files must end with "Endpoint"
- Create API endpoints using:
```bash
phpslides make:api-controller User
```
- Automatically creates `UserEndpoint` class in Http/Endpoint directory

##### Guards
- Contains authentication logic
- Used for protecting web & API routes
- Create guards using:
```bash
phpslides make:guard AdminGuard
```

### Core Components
1. Controllers
   - Handle web routing and request processing
   - Must follow naming convention: `ClassNameController`
   - Can be created manually or via CLI

2. API Controllers
   - Handle API endpoints
   - Must end with "Endpoint" suffix
   - Follow RESTful conventions

3. Guards
   - Manage authentication and authorization
   - Protect routes and resources
   - Can be customized for different access levels

4. Database (Forgery)
   - Manage database structures
   - Create and modify tables
   - Handle database migrations

## Configuration
Basic configuration details are stored in `.env` file. Make sure to:
1. Copy `.env.example` to `.env`
2. Update database and other configuration settings
3. Set up your development environment before starting

## Next Steps
- Set up your first controller
- Create database structures
- Configure authentication
- Start building your application