
A Spring Boot backend service for managing logistics loads, built with PostgreSQL. This API supports CRUD operations for load management, including filtering by shipper, product type, and facility locations
## README - Documentation for API Project 

**Note:** I have used AI to format and structure this README file. The original notes were in my rough language, and I used AI to shape them professionally.

**Note:** I have used Lombok in the project, but due to some unexpected issues with it not generating getters and setters as expected, I manually added them to ensure smooth functionality.

### Project Overview
This project is a backend API system for managing loads in a logistics application. It is built using **Spring Boot** and **PostgreSQL** for relational database management. The API supports CRUD operations for load management.

### Database Configuration
- **`application.properties`**: Contains database configurations.
- Added **password** and configured **Hibernate to update** the database schema because PostgreSQL is a relational database. If MongoDB was used, schema updates would not be needed since it is schema-less.

### Project Structure

#### 1. **Entity Package (`entity/`)**
   - **`Loads.java`**: Represents the main `Loads` entity with all required fields.
   - **`Facility.java`**: Embedded entity inside `Loads` to store facility-related details.

#### 2. **Controller Package (`controller/`)**
   - **`LoadController.java`**: Handles API requests for managing loads.
   - Endpoints:
     - `POST /load` - Create a new load
     - `GET /load` - Retrieve all loads
     - `GET /load/{loadId}` - Retrieve a load by ID
     - `GET /load/shipper/{shipperId}` - Retrieve loads by `shipperId`
     - `PUT /load/{loadId}` - Update a load
     - `DELETE /load/{loadId}` - Delete a load

#### 3. **Repository Package (`repository/`)**
   - **`LoadRepository.java`**: Interface extending `JpaRepository` for database operations.
   - Contains custom queries like `findByShipperId`, `findByFacilityLoadingPoint`, etc.

#### 4. **Service Package (`service/`)**
   - **`LoadsService.java`**: Implements business logic for managing loads.
   - Handles creation, retrieval, updating, and deletion of loads.

#### 5. **Exception Handling (`exception/`)**
   - **`GlobalExceptionHandler.java`**: Manages exceptions globally using `@ControllerAdvice`.
   - **`ErrorResponse.java`**: Defines the structure for error messages.

### Steps Followed in Development
1. **Created entity classes (`Loads`, `Facility`)** to define the data structure.
2. **Implemented the repository (`LoadRepository`)** to interact with the database.
3. **Developed service methods (`LoadsService`)** to process business logic.
4. **Built the controller (`LoadController`)** to expose REST APIs.
5. **Added exception handling (`GlobalExceptionHandler`)** to handle errors gracefully.
6. **Tested APIs using Postman or cURL** to verify correctness.



This README provides a structured overview of the project, its components, and how it was developed. 🚀

