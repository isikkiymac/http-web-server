# Multi-Function HTTP Web Server

A production-grade HTTP/1.0 web server built from scratch in C, featuring a 3-tier architecture for serving both static and dynamic content.

## Overview
Built as part of Columbia University's Computer Systems course (COMS 3157). The server handles concurrent client connections over TCP, serves static files from a web root, and integrates with a backend MDB lookup service for dynamic content.

## Tech Stack
- **Language:** C
- **Protocols:** HTTP/1.0, TCP/IP
- **System Calls:** socket, bind, listen, accept, recv, send, fork
- **Tools:** Make, Valgrind (memory-checked, zero leaks)

## Key Features
- **Static file serving** with correct MIME handling and binary file support
- **Dynamic content** via integration with a separate MDB lookup server
- **Directory traversal protection** (blocks `/../` and `/..` attacks)
- **Comprehensive request logging** to stderr with client IP, request line, and status code
- **Proper HTTP status codes:** 200 OK, 400 Bad Request, 403 Forbidden, 404 Not Found, 501 Not Implemented
- **Modular routing** and error-handling middleware
- **Low-latency I/O** via buffered reads/writes and efficient socket handling
- **3-tier architecture:** client → web server → backend service

## Architecture
Client → HTTP Server (port X) → MDB Lookup Server (port Y)
↓
Static files (web_root)


## What I Learned
- Socket programming and TCP connection lifecycle
- HTTP protocol internals (request parsing, headers, status codes)
- Security best practices (path traversal, input validation)
- Process management with fork/exec
- Memory management and debugging with Valgrind

## Note
This project was completed for a course. Source code is available upon request due to course policy restrictions. I'm happy to walk through the architecture, design decisions, and implementation details in an interview.
