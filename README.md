# Hotel Billing and Check-Out System

A Java mini project that automates hotel billing and check-out. Staff enter guest details, pick a room type and extra services, and the system calculates the bill and saves it to a MySQL database.

Built with OOP principles (encapsulation, inheritance, abstraction), with both a console interface and a JavaFX GUI.

## Features

- Guest details: name, phone, days of stay
- Room types with different rates
- Optional services: food, laundry, Wi-Fi
- Automatic bill calculation
- Console version and JavaFX GUI version
- Bills saved to MySQL through JDBC

## Pricing

| Room | Rate per day |
|------|--------------|
| Standard | ₹1000 |
| Deluxe | ₹2000 |
| Suite | ₹4000 |

| Service | Cost |
|---------|------|
| Food | ₹500 |
| Laundry | ₹300 |
| Wi-Fi | ₹200 |

**Total = (room rate × days) + selected services**

## Tech Stack

- Java (OOP)
- JavaFX 21
- MySQL + JDBC (MySQL Connector/J)

## Project Structure

```
src/Miniproject/
├── Customer.java            # Customer data and bill generation
├── Room.java                # Abstract Room + Standard, Deluxe, Suite
├── Services.java            # Food, laundry, Wi-Fi cost
├── HotelBillingSystem.java  # Console app
├── HotelBillingFx.java      # JavaFX GUI app
└── DBConnection.java        # JDBC connection
database/hotel_db.sql        # Database schema
```

## Setup

1. Install JDK 17+, JavaFX SDK 21, and MySQL.
2. Create the database:

```sql
CREATE DATABASE hotel_db;
USE hotel_db;

CREATE TABLE bills (
    id INT AUTO_INCREMENT PRIMARY KEY,
    customer_name VARCHAR(100),
    phone VARCHAR(15),
    room_type VARCHAR(20),
    days INT,
    room_charge DOUBLE,
    service_charge DOUBLE,
    total DOUBLE
);
```

3. Add MySQL Connector/J and the JavaFX SDK to your project libraries.
4. In `DBConnection.java`, set your own MySQL username and password.

## Run

**Console version:** run `HotelBillingSystem.java`

**GUI version:** run `HotelBillingFx.java` with the JavaFX modules:

```
--module-path path/to/javafx-sdk-21/lib --add-modules javafx.controls
```

## Future Work

- Online payment integration
- Room availability tracking
- Revenue reports and analytics
- Multi-user login

## Author

Mukesh P, B.Tech Artificial Intelligence and Data Science, Rajalakshmi Institute of Technology (Anna University)
