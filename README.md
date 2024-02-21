# go_web_server

## Description
This project presents a straightforward implementation of a web server in the Go programming language. Solely utilizing the Go Standard Library, the server serves educational purposes, delving into the essential functions offered by the standard library's net/http package. The server achieves the following:

- Listens to a specified port for incoming HTTP requests.
- Processes requests and responds with corresponding HTTP responses.

The application handles requests through two methods:

1. **Handler Functions:** Registers individual functions to process requests based on specific patterns.
2. **FileServer Handler:** Serves HTTP requests with the contents of the file system rooted at the specified root.

Additionally, the repository includes a Postman collection for testing the web server's functionality.

## Getting Started

### Dependencies
Ensure you have the following for building and compiling the application:

- Go version 1.18.x or higher.
- Optionally, Postman for running provided tests.

### Installation

1. Clone this repository.
2. Set the repository folder as your working directory.
3. Initialize the module for the application by running the following commands in the terminal (provide a suitable name for your module):

   ```bash
   go mod init module_name
   go mod vendor
   ```

4. Update the package reference in the import section inside `cmd/web-server/golang-web-server.go` with the module_name used in the previous step:

   ```go
   "module_name/pkg/handler"
   ```

5. Compile and build the application to ensure everything works:

   ```bash
   ./scripts/build.sh
   ```

   Alternatively:

   ```bash
   go build -o ./bin/web-server cmd/web-server/golang-web-server.go
   ```

   This generates a binary file named `web-server` in the `bin` directory.

### Execution

Run the web-server binary file directly:

```bash
./bin/web-server
```

Expected outcome:

```
Initializing the handler functions...
Handler functions have been initialized
Listening on localhost:8081...
```

Note: By default, the application executes using handler functions and listens on port 8081.

Alternatively, run the application with the FileServer handler:

```bash
./bin/web-server -use-handler-functions=false
```

Expected outcome:

```
Initializing handler with FileServer
Handler has been initialized
Listening on localhost:8081...
```

## Testing

Interact and test the application using either a web browser or Postman.

### Web Browser

Open a web browser and go to [http://localhost:8081](http://localhost:8081). If everything works, the index page should load. Examine the source code for requests processed by the web server, which varies depending on the application's request-handling method (handler functions or FileServer handler).

### Postman

Import the collection into Postman and open the "Golang Mini Web Server" collection. The requests are grouped into folders for handler functions and FileServer handler implementations. Run requests within the folder that matches the current mode of the web server.
