Phase 1: Backend Fundamentals
Learning started
 Beginner → Intermediate


We're going to approach this as a practical backend engineering course, not just a collection of coding tutorials.

Our objective is to take you from understanding how a backend works to building your own servers, networking tools, APIs, and infrastructure.

Primary language: Go (Golang).

We'll use Go because it's particularly useful for networking, servers, concurrency, reverse proxies, load balancers, and distributed systems.
1. Phase 1 curriculum
Backend Fundamentals
7 projects

1. URL Shortener
   Start here
   HTTP APIs, routing, database operations, redirects and caching.
2. Build Your Own Web Server
   
   TCP sockets, HTTP protocol, request parsing and response handling.
3. Build Your Own Web Scraper
   
   HTTP clients, HTML parsing, concurrency and data extraction.
4. Build Your Own Rate Limiter
   
   Token bucket, sliding window, middleware and request throttling.
5. Build Your Own Reverse Proxy
   
   Request forwarding, routing, upstream servers and proxying.
6. Build Your Own API Gateway
   
   Authentication, API routing, middleware and service communication.
7. Build Your Own Load Balancer
   
   Round-robin, health checks, failure handling and traffic distribution.

2. Technology stack
We'll use the following tools throughout the course.
Technology	Purpose
Go	Backend programming
PostgreSQL	Database
Redis	Caching
Postman	API testing
VS Code	Code editor
Git + GitHub	Version control
Docker	Containerization
Linux	Server environment
Nginx	Reverse proxy
GitHub Actions	CI/CD

Don't worry about learning everything at once. We'll introduce each tool when a project needs it.
3. How every project will be taught
Every project will have six stages:
1. Understand: What problem are we solving?
2. Explore: How does the real technology work?
3. Design: Architecture, data flow and folder structure.
4. Build: Implement it step by step.
5. Test: Test functionality, errors and performance.
6. Deploy: Run it in a production-like environment and publish it on GitHub.
I'll also give you coding challenges and explanations of important code rather than simply handing you finished code.

Lesson 1: Understand Backend Development
Before writing code, you need to understand what actually happens when someone visits a website.
4. What is a backend?
Consider a simple login page.








medium.com


When a user enters their email and password:
1. Frontend collects the information.
2. Frontend sends an HTTP request to the backend.
3. Backend validates the information.
4. Backend communicates with the database.
5. Database returns the result.
6. Backend sends a response to the frontend.
7. Frontend displays the result.
The backend is responsible for business logic, authentication, data processing, database operations, security and communication.
5. Understand the request-response lifecycle
Imagine opening:

https://example.com/users

Your browser sends a request:
GET /users HTTP/1.1
Host: example.com
Accept: application/json


The backend processes the request and returns:
HTTP/1.1 200 OK
Content-Type: application/json

{
  "users": [
    {
      "id": 1,
      "name": "Abhishek"
    }
  ]
}


These are the important terms:
Term	Meaning
Client	Browser, mobile app or another service
Server	Software that processes requests
HTTP	Communication protocol
API	Interface through which software communicates
Endpoint	A specific API address
Request	Message sent to a server
Response	Message returned by a server
JSON	Common data exchange format
Database	Persistent data storage

6. The first concepts you must learn
Before starting the URL Shortener, understand these topics:
- HTTP and HTTPS
- HTTP methods: GET, POST, PUT, PATCH, DELETE
- HTTP status codes: 200, 201, 400, 401, 404, 500
- Headers and request bodies
- JSON serialization
- REST API principles
- Client-server architecture
- DNS, IP addresses and ports
- TCP basics
We'll learn these through practical exercises, not memorization.
Lesson 2: Set Up Your Backend Development Environment
We'll work on Windows using VS Code and PowerShell.
Step 1. Install Go










Go (Golang)

Programming language and compiler
Download Go

After installing, open PowerShell and execute:
go version


You should see something similar to:
go version go1.x.x windows/amd64


Step 2. Install VS Code extensions










Visual Studio Code
Download VS Code

Install these extensions:
- Go — official Go extension.
- REST Client — test APIs directly inside VS Code.
- Docker — manage containers later.
Step 3. Create your first backend project
Open PowerShell:
mkdir backend-engineering
cd backend-engineering

mkdir 01-url-shortener
cd 01-url-shortener

go mod init github.com/yourusername/url-shortener
code .


Create this folder structure:
01-url-shortener/
│
├── main.go
├── go.mod
│
├── handlers/
├── models/
├── routes/
├── services/
├── storage/
│
└── README.md


Initially, we'll keep the application in main.go. We'll introduce the other folders as the project grows.
Lesson 3: Build Your First HTTP Server
Let's write your first backend application.

Create main.go:

package main

import (
    "encoding/json"
    "log"
    "net/http"
)

type Response struct {
    Message string `json:"message"`
    Status  string `json:"status"`
}

func healthHandler(w http.ResponseWriter, r *http.Request) {

    w.Header().Set("Content-Type", "application/json")

    response := Response{
        Message: "Backend server is running!",
        Status:  "healthy",
    }

    json.NewEncoder(w).Encode(response)
}

func main() {

    http.HandleFunc("/health", healthHandler)

    log.Println("Server running on http://localhost:8080")

    err := http.ListenAndServe(":8080", nil)

    if err != nil {
        log.Fatal(err)
    }
}



Step 4. Run your server
In the VS Code terminal:
go run main.go


Expected output:
Server running on http://localhost:8080


Open your browser:
http://localhost:8080/healthExpected response:
{
  "message": "Backend server is running!",
  "status": "healthy"
}


Your first backend API
Congratulations! You've created an HTTP server and an API endpoint using Go's standard library without any backend framework.
7. Understand the code you just wrote
Code	What it does
package main	Defines an executable Go program
net/http	Provides HTTP server functionality
http.HandleFunc()	Registers a URL handler
http.ResponseWriter	Writes the HTTP response
*http.Request	Contains incoming request information
json.NewEncoder()	Converts Go data into JSON
ListenAndServe()	Starts the HTTP server

One important distinction: we're using Go's HTTP server library here. Later, we'll build a lower-level HTTP server using TCP sockets to understand what happens underneath.