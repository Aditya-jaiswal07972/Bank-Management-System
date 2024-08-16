# Bank Management System
## Introduction

This project is a console-based Bank Management System implemented in Java. It connects to a MySQL database to perform various banking operations such as adding customers, managing accounts, and handling transactions. The system provides a menu-driven interface for users to interact with the database.

## Features

- **Add Customer**: Allows users to add a new customer to the database.
- **Display Customer**: Fetches and displays customer details based on the customer ID.
- **Add Account**: Enables users to add a new account for an existing customer.
- **Display Account**: Retrieves and displays account details based on the account number.
- **Deposit Amount**: Facilitates depositing an amount into an existing account.
- **Withdraw Amount**: Facilitates withdrawing an amount from an existing account.
- **Exit**: Exits the application.

## Technologies Used

- Java
- MySQL
- JDBC (Java Database Connectivity)

## Prerequisites

- Java Development Kit (JDK) 8 or higher
- MySQL Server
- MySQL JDBC Driver

## Database Setup

1. **Install MySQL**: Ensure MySQL is installed and running on your local machine.
2. **Create Database**: Create a database named `bankmanagementsystem`.
3. **Create Tables**:

```sql
CREATE TABLE customer (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    address VARCHAR(255),
    phone VARCHAR(20),
    email VARCHAR(100)
);

CREATE TABLE account (
    account_number INT PRIMARY KEY,
    customer_id INT,
    account_type VARCHAR(50),
    balance DOUBLE,
    FOREIGN KEY (customer_id) REFERENCES customer(id)
);
```

## Configuration

1. **Database Connection**: Update the database connection details in the code:

```java
conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/bankmanagementsystem", "root", "rishav");
```

## How to Run

1. **Compile the Java file**:

```sh
javac BankManagementSystem.java
```

2. **Run the compiled class**:

```sh
java BankManagementSystem
```

## Usage

Upon running the application, the following menu will be displayed:

```
Welcome to the Bank Management System.
1. Add Customer
2. Display Customer
3. Add Account
4. Display Account
5. Deposit Amount
6. Withdraw Amount
7. Exit
Enter your choice (1-7):
```

Enter the corresponding number for the desired operation and follow the prompts.

## Code Structure

- **Main Class**: `BankManagementSystem`
  - Establishes database connection
  - Provides menu-driven interface for user interaction
  - Performs CRUD operations on the database

- **Methods**:
  - `addCustomer()`: Adds a new customer to the database
  - `displayCustomer()`: Displays customer details by ID
  - `addAccount()`: Adds a new account for a customer
  - `displayAccount()`: Displays account details by account number
  - `depositAmount()`: Deposits amount into an account
  - `withdrawAmount()`: Withdraws amount from an account

## Error Handling

The code includes basic error handling to manage exceptions and invalid inputs. However, for production use, more robust error handling and input validation would be recommended.

## License

This project is licensed under the MIT License.

---

Feel free to contribute to this project by forking the repository and submitting pull requests. Your contributions are always welcome!
