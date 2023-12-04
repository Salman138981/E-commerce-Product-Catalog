# E-commerce-Product-Catalog
* A Java-based web application for managing an e-commerce product catalog. This project leverages the Spring Boot framework, Hibernate for database interaction, and MySQL as the underlying database. The system allows users to seamlessly add, update, and remove products within specified categories.

## Tech Stack
* Java
* Srping Boot
* Hibernate
* MySQL

## Installation & Run 
* Before running the API server, you should update the database config inside the application.properties file.
* Update the port number, username and password as per your local database config.

```
spring.datasource.url=jdbc:mysql://localhost:3306/database
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
spring.datasource.username=root
spring.datasource.password=root

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```
## API Documentation

Explore the API endpoints to understand how to interact with the system. The documentation includes request and response examples for each endpoint.

### 1. Get All Products of a Category

#### Endpoint

```http
GET /api/categories/products{categoryName}
```

#### Example
##### Request
```
GET /api/categories/products/Electronics
```
##### Response
```
[
  {
    "id": 1,
    "productName": "Iphone",
    "price": 70000,
    "rating": 5
  },
  {
    "id": 4,
    "productName": "tablet",
    "price": 10000,
    "rating": 4
  }
]
```
### 2. Add a Product to a Category

#### Endpoint

```http
POST /api/categories/{categoryId}/products/{productId}
```

#### Example
##### Request
```
POST /api/categories/1/products/4
```
##### Response
```
{
  "id": 4,
  "productName": "tablet",
  "price": 10000,
  "rating": 4
}
```
### 3. Remove a Product from Category

#### Endpoint

```http
DELETE /api/categories/{categoryId}/products/{productId}
```

#### Example
##### Request
```
DELETE /api/categories/2/products/4
```
##### Response
```
{
  "id": 4,
  "productName": "tablet",
  "price": 10000,
  "rating": 4
}
```
