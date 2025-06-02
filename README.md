# Go Bookstore API

A simple RESTful API for managing books, built with Go, GORM, and Gorilla Mux.

## Features

- Connects to MySQL database using GORM ORM
- CRUD operations on `Book` model (Create, Read, Update, Delete)
- REST API routing with Gorilla Mux

## Requirements

- Go 1.18+ (or your installed version)
- MySQL server
- Git (to clone repo)

## Setup

1. Clone the repository:

   ```bash
   git clone https://github.com/saaib8/go-bookstore.git
   cd go-bookstore
````

2. Create the MySQL database:

   ```sql
   CREATE DATABASE simplerest;
   ```

3. Update database credentials in `pkg/config/app.go`:

   ```go
   gorm.Open("mysql", "username:password@tcp(localhost:3306)/simplerest?charset=utf8&parseTime=True&loc=Local")
   ```

4. Run the application:

   ```bash
   go run main.go
   ```

   The server will start at `http://localhost:8080`

## API Endpoints

| Method | Endpoint          | Description             |
| ------ | ----------------- | ----------------------- |
| GET    | `/books`          | Get all books           |
| GET    | `/books/{bookId}` | Get book by ID          |
| POST   | `/books`          | Create a new book       |
| PUT    | `/books/{bookId}` | Update an existing book |
| DELETE | `/books/{bookId}` | Delete a book           |

## Project Structure

```
.
├── cmd/
├── pkg/
│   ├── config/       # Database connection and config
│   ├── controllers/  # HTTP handlers
│   ├── models/       # GORM models and DB logic
│   └── utils/        # Helper functions
├── main.go           # Application entry point
└── go.mod            # Go modules file
```

## Notes

* Make sure MySQL server is running before starting the app.
* Use tools like Postman or curl to test API endpoints.
* This project uses GORM v1 (github.com/jinzhu/gorm).


