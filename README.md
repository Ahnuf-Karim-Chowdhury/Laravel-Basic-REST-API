# Laravel-Basic-REST-API
---
# Overview
This project is a Laravel-based REST API. The structure of the project is organized to follow best practices for building scalable and maintainable applications. The API provides endpoints for managing posts and user authentication.

# Project Structure
The project structure is as follows:

```
app
├── Http
│   ├── Controllers
│   │   ├── ApiController.php
│   │   ├── Controller.php
│   │   └── PostController.php
│   └── Requests
│       ├── StorePostRequest.php
│       └── UpdatePostRequest.php
├── Models
│   ├── Post.php
│   └── User.php
├── Providers
│   └── AppServiceProvider.php
bootstrap
config
database
public
resources
routes
├── api.php
├── console.php
└── web.php
storage
tests
vendor
.editorconfig
.env
.env.example
.gitattributes
.gitignore
artisan
composer.json
composer.lock
package.json
phpunit.xml
README.md
webpack.mix.js

```

---
# Models
---
   # post.php
- **Namespace**: `App\Models`
- **Purpose**: Model representing a post.
- **Key Methods**:
   - `fillable`: Specifies the attributes that are mass assignable (`title`, `description`).

   # user.php
- **Namespace**: `App\Models`
- **Purpose**: Model representing a user.
- **Key Methods**:
   - `fillable`: Specifies the attributes that are mass assignable (`name`, `email`, `password`).
   - `hidden`: Specifies the attributes that should be hidden for serialization (`password`, `remember_token`).
   - `casts()`: Specifies the attributes that should be cast to native types (`email_verified_at`, `password`).
---


# Controllers
---
# ApiController.php
- **Namespace**: `App\Http\Controllers`
- **Purpose**: Base controller for handling API responses.
- **Key Methods**:
   - `Response($data, $message, $status = 200)`: Returns a JSON response with data and message.
   - `errorResponse($message = "Error", $status = 500)`: Returns a JSON error response with a message.

# PostController.php
- **Namespace**: `App\Http\Controllers`
- **Purpose**: Controller for managing posts.
- **Key Methods**:
   - `index()`: Retrieves and returns a list of all posts.
   - `store(StorePostRequest $request)`: Creates a new post with validated data.
   - `show($id)`: Retrieves and returns a specific post by ID.
   - `update(UpdatePostRequest $request, $id)` : Updates a specific post with validated data.
   - `destroy($id)` : Deletes a specific post by ID.
---


# Requests
---
     
  # StorePostRequest.php
- **Namespace**: `App\Http\Requests`
- **Purpose**: Handles validation for creating a new post.
- **Key Methods**:
   - `authorize()`: Determines if the user is authorized to make this request.
   - `rules()`: Returns validation rules for the request.

  # UpdatePostRequest.php
- **Namespace**: `App\Http\Requests`
- **Purpose**: Handles validation for updating an existing post.
- **Key Methods**:
   - `authorize()`: Determines if the user is authorized to make this request.
   - `rules()`: Returns validation rules for the request.

  
---

# Running the Project
---
To run the project, follow these steps:

1. Clone the repository:
   ```
   git clone <repository-url>
   ```
2. Navigate to the project directory:
   ```
   cd <project-directory>
   ```
3. Install the dependencies:
   ```
   composer install
   ```
4. Set up the environment variables:
   ```
   cp .env.example .env
   ```
5. Generate the application key:
   ```
   php artisan key:generate
   ```
6. Run the migrations:
   ```
   php artisan migrate
   ```
7. Serve the application:
   ```
   php artisan serve
   ```


