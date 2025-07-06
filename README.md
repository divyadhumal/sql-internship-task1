# 📚 Library Database Schema Design (PostgreSQL)

This project is part of my internship task. It demonstrates the creation of a relational database schema for managing a library system using PostgreSQL. It includes table creation, inserting sample records, defining relationships, and generating an ER diagram.

---

## ✅ Objective

- Design a normalized relational database for a Library System
- Create tables: Books, Members, and Borrow
- Define relationships using Primary and Foreign Keys
- Populate with sample data
- Generate and attach an ER diagram

---

## 🛠 Tools Used

- PostgreSQL with pgAdmin
- dbdiagram.io (for ER diagram)
- Markdown for documentation

---

## 🧱 Tables and Structure

### 📘 Books Table

| Column         | Data Type    | Description                  |
|----------------|--------------|------------------------------|
| `book_id`      | SERIAL       | Primary Key, auto-generated  |
| `title`        | VARCHAR(100) | Book title                   |
| `author`       | VARCHAR(100) | Author name                  |
| `category`     | VARCHAR(50)  | Book category/genre          |
| `published_year` | INT        | Year the book was published  |

---

### 👤 Members Table

| Column      | Data Type     | Description                   |
|-------------|---------------|-------------------------------|
| `member_id` | SERIAL        | Primary Key, auto-generated   |
| `name`      | VARCHAR(100)  | Name of the member            |
| `email`     | VARCHAR(100)  | Unique email address          |
| `phone`     | VARCHAR(15)   | Contact number                |

---

### 🔁 Borrow Table

| Column       | Data Type | Description                                 |
|--------------|-----------|---------------------------------------------|
| `borrow_id`  | SERIAL    | Primary Key, auto-generated                 |
| `book_id`    | INT       | Foreign Key referencing `Books(book_id)`    |
| `member_id`  | INT       | Foreign Key referencing `Members(member_id)`|
| `borrow_date`| DATE      | Date the book was borrowed                  |
| `return_date`| DATE      | Date the book was returned (nullable)       |

---

## 🔗 Relationships

- A **Member** can borrow many **Books**
- A **Book** can be borrowed by many **Members**
- Relationship is handled via the `Borrow` table

---

## 📷 ER Diagram

> Generated using [dbdiagram.io](https://dbdiagram.io)

   
## 📘 Key Concepts

### 🔑 Primary Key
A **Primary Key** is a unique identifier for each record in a table. It cannot be null and must be unique.  
> Example: `book_id` in `Books`, `member_id` in `Members`.

### 🔗 Foreign Key
A **Foreign Key** is a column that creates a relationship between two tables. It references the primary key of another table.  
> Example: `book_id` in `Borrow` references `Books(book_id)`.

    
