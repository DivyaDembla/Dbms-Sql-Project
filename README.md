✈️ Airline Management System (DBMS Mini Project)

A comprehensive backend database project designed to simulate core airline operations. This system manages flight scheduling, ticket booking, passenger records, and employee administration using normalized tables and advanced PL/SQL automation.

📌 Project Overview

This project implements a relational database system to handle:

Flight Operations: Scheduling flights, managing delays, and linking airlines to airports.

Passenger Management: A normalized structure separating passenger IDs, personal details, and flight associations.

Ticketing System: Handling bookings, classes (Economy/Business/First), and calculating cancellation surcharges.

HR Management: Tracking employee shifts, job types, and automating salary updates.

🗂 Database Schema

The database is designed with Normalization (up to 3NF) to ensure data integrity.

1. Flight & Infrastructure

City: Stores city names mapped to states and countries.

Airport: Airport details linked to specific cities (FK_CNAME).

Airlines: Airline codes and names (e.g., AI for Air India).

Ref1: A bridge table linking Airlines to Airports.

Flight: The core schedule table containing source, destination, timing, status (Delayed/On-time), and connection details.

2. Passenger & Ticketing

Passenger1: Base table storing unique Passenger IDs (P_ID) and Passport Numbers.

Passenger2: Stores personal details (Name, Address, Age, Sex).

Passenger3: Links Passengers to specific Flight Codes.

Ticket1: Primary ticketing info (Dates, Seat No, Class, Cancellation Date).

Ticket2: Stores pricing information linked to Ticket1.

Ticket3: Stores surcharge amounts for cancelled tickets.

3. Human Resources

Employee1: Employee personal details, shifts, and positions.

Employee2: Reference table for Salary grades based on Job Type.

💻 Key Features & Queries

This project includes 20+ optimized queries demonstrating various SQL capabilities:

🔍 Advanced SQL Analysis

Pattern Matching: Retrieving employee names starting with specific letters (e.g., 'R') and specific age groups.

Complex Joins:

Full Join: Linking Passenger1 and Passenger3 to see flight associations.

Three-Table Join: Connecting Ticket1, Passenger2, and Ticket3 to calculate surcharges for cancelled tickets.

Pivot Logic: Counting Male vs. Female passengers per travel class using CASE statements.

N-th Highest Value:

Finding the 2nd Highest Business Class Price.

Finding the 3rd Highest Economy Class Price using nested subqueries.

⚙️ PL/SQL Automation

The project utilizes procedural logic to handle business rules:

Stored Procedures:

add_to_flight: Accepts parameters to insert new flight schedules safely.

pro: Retrieves passenger details with Exception Handling (NO_DATA_FOUND) for invalid IDs.

Functions:

total_employees: Returns the current count of active staff members.

Cursors:

Explicit Cursor: Iterates through tickets to print a route manifest (Source -> Destination).

Implicit Cursor: Updates ticket prices in bulk (SQL%ROWCOUNT tracking).

Triggers & Sequences:

auto_pid: A sequence used to auto-generate Passenger IDs.

Conditional Logic: PL/SQL blocks to update employee salaries if they fall below a specific threshold.

🚀 How to Run

Database Setup:

Open your Oracle SQL environment (SQL*Plus or SQL Developer).

Copy and execute the Table Creation scripts (create City, Airport, Airlines, etc.).

Data Population:

Insert the sample data provided in the script to populate the tables.

Execute PL/SQL:

Compile the Procedures and Functions.

Run the anonymous blocks (the sections starting with DECLARE).

Example execution:

EXEC add_to_flight('AI2024','Mumbai','Colorado','15:15','17:25','Delayed','14hr',1,0,'AI');


👨‍💻 Author

Sankalp Jadhav, Divya Dembla, Mohd Uzair, Snehal Dalvi

Department: IT

Project Type: Database Management Systems (Mini Project)
