# REST API Design Guide

## Overview

This document is used as a guide for designing RESTful APIs adhering to the Representational State Transfer (REST) architectural style. It outlines key principles, HTTP methods, and differences between PUT and PATCH methods.

## Key Principles of REST API

1. **Resource Oriented**: 
    - Resource: The key abstraction of information in REST is a resource. Any information that we can name can be a resource. 
    - RESTful APIs treat data as resources accessible via unique URIs, allowing manipulation using standard HTTP methods.

2. **Uniform Interface**: 
    - Standardized HTTP methods promote simplicity and visibility of interactions between client and server components.

3. **Client-Server**:
    - Separation of concerns enables independent evolution of client and server components.

4. **Stateless**:
    - Each request from client to server contains all necessary information, enhancing scalability and reliability.

5. **Architectural Style**: 
    - REST is an architectural style, not a protocol, emphasizing the use of HTTP methods for communication.

## HTTP Methods

1. **GET**: 
    - Retrieve resources (as like READ from the database)

2. **POST**: 
    - Create new resources (as like CREATE a record into the database)

3. **DELETE**: 
    - Remove resources (as like DELETE a record from the database)

4. **PUT/PATCH**: 
    - Update resource

    **Difference between PUT and PATCH**:

    |FEATURE| PUT | PATCH |
    |-------|--------|-------------|
    |updation| Replace the entire resource with the new representation.    | Applies partial modifications to the resource. |
    |Idempotent | YES | NO |
    |Used | Complete Updates | Partial Updates |
    |Request Body| Contains new representation |Contains only changes to be applied |
   
    Although it's not mandatory to strictly adhere to HTTP methods for CRUD operations, maintaining consistency and adhering to conventions improves readability and uniformity across APIs.
----
## Some of the Best Practices for Designing REST API
1. Use JSON as the Format for Sending and Receiving Data
2. Name Collections with Plural Nouns
3. Use Nouns Instead of Verbs in Endpoints
  - e.g Bad Pratices : https://inventoyreader/book
  - e.g Should Have: https://inventoryreader/books
4. Use Status Codes in Error Handling
 ![image](https://github.com/amey1302/RESTAPINotes/assets/114746925/65bcdb31-a918-4d95-acae-799c446aca4d) 
  - credits https://www.freecodecamp.org/news/rest-api-best-practices-rest-endpoint-design-examples/
5. Be clear with versioning
  - for version 1 https://inventoryreader/v1, it's not mandatory to use this but most tech giants do the same.
6. Don’t expose internal errors or implementation details, for the SQL error instead of as SQL Error provide as Internal server error
7. Use objects for fields that could need more information in the future
