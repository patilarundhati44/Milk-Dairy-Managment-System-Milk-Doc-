
## Milk Dairy Management System (MilkDoc)

![Java](https://img.shields.io/badge/Java-17-blue)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-green)
![JDBC](https://img.shields.io/badge/JDBC-4.2-orange)
![Multithreading](https://img.shields.io/badge/Multithreading-Enabled-purple)

The Milk Dairy Management System (MilkDoc) is a console-based Core Java application that uses JDBC and PostgreSQL. 
It allows users to perform CRUD (Create, Read, Update, Delete) operations on milk providers, record daily milk collections, and manage payments. 
The system is menu-driven, offering a simple interface to manage dairy operations efficiently.

---


## Features

- Add Milk Provider     :    Add a new milk provider to the database.
- Add Milk Record   :    Record daily milk quantity, fat content, and rate per litre.
- View All Providers :    Display all registered milk providers.
- Update Milk Record :    Update existing milk collection entries.
- Delete Milk Record :    Delete any specific milk record using ID.
- Record Payment     :    Log payment given to milk providers.
- Calculate Total Payment    :    Show total payable amount to a provider.
- Check Pending Payment :    Calculate remaining payment after deduction.
- Monthly Summary   :    Display total milk and amount for a specific month.
- Supplier of the Day:    Get the highest milk supplier for a selected date.
- Menu-Driven Interface:    Easy-to-use console-based menu for user navigation.

---

## Technologies Used

- **Core Java**: For implementing the application logic and OOPs concepts.
- **JDBC (Java Database Connectivity)**: For connecting and interacting with the PostgreSQL database.
- **PostgreSQL**: For storing and managing provider, milk, and payment data.
---


## Dependencies

Add this PostgreSQL JDBC dependency in your `pom.xml`:

```xml
<dependency>
    <groupId>org.postgresql</groupId>
    <artifactId>postgresql</artifactId>
    <version>42.6.0</version>
</dependency>
```
---

## Prerequisites

- Before running the project, ensure you have the following installed:
- Java Development Kit (JDK) 17 or higher.
- PostgreSQL 15 or higher.
- Any Java IDE (e.g., IntelliJ, VS Code, Eclipse).

## Database Setup

Create the required tables in your PostgreSQL database by executing the following SQL:

```sql
CREATE TABLE milk_provider (
    provider_id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    contact VARCHAR(20),
    address VARCHAR(255)
);

CREATE TABLE milk_record (
    record_id SERIAL PRIMARY KEY,
    provider_id INT REFERENCES milk_provider(provider_id),
    date DATE NOT NULL,
    quantity DOUBLE PRECISION,
    fat_content DOUBLE PRECISION,
    rate_per_litre DOUBLE PRECISION
);

CREATE TABLE payment (
    payment_id SERIAL PRIMARY KEY,
    provider_id INT REFERENCES milk_provider(provider_id),
    amount DOUBLE PRECISION,
    payment_date DATE
);
```
---

## Contact
For any questions or feedback, feel free to reach out:

- Your Name: Arundati Anand Patil

- Email: patilarundhati44@gmail.com

- GitHub: patilarundhati44
