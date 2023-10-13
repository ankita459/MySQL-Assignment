**Create a database called store, this database contains the following tables:**
**a. items: **This table contains the item information such as its id, name 
and price.
**b. users:** This table contains the user specific information such as name, 
email id, password, contact number, city and address.
**c. users_items:** This table stores the information about the item orders by 
the users. Columns are id, user_id, items_id and status.

**Queries:**
**-- Create the store database**
CREATE DATABASE IF NOT EXISTS store;

**-- Use the store database**
USE store;

**-- Create the items table**
CREATE TABLE IF NOT EXISTS items (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL,
    price DECIMAL(10, 2) NOT NULL
);

**-- Create the users table**
CREATE TABLE IF NOT EXISTS users (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL,
    password VARCHAR(255) NOT NULL,
    contact_number VARCHAR(20) NOT NULL,
    city VARCHAR(255) NOT NULL,
    address VARCHAR(255) NOT NULL
);

**-- Create the users_items table**
CREATE TABLE IF NOT EXISTS users_items (
    id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    item_id INT,
    status VARCHAR(255),
    FOREIGN KEY (user_id) REFERENCES users(id),
    FOREIGN KEY (item_id) REFERENCES items(id)
);
