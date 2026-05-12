# 🍔 Food Delivery Microservices Application

![Java](https://img.shields.io/badge/Java-21-orange)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.2-green)
![MySQL](https://img.shields.io/badge/MySQL-8.0-blue)

> A production-grade, distributed Food Delivery Backend built with **Spring Boot Microservices Architecture** — similar to how **Swiggy** and **Zomato** work behind the scenes.

---

## 📌 What Problem Does This Solve?

Traditional food delivery apps need to handle:
- Thousands of users registering and logging in simultaneously
- Hundreds of restaurants being added and browsed
- Millions of orders being placed and tracked in real time

This project solves that by using **Microservices Architecture** — splitting the app into 3 independent services that can run and scale separately.

---

## 🏗️ System Architecture

```
User Service (8081)  -->  Restaurant Service (8082)  -->  Order Service (8083)
       |                          |                              |
       |                          |                              |
       v                          v                              v
   [ userdb ]              [ restaurantdb ]                 [ orderdb ]
                               MySQL Database
```

Each service has its own database and runs independently!

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Language | Java 21 |
| Framework | Spring Boot 3.2 |
| Architecture | Microservices |
| ORM | Hibernate / JPA |
| Security | Spring Security (RBAC) |
| Database | MySQL 8.0 |
| API Testing | Postman |
| Build Tool | Maven |
| Version Control | Git & GitHub |

---

## 📦 Microservices Overview

### 👤 User Service (Port: 8081)
Handles everything related to users — registration, authentication, and role-based access control using Spring Security.

### 🍽️ Restaurant Service (Port: 8082)
Manages restaurant data — adding new restaurants, browsing by location or cuisine type.

### 📦 Order Service (Port: 8083)
Handles the complete order lifecycle — placing orders, updating status (PENDING → CONFIRMED → DELIVERED).

---

## 🚀 API Endpoints

### 👤 User Service
| Method | Endpoint | Description |
|---|---|---|
| POST | /api/users/register | Register new user |
| GET | /api/users | Get all users |
| GET | /api/users/{id} | Get user by ID |
| DELETE | /api/users/{id} | Delete user |

### 🍽️ Restaurant Service
| Method | Endpoint | Description |
|---|---|---|
| POST | /api/restaurants | Add new restaurant |
| GET | /api/restaurants | Get all restaurants |
| GET | /api/restaurants/{id} | Get restaurant by ID |
| GET | /api/restaurants/cuisine/{cuisine} | Filter by cuisine |
| GET | /api/restaurants/location/{location} | Filter by location |
| DELETE | /api/restaurants/{id} | Delete restaurant |

### 📦 Order Service
| Method | Endpoint | Description |
|---|---|---|
| POST | /api/orders | Place new order |
| GET | /api/orders | Get all orders |
| GET | /api/orders/{id} | Get order by ID |
| GET | /api/orders/user/{userId} | Get orders by user |
| PUT | /api/orders/{id}/status | Update order status |
| DELETE | /api/orders/{id} | Delete order |

---

## ⚙️ How to Run This Project

### Prerequisites
- Java 17 or above
- MySQL 8.0
- Maven
- Postman

### Step 1 - Clone the Repository
```bash
git clone https://github.com/Dharsanboya/food-delivery-microservices.git
```

### Step 2 - Create MySQL Databases
```sql
CREATE DATABASE userdb;
CREATE DATABASE restaurantdb;
CREATE DATABASE orderdb;
```

### Step 3 - Run Each Service
```
user-service       → UserServiceApplication.java       → Port 8081
restaurant-service → RestaurantServiceApplication.java → Port 8082
order-service      → OrderServiceApplication.java      → Port 8083
```

### Step 4 - Test with Postman

**Register a user:**
```json
POST http://localhost:8081/api/users/register
{
  "name": "Dharsan",
  "email": "dharsan@gmail.com",
  "password": "123456"
}
```

**Add a restaurant:**
```json
POST http://localhost:8082/api/restaurants
{
  "name": "Spice Garden",
  "location": "Bangalore",
  "cuisine": "Indian",
  "contactNumber": "9876543210"
}
```

**Place an order:**
```json
POST http://localhost:8083/api/orders
{
  "userId": 1,
  "restaurantId": 1,
  "foodItems": "Biryani, Naan",
  "totalAmount": 450.00
}
```

---

## 📁 Project Structure

```
food-delivery-microservices/
├── user-service/
│   └── src/main/java/com/fooddelivery/userservice/
│       ├── controller/
│       ├── service/
│       ├── repository/
│       ├── model/
│       └── config/
├── restaurant-service/
│   └── src/main/java/com/fooddelivery/restaurantservice/
│       ├── controller/
│       ├── service/
│       ├── repository/
│       └── model/
├── order-service/
│   └── src/main/java/com/fooddelivery/orderservice/
│       ├── controller/
│       ├── service/
│       ├── repository/
│       └── model/
└── pom.xml
```

---

## 👨‍💻 Developer

**Dharsan Boya** — Java Backend Developer

- 📧 dharsanboya96@gmail.com
- 🔗 [LinkedIn](https://www.linkedin.com/in/dharsanboya/)
- 💻 [GitHub](https://github.com/Dharsanboya)

---

⭐ If you found this project helpful, please give it a star!
