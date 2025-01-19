# PhpSlides Framework Documentation

## 1. Getting Started

- [Introduction to PhpSlides Framework](/introduction.md)
- [Installation Guide](/installation.md)
- [Project Directory Structure](/project_structure.md)
- [Basic Configuration](/configuration.md)
- Quick Start Guide

## 2. Core Concepts

### 2.1 Routing System
- [Basic Route Handling](/web_routing.md)
- [HTTP Methods and Closures](/web_routing.md)
  - [GET Requests](/web_routing.md#get-route-with-closure)
  - [POST Requests](/web_routing.md#post-route-with-closure)
  - [PUT Requests](/web_routing.md#put-route-with-closure)
  - [PATCH Requests](/web_routing.md#patch-route-with-closure)
  - [DELETE Requests](/web_routing.md#delete-route-with-closure)
- [Route Parameters](/route_parameters.md)
- Named Routes
- Protected Routes
- [Route Mapping](/route_mapping.md)
  - [Pattern Matching Routes](/route_mapping.md#pattern-matching-routes)
  - [Case Sensitivity](/route_mapping.md#case-sensitivity)
  - [Nested Routes](/route_mapping.md#nested-routes)
  - [Special Cases](/route_mapping.md#special-cases)

### 2.2 View System

- View Rendering Basics
- Working with .psl Files
- Template Syntax
- Including Other Views
- View Components
- Passing Data to Views

### 2.3 Authentication
- AuthGuard Overview
- User Authentication
- Authentication Middleware
- Protected Routes
- Session Management

## 3. Advanced Features

### 3.1 Request Handling
- Request Object
- Query Parameters
- Route Parameters
- Request Validation
- File Uploads
- Request Headers

### 3.2 Database Integration
- Database Configurationm
- Query Builder
- Table Creation
- Column Management
- Database Forgery System
- Data Migration

### 3.3 API Development
- RESTful API Basics
- API Versioning
- API Route Definition
- Controller Integration
- Response Formatting
- API Authentication

### 3.4 Security
- JWT Implementation
  - Token Generation
  - Payload Management
  - Token Verification
  - Token Expiration
- CSRF Protection
- XSS Prevention
- Security Best Practices

## 4. Template Engine Features

### 4.1 View Syntax
- PHP Tags Usage
- Control Structures
  - Foreach Loops
  - For Loops
  - While Loops
  - If/Else Conditions
- Comments
- Props System
- Bracket Interpolation

### 4.2 Asset Management
- Public Files Handling
- Image Processing
- Resource Management
- Asset Optimization