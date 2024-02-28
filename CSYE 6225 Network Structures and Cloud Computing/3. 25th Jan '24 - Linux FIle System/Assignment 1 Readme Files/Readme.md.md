# Health Check API - Assignment 2

## Overview

This project implements a health check API as part of Assignment 2. The API is built using Node.js, Express, and TypeScript, with route generation handled by `tsoa`. The primary function of this API is to monitor the health of the application, ensuring connectivity and operational status.

## Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

- Node.js
- npm (Node Package Manager)

### Clone the Repository

Clone the project repository to your local machine via SSH. Use the command:
    `git clone git@github.com:parthasarathydNU/cloud-assignments.git

### Running the Application

Use the `start-demo` script to build and start the application. This script will:

- Install all dependencies (`npm i`)
- Generate routes using `tsoa` (`npm run generate-tsoa`)
- Build the project (`npm run build`)
- Start the application (`npm run start`)

Run the script using: `npm run start-demo`

## Features

- **Health Check Endpoint**: Provides a `/healthz` GET endpoint to check the application's health, ensuring database connectivity and operational status.
- **Automatic Route Generation**: Utilizes `tsoa` for automatic generation of Express routes based on TypeScript decorators.
- **Error Handling**: Includes handling for 405 Method Not Allowed errors, ensuring the API responds appropriately to unsupported HTTP methods on the `/healthz` endpoint.

## API Endpoints

- `GET /healthz`: Checks the health of the application and returns an HTTP 200 status code if healthy, or HTTP 503 if there are issues with the database connectivity.

### Output 

When database is connected and we do a GET request
```shell
curl -vvvv  http://localhost:3000/healthz
*   Trying 127.0.0.1:3000...
* Connected to localhost (127.0.0.1) port 3000 (#0)
> GET /healthz HTTP/1.1
> Host: localhost:3000
> User-Agent: curl/7.84.0
> Accept: */*
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< X-Powered-By: Express
< cache-control: no-cache
< Date: Mon, 29 Jan 2024 05:56:32 GMT
< Connection: keep-alive
< Keep-Alive: timeout=5
< Content-Length: 0
<
* Connection #0 to host localhost left intact
```


When database is disconnected
```shell
curl -vvvv  http://localhost:3000/healthz
*   Trying 127.0.0.1:3000...
* Connected to localhost (127.0.0.1) port 3000 (#0)
> GET /healthz HTTP/1.1
> Host: localhost:3000
> User-Agent: curl/7.84.0
> Accept: */*
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 503 Service Unavailable
< X-Powered-By: Express
< cache-control: no-cache
< Date: Mon, 29 Jan 2024 05:56:07 GMT
< Connection: keep-alive
< Keep-Alive: timeout=5
< Content-Length: 0
<
* Connection #0 to host localhost left intact
```


When a different method apart from GET is used
```shell
 curl -vvvv -XPUT http://localhost:3000/healthz
*   Trying 127.0.0.1:3000...
* Connected to localhost (127.0.0.1) port 3000 (#0)
> PUT /healthz HTTP/1.1
> Host: localhost:3000
> User-Agent: curl/7.84.0
> Accept: */*
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 405 Method Not Allowed
< X-Powered-By: Express
< cache-control: no-cache
< Date: Mon, 29 Jan 2024 05:56:16 GMT
< Connection: keep-alive
< Keep-Alive: timeout=5
< Content-Length: 0
<
* Connection #0 to host localhost left intact
```