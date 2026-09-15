# 🚍 Train/Bus Seat Booking Simulator — Java

A command-line Java application that simulates a real-world transport seat booking system. The application supports both trains and buses, with a visual seat map, seat booking, cancellation, route search, ticket viewing, statistics, and CSV-based data persistence.

## 👩‍💻 Author

**Sandhya Kumari**
B.Tech CSE — Cyber Security & Digital Forensics
VIT Bhopal University
Course: Programming in Java

---

## 📌 Problem Statement

Booking seats in real transport systems involves complex logic such as tracking seat availability, assigning seat types, handling cancellations, and maintaining booking records.

This project simulates a transport seat booking system using Java and demonstrates how Object-Oriented Programming can be applied to solve a real-world problem.

---

## ✨ Features

| Feature            | Description                                                          |
| ------------------ | -------------------------------------------------------------------- |
| 🔍 Search by Route | Find trains/buses between two cities with availability               |
| 💺 Book a Seat     | Choose a specific seat or automatically assign a preferred seat type |
| ❌ Cancel Booking   | Cancel an active booking using Booking ID                            |
| 🪑 Seat Map        | Display available and booked seats using an ASCII seat map           |
| 🚆 All Vehicles    | View all available trains and buses with occupancy                   |
| 👤 My Bookings     | Search bookings using passenger name or phone                        |
| 🎫 View Ticket     | Display complete ticket details using Booking ID                     |
| 📊 Statistics      | View bookings, cancellations, revenue and occupancy                  |
| 💾 Persistence     | Store bookings and seat states using CSV files                       |

---

## 📂 Project Structure

```text
SeatBookingSimulator/
│
├── src/
│   └── booking/
│       ├── Main.java
│       ├── BookingManager.java
│       ├── Vehicle.java
│       ├── Seat.java
│       ├── Booking.java
│       ├── FileManager.java
│       ├── InputHelper.java
│       ├── SeatType.java
│       └── TransportType.java
│
├── data/
│   ├── bookings.csv
│   └── seat_state.csv
│
└── README.md
```

### Class Description

* **Main.java** — Provides the command-line interface and main menu.
* **BookingManager.java** — Handles searching, booking, cancellation and statistics.
* **Vehicle.java** — Represents trains and buses and manages their seat layouts.
* **Seat.java** — Represents an individual seat and its booking status.
* **Booking.java** — Stores passenger and ticket information.
* **FileManager.java** — Handles CSV-based persistent storage.
* **InputHelper.java** — Validates user input.
* **SeatType.java** — Enum representing Window, Middle and Aisle seats.
* **TransportType.java** — Enum representing Train and Bus transportation.

---

## 🚆 Pre-loaded Routes

### Trains

| ID   | Name             | Route               |  Fare |
| ---- | ---------------- | ------------------- | ----: |
| TR01 | Rajdhani Express | Delhi → Mumbai      | ₹1500 |
| TR02 | Shatabdi Express | Delhi → Jaipur      |  ₹800 |
| TR03 | Duronto Express  | Mumbai → Pune       |  ₹450 |
| TR04 | Garib Rath       | Kolkata → Delhi     |  ₹700 |
| TR05 | Vande Bharat     | Chennai → Bengaluru | ₹1200 |

### Buses

| ID   | Name                | Route                  | Fare |
| ---- | ------------------- | ---------------------- | ---: |
| BS01 | KSRTC Airavat Volvo | Bengaluru → Mysuru     | ₹350 |
| BS02 | MSRTC Shivneri      | Mumbai → Pune          | ₹300 |
| BS03 | APSRTC Garuda       | Hyderabad → Vijayawada | ₹550 |
| BS04 | RSRTC Volvo         | Jaipur → Delhi         | ₹650 |
| BS05 | HRTC Volvo          | Delhi → Shimla         | ₹750 |

---

## 🪑 Seat Layout

### Train

Each row contains 6 seats:

```text
W M A | A M W
```

Where:

* **W** = Window
* **M** = Middle
* **A** = Aisle

Example:

```text
Row   W   M   A | A   M   W
─────────────────────────────
  1   W   M  [A]| A   M   W
  2   W   M   A |[A]  M   W
  3  [W]  M   A | A   M  [W]
```

`[X]` represents a booked seat.

### Bus

Each row contains 4 seats:

```text
W A | A W
```

---

## ☕ Java Concepts Used

| Java Concept                | Application                            |
| --------------------------- | -------------------------------------- |
| Object-Oriented Programming | Model and logic classes                |
| Encapsulation               | Private fields with methods            |
| Enums                       | Seat types and transport types         |
| ArrayList                   | Vehicles, seats and bookings           |
| Optional<T>                 | Searching vehicles, seats and bookings |
| Streams & Lambdas           | Filtering, searching and aggregation   |
| File I/O                    | CSV persistence                        |
| Exception Handling          | Input and file error handling          |
| Switch Expressions          | Menu and selection handling            |
| String Formatting           | Seat maps and ticket display           |
| java.time API               | Booking timestamps                     |

---

## 🛠️ Technologies Used

* **Language:** Java
* **JDK:** 17 or above
* **Interface:** Command Line Interface (CLI)
* **Storage:** CSV files
* **Programming Paradigm:** Object-Oriented Programming

---

## 📋 Prerequisites

Install:

```text
Java JDK 17 or above
```

Check your Java version:

```bash
java -version
javac -version
```

---

## ▶️ How to Run

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/SeatBookingSimulator.git
```

Navigate to the project:

```bash
cd SeatBookingSimulator
```

Create the output directory:

```bash
mkdir out
```

Compile the Java files:

```bash
javac -d out src/booking/*.java
```

Run the application:

```bash
java -cp out booking.Main
```

The `data/` directory is automatically used for storing booking and seat information.

---

## 💾 Data Persistence

The application stores booking information and seat states in CSV files:

```text
data/
├── bookings.csv
└── seat_state.csv
```

This allows booking information and seat availability to remain available across application sessions.

---

## 📊 Sample Seat Map

```text
Seat Map — Rajdhani Express (Train)

Legend: [X] = Booked
        W   = Window
        M   = Middle
        A   = Aisle

──────────────────────────────────────────────────
Row   W   M   A | A   M   W
──────────────────────────────────────────────────
  1   W   M  [A]| A   M   W
  2   W   M   A |[A]  M   W
  3  [W]  M   A | A   M  [W]
──────────────────────────────────────────────────

Available: 54
Booked: 6
Total: 60
```

---

## 🚀 Future Improvements

The project can be extended with:

* Date-based booking
* Different fare classes
* Sleeper, 3AC and 2AC categories
* Waitlist management
* JavaFX graphical user interface
* PDF ticket generation
* Online payment simulation
* Admin dashboard
* Login and user authentication

---

## 🎯 Learning Outcome

Through this project, I gained practical experience in:

* Java Object-Oriented Programming
* Classes and objects
* Encapsulation
* Collections
* Enums
* Exception handling
* File handling
* Java Streams and Lambda expressions
* CLI application development
* Designing a real-world software system

---

## 📜 License

This project is created for educational purposes as part of the **Programming in Java** course.

---

## 👩‍🎓 Student

**Sandhya Kumari**
**B.Tech CSE — Cyber Security & Digital Forensics**
**VIT Bhopal University**
