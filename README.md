# ⚽ Football Ticket Booking System - Database Design & SQL Queries

## 📖 Overview

This project is a simplified **Football Ticket Booking System** designed to demonstrate database design principles, ERD modeling, and SQL query writing.

The assignment focuses on:

* Database schema design
* Entity Relationship Diagram (ERD)
* Primary Key and Foreign Key relationships
* Referential Integrity
* SQL filtering and pattern matching
* JOIN operations
* Subqueries
* Aggregate functions
* NULL handling
* Pagination techniques

---

## 🎯 Learning Objectives

By completing this project, I was able to:

* Design an ERD with One-to-Many and Many-to-One relationships.
* Understand Primary Keys (PK) and Foreign Keys (FK).
* Maintain Referential Integrity between tables.
* Write SQL queries using:

  * WHERE
  * LIKE / ILIKE
  * IS NULL
  * COALESCE
  * INNER JOIN
  * LEFT JOIN
  * Aggregate Functions
  * Subqueries
  * ORDER BY
  * LIMIT & OFFSET

---

# 🗂 Database Schema

## 1. Users Table

Stores all football fans and ticket managers.

| Field Name   | Description                    |
| ------------ | ------------------------------ |
| user_id      | Unique user identifier         |
| full_name    | Full name of the user          |
| email        | User email address             |
| role         | Football Fan or Ticket Manager |
| phone_number | Contact number                 |

---

## 2. Matches Table

Stores football match information.

| Field Name          | Description                                  |
| ------------------- | -------------------------------------------- |
| match_id            | Unique match identifier                      |
| fixture             | Competing teams                              |
| tournament_category | Tournament name                              |
| base_ticket_price   | Base ticket price                            |
| match_status        | Available, Selling Fast, Sold Out, Postponed |

---

## 3. Bookings Table

Stores ticket purchase records.

| Field Name     | Description                             |
| -------------- | --------------------------------------- |
| booking_id     | Unique booking identifier               |
| user_id        | References Users table                  |
| match_id       | References Matches table                |
| seat_number    | Allocated seat number                   |
| payment_status | Pending, Confirmed, Cancelled, Refunded |
| total_cost     | Final booking cost                      |

---

# 🔗 Entity Relationships

### One-to-Many

One User can have many Bookings.

```text
Users (1) --------< Bookings (M)
```

### Many-to-One

Many Bookings can belong to one Match.

```text
Bookings (M) >-------- (1) Matches
```

### Logical One-to-One

Each booking record maps exactly one User to one Match for a specific seat reservation.

---

# 🧩 ERD Diagram

The ERD includes:

* Primary Keys (PK)
* Foreign Keys (FK)
* Relationship Cardinality
* Status Fields

ERD Link:

```text
https://drawsql.app/teams/mdshahid-hossain/diagrams/football-ticket-booking-system
```

---

# 📝 Sample Data

## Users

| user_id | full_name     | email                                     | role           |
| ------- | ------------- | ----------------------------------------- | -------------- |
| 1       | Tanvir Rahman | [tanvir@mail.com](mailto:tanvir@mail.com) | Football Fan   |
| 2       | Asif Haque    | [asif@mail.com](mailto:asif@mail.com)     | Football Fan   |
| 3       | Sajjad Rahman | [sajjad@mail.com](mailto:sajjad@mail.com) | Ticket Manager |
| 4       | Jannat Ara    | [jannat@mail.com](mailto:jannat@mail.com) | Football Fan   |

---

## Matches

| match_id | fixture                  | tournament_category | base_ticket_price | match_status |
| -------- | ------------------------ | ------------------- | ----------------- | ------------ |
| 101      | Real Madrid vs Barcelona | Champions League    | 150               | Available    |
| 102      | Man City vs Liverpool    | Premier League      | 120               | Selling Fast |
| 103      | Bayern Munich vs PSG     | Champions League    | 130               | Available    |
| 104      | AC Milan vs Inter Milan  | Serie A             | 90                | Sold Out     |
| 105      | Juventus vs Roma         | Serie A             | 80                | Available    |

---

## Bookings

| booking_id | user_id | match_id | seat_number | payment_status | total_cost |
| ---------- | ------- | -------- | ----------- | -------------- | ---------- |
| 501        | 1       | 101      | A-12        | Confirmed      | 150        |
| 502        | 1       | 102      | B-04        | Confirmed      | 120        |
| 503        | 2       | 101      | A-13        | Confirmed      | 150        |
| 504        | 2       | 101      | NULL        | NULL           | 150        |
| 505        | 3       | 102      | C-20        | Pending        | 120        |

---

# 💻 SQL Queries Implemented

### Query 1

Retrieve all available Champions League matches.

### Query 2

Search users using LIKE and ILIKE.

### Query 3

Handle NULL payment statuses using COALESCE.

### Query 4

Retrieve booking details using INNER JOIN.

### Query 5

Display all users and their bookings using LEFT JOIN.

### Query 6

Find bookings with costs above the average booking cost.

### Query 7

Retrieve top expensive matches using ORDER BY, LIMIT, and OFFSET.

---

# 🛠 Technologies Used

* PostgreSQL
* SQL
* DrawSQL (ERD Design)

---

# 📂 Project Structure

```text
Football-Ticket-Booking-System/
│
├── README.md
├── QUERY.sql


---

# 👨‍💻 Author

**Md. Shahid Hossain**

Full Stack Web Developer

* React.js
* Tailwind CSS
* JavaScript
* Node.js
* Express.js
* PostgreSQL
* TypeScript
