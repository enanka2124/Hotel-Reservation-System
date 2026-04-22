# 🏨 Hotel Reservation System

A Java-based desktop application that streamlines hotel room booking and management — enabling customers to reserve rooms while giving administrators full control over availability, bookings, and customer records.

[![Java](https://img.shields.io/badge/Java-100%25-orange?style=flat&logo=java)](https://www.java.com)
[![JDBC](https://img.shields.io/badge/Database-MySQL%20%2B%20JDBC-blue?style=flat&logo=mysql)](https://www.mysql.com)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-black?style=flat&logo=github)](https://github.com/enanka2124/Hotel-Reservation-System)

---

## 📌 Overview

The Hotel Reservation System is a Java application built to demonstrate core programming concepts including object-oriented design and relational database integration via JDBC. It manages the full lifecycle of a hotel booking — from checking room availability to recording reservations and maintaining customer records — with all data persisted in a MySQL database.

---

## ✨ Features

- **Customer Management** — Add, view, update, and remove customer records
- **Room Availability** — Real-time tracking of available and booked rooms
- **Booking Operations** — Make, modify, and cancel reservations with ease
- **JDBC Integration** — Persistent storage and efficient data retrieval via MySQL
- **Admin Operations** — Manage hotel inventory and reservation history

---

## 🛠️ Tech Stack

| Layer        | Technology                        |
|--------------|-----------------------------------|
| Language     | Java                              |
| Database     | MySQL                             |
| DB Connector | JDBC (Java Database Connectivity) |
| Architecture | Object-Oriented Programming (OOP) |

---

## 🗂️ Project Structure

```
Hotel-Reservation-System/
│
├── HotelReservationSystem/
│   ├── Main.java                  # Entry point
│   ├── Hotel.java                 # Core hotel management logic
│   ├── Room.java                  # Room model and availability
│   ├── Customer.java              # Customer data model
│   ├── Reservation.java           # Booking operations
│   └── DBConnection.java          # JDBC database connectivity
│
└── README.md
```

---

## ⚙️ Prerequisites

- Java Development Kit (JDK) 8 or higher
- MySQL Server (running locally or remotely)
- MySQL JDBC Driver (`mysql-connector-java.jar`)
- Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans) or command line

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/enanka2124/Hotel-Reservation-System.git
cd Hotel-Reservation-System
```

### 2. Set Up the Database

Start your MySQL server and create the required database and tables:

```sql
CREATE DATABASE hotel_db;
USE hotel_db;

CREATE TABLE customers (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    phone VARCHAR(15),
    email VARCHAR(100)
);

CREATE TABLE rooms (
    room_number INT PRIMARY KEY,
    type VARCHAR(50),
    price DECIMAL(10, 2),
    is_available BOOLEAN DEFAULT TRUE
);

CREATE TABLE reservations (
    reservation_id INT AUTO_INCREMENT PRIMARY KEY,
    customer_id INT,
    room_number INT,
    check_in DATE,
    check_out DATE,
    FOREIGN KEY (customer_id) REFERENCES customers(id),
    FOREIGN KEY (room_number) REFERENCES rooms(room_number)
);
```

### 3. Configure Database Connection

Update your `DBConnection.java` with your MySQL credentials:

```java
String url = "jdbc:mysql://localhost:3306/hotel_db";
String username = "your_mysql_username";
String password = "your_mysql_password";
```

### 4. Add JDBC Driver

Download the [MySQL Connector/J](https://dev.mysql.com/downloads/connector/j/) and add it to your project's classpath.

### 5. Run the Application

**Using an IDE:**  
Open the project and run `Main.java`

**Using the Command Line:**
```bash
javac -cp .:mysql-connector-java.jar HotelReservationSystem/*.java
java -cp .:mysql-connector-java.jar HotelReservationSystem.Main
```
> On Windows, replace `:` with `;` in the classpath

---

## 🖥️ Usage

1. **Launch** the application from your IDE or terminal
2. **Manage Customers** — Register new customers or look up existing records
3. **Check Room Availability** — Browse available rooms by type or date
4. **Make a Reservation** — Link a customer to an available room with check-in/check-out dates
5. **View / Cancel Bookings** — Retrieve reservation history or cancel existing bookings
6. All changes are **automatically persisted** to the MySQL database via JDBC

---

## 🏗️ Architecture

The project follows a **layered, modular OOP design**:

- **Model Layer** — `Customer.java`, `Room.java`, `Reservation.java` encapsulate data and business rules
- **Logic Layer** — `Hotel.java` orchestrates operations across models
- **Persistence Layer** — `DBConnection.java` handles all JDBC interactions with MySQL
- **Entry Point** — `Main.java` initializes the application and drives the user flow

---

## 🔗 Repository

[https://github.com/enanka2124/Hotel-Reservation-System](https://github.com/enanka2124/Hotel-Reservation-System)

---

## 📄 License

This project is built for educational purposes. Feel free to fork, explore, and build upon it.

---

## 👤 Author

**enanka2124**  
[GitHub Profile](https://github.com/enanka2124)
