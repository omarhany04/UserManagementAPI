# UserManagementAPI

ASP.NET Core Web API for managing users with in-memory storage, custom middleware, and Swagger UI.

## Features

- Users CRUD API
- Request and response logging middleware
- Global error handling middleware
- Simple bearer token authentication middleware
- Swagger UI for testing endpoints

## Requirements

- .NET SDK 10.0 or later

## Run The API

```powershell
dotnet run
```

The default launch profiles use:

- `https://localhost:7217`
- `http://localhost:5129`

Open Swagger:

```text
https://localhost:7217/swagger
```

## Authentication

All API routes require this header:

```text
Authorization: Bearer mysecrettoken
```

In Swagger, click **Authorize** and enter:

```text
Bearer mysecrettoken
```

## API Endpoints

### Get All Users

```http
GET /api/users
```

### Get User By Id

```http
GET /api/users/{id}
```

### Add User

```http
POST /api/users
Content-Type: application/json
Authorization: Bearer mysecrettoken

{
  "name": "Ali",
  "email": "ali@test.com"
}
```

### Update User

```http
PUT /api/users/{id}
Content-Type: application/json
Authorization: Bearer mysecrettoken

{
  "name": "Ali Updated",
  "email": "updated@test.com"
}
```

### Delete User

```http
DELETE /api/users/{id}
Authorization: Bearer mysecrettoken
```

## Project Structure

```text
Controllers/
  UsersController.cs
Middleware/
  AuthMiddleware.cs
  ErrorHandlingMiddleware.cs
  LoggingMiddleware.cs
Models/
  User.cs
Program.cs
```
