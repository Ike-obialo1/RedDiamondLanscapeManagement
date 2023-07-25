# RedDiamondLanscapeManagement
This SQL code sets up the database schema for the Red Diamond Lanscapes 
I developed a management system to efficiently handle various aspects of the company's operations. The database stores essential information about clients, employees, projects, and inventory. The goal of this project was to streamline the company's processes, improve data organization, and enable data-driven decision-making.
-- Create the Landscaping Company Management System database
CREATE DATABASE LandscapingCompanyDB;

-- Use the database
USE Red Diamond LandscapesDB;

-- Create the Clients table
CREATE TABLE Clients (
    ClientID INT AUTO_INCREMENT PRIMARY KEY,
    Name VARCHAR(100) NOT NULL,
    ContactNumber VARCHAR(20),
    Email VARCHAR(100),
    Address VARCHAR(200)
);

-- Create the Employees table
CREATE TABLE Employees (
    EmployeeID INT AUTO_INCREMENT PRIMARY KEY,
    Name VARCHAR(100) NOT NULL,
    ContactNumber VARCHAR(20),
    Email VARCHAR(100),
    Role VARCHAR(50),
    Salary DECIMAL(10, 2)
);

-- Create the Projects table
CREATE TABLE Projects (
    ProjectID INT AUTO_INCREMENT PRIMARY KEY,
    ClientID INT,
    EmployeeID INT,
    StartDate DATE,
    EndDate DATE,
    Budget DECIMAL(10, 2),
    Status VARCHAR(50),
    FOREIGN KEY (ClientID) REFERENCES Clients(ClientID),
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)
);

-- Create the Services table
CREATE TABLE Services (
    ServiceID INT AUTO_INCREMENT PRIMARY KEY,
    ServiceName VARCHAR(100) NOT NULL,
    Description TEXT,
    Price DECIMAL(10, 2)
);

-- Create the Inventory table
CREATE TABLE Inventory (
    InventoryID INT AUTO_INCREMENT PRIMARY KEY,
    ItemName VARCHAR(100) NOT NULL,
    Description TEXT,
    Quantity INT,
    UnitPrice DECIMAL(10, 2)
);
