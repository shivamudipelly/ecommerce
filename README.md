# 🛍️ E-Commerce Platform

> A full-featured e-commerce application built with Java and Spring Boot

[![Java](https://img.shields.io/badge/Java-17+-orange?style=flat&logo=java&logoColor=white)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.0+-green?style=flat&logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Installation](#installation)
- [Running the Application](#running-the-application)
- [API Documentation](#api-documentation)
- [Database Schema](#database-schema)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

This is a comprehensive e-commerce platform built using **Java** and **Spring Boot**. The application provides a complete end-to-end solution for online shopping, including product catalog management, shopping cart, order processing, and user authentication.

The platform is designed with scalability and performance in mind, using best practices in software architecture and database design.

## ✨ Features

- ✅ User Registration and Authentication
- ✅ Product Catalog with Categories
- ✅ Shopping Cart Management
- ✅ Order Processing and Management
- ✅ Payment Integration
- ✅ User Profile Management
- ✅ Order History and Tracking
- ✅ Admin Dashboard for Product Management
- ✅ Search and Filter Functionality
- ✅ Reviews and Ratings System
- ✅ RESTful API for Mobile Apps
- ✅ Secure Data Handling

## 🛠 Tech Stack

### Backend
- **Java 17+** - Programming Language
- **Spring Boot 3.0+** - Web Framework
- **Spring Data JPA** - ORM and Database Access
- **Spring Security** - Authentication and Authorization
- **MySQL/PostgreSQL** - Relational Database
- **Maven** - Dependency Management
- **REST API** - Backend API Design

### Tools & Libraries
- **Lombok** - Reduce Boilerplate Code
- **Validation** - Input Validation
- **JWT** - Token-Based Authentication
- **Docker** - Containerization

## 📁 Project Structure

```
ecommerce/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/ecommerce/
│   │   │       ├── config/          # Spring Configurations
│   │   │       ├─┐ controller/      # REST Controllers
│   │   │       ├─┐ service/         # Business Logic
│   │   │       ├─┐ repository/      # Data Access Layer
│   │   │       ├─┐ model/           # Entity Classes
│   │   │       ├─┐ dto/             # Data Transfer Objects
│   │   │       ├─┐ exception/       # Custom Exceptions
│   │   │       ├─┐ util/            # Utility Classes
│   │   │       └─┐ EcommerceApplication.java
│   │   ├─┐ resources/
│   │       ├─┐ application.properties
│   │       └─┐ application-{env}.properties
│   └─┐ test/               # Unit and Integration Tests
│
├─┐ pom.xml              # Maven Configuration
├─┐ Dockerfile           # Docker Configuration
├─┐ docker-compose.yml   # Docker Compose Setup
└─┐ README.md            # This file
```

## 🚀 Getting Started

### Prerequisites

- Java 17 or Higher
- Maven 3.8.0 or Higher
- MySQL 8.0 or PostgreSQL 12+
- Git

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/shivamudipelly/ecommerce.git
   cd ecommerce
   ```

2. **Configure Database**
   
   Update `src/main/resources/application.properties`:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/ecommerce_db
   spring.datasource.username=your_username
   spring.datasource.password=your_password
   spring.jpa.hibernate.ddl-auto=update
   ```

3. **Build the Project**
   ```bash
   mvn clean install
   ```

## ▶️ Running the Application

### Using Maven

```bash
mvn spring-boot:run
```

The application will start on `http://localhost:8080`

### Using Docker

1. **Build Docker Image**
   ```bash
   docker build -t ecommerce:latest .
   ```

2. **Run Docker Container**
   ```bash
   docker run -p 8080:8080 --name ecommerce-app ecommerce:latest
   ```

### Using Docker Compose

```bash
docker-compose up -d
```

## 🔌 API Documentation

### Authentication Endpoints

- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login user
- `POST /api/auth/logout` - Logout user
- `POST /api/auth/refresh-token` - Refresh authentication token

### Product Endpoints

- `GET /api/products` - Get all products with pagination
- `GET /api/products/{id}` - Get product by ID
- `GET /api/products/category/{categoryId}` - Get products by category
- `POST /api/products` - Create new product (Admin)
- `PUT /api/products/{id}` - Update product (Admin)
- `DELETE /api/products/{id}` - Delete product (Admin)

### Cart Endpoints

- `GET /api/cart` - Get user's shopping cart
- `POST /api/cart/items` - Add item to cart
- `PUT /api/cart/items/{itemId}` - Update cart item quantity
- `DELETE /api/cart/items/{itemId}` - Remove item from cart
- `DELETE /api/cart` - Clear entire cart

### Order Endpoints

- `GET /api/orders` - Get user's orders
- `GET /api/orders/{id}` - Get order details
- `POST /api/orders` - Create new order
- `PUT /api/orders/{id}` - Update order status (Admin)
- `DELETE /api/orders/{id}` - Cancel order

### Category Endpoints

- `GET /api/categories` - Get all product categories
- `GET /api/categories/{id}` - Get category details
- `POST /api/categories` - Create category (Admin)
- `PUT /api/categories/{id}` - Update category (Admin)
- `DELETE /api/categories/{id}` - Delete category (Admin)

## 📋 Database Schema

### Key Tables

- **users** - User account information
- **products** - Product catalog
- **categories** - Product categories
- **shopping_cart** - User shopping carts
- **cart_items** - Items in shopping carts
- **orders** - Customer orders
- **order_items** - Items in orders
- **reviews** - Product reviews and ratings
- **payments** - Payment information

## 😀 Sample Configuration

### application.properties

```properties
# Server Configuration
server.port=8080
server.servlet.context-path=/api

# Database Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/ecommerce_db
spring.datasource.username=root
spring.datasource.password=password
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=false

# JPA Configuration
spring.jpa.database-platform=org.hibernate.dialect.MySQL8Dialect
spring.jpa.properties.hibernate.format_sql=true

# Logging
logging.level.root=INFO
logging.level.com.ecommerce=DEBUG
```

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📄 Additional Notes

- This is a Spring Boot 3.0+ application
- All database migrations are handled by Hibernate
- JWT is used for API authentication
- The application follows REST API best practices
- CORS is enabled for frontend communication

---

<div align="center">
  Made with ❤️ by Shiva Mudipelly<br/>
  <a href="https://github.com/shivamudipelly">GitHub</a> • <a href="https://linkedin.com/in/shivamudipelly">LinkedIn</a>
</div>
