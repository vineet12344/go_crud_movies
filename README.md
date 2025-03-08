# Movie API in GoLang

This is a simple RESTful API built using Go and Gorilla Mux for managing a collection of movies.

## Features
- Get all movies
- Get a single movie by ID
- Create a new movie
- Update an existing movie
- Delete a movie

## Technologies Used
- **Go** (Golang)
- **Gorilla Mux** (for routing)
- **net/http** (for handling HTTP requests)
- **encoding/json** (for JSON processing)
- **math/rand** and **strconv** (for generating random IDs)

## Setup and Installation

### Prerequisites
- Install [Go](https://go.dev/doc/install)

### Clone the Repository
```sh
git clone https://github.com/yourusername/yourrepository.git
cd yourrepository
```

### Install Dependencies
```sh
go get -u github.com/gorilla/mux
```

### Run the Application
```sh
go run main.go
```

The server will start at `http://localhost:8000`.

## API Endpoints

| Method | Endpoint          | Description               |
|--------|------------------|---------------------------|
| GET    | `/movies`        | Get all movies            |
| GET    | `/movies/{id}`   | Get a single movie by ID  |
| POST   | `/movies`        | Create a new movie        |
| PUT    | `/movies/{id}`   | Update an existing movie  |
| DELETE | `/movies/{id}`   | Delete a movie            |

## Sample JSON Request Bodies

### Create a Movie (POST `/movies`)
```json
{
  "isbn": "123456",
  "title": "New Movie",
  "director": {
    "firstname": "John",
    "lastname": "Doe"
  }
}
```

### Update a Movie (PUT `/movies/{id}`)
```json
{
  "isbn": "654321",
  "title": "Updated Movie",
  "director": {
    "firstname": "Jane",
    "lastname": "Doe"
  }
}
```

## Example Usage
### Get All Movies
```sh
curl -X GET http://localhost:8000/movies
```

### Get a Specific Movie
```sh
curl -X GET http://localhost:8000/movies/1
```

### Create a Movie
```sh
curl -X POST http://localhost:8000/movies -H "Content-Type: application/json" -d '{"isbn":"987654","title":"My Movie","director":{"firstname":"Alice","lastname":"Smith"}}'
```

### Update a Movie
```sh
curl -X PUT http://localhost:8000/movies/1 -H "Content-Type: application/json" -d '{"isbn":"123123","title":"Updated Title","director":{"firstname":"Bob","lastname":"Brown"}}'
```

### Delete a Movie
```sh
curl -X DELETE http://localhost:8000/movies/1
```

## Issues and Improvements
- Fix potential issues like handling non-existent movie IDs.
- Add persistent storage (currently using an in-memory slice).
- Implement authentication and authorization.

## Author
**Vineet Salve**

## License
This project is open-source and available under the [MIT License](LICENSE).

