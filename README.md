# TransConnect Project

Welcome to the **TransConnect Project**! This document outlines the structure, features, and potential enhancements of the TransConnect application, developed to optimize logistics management processes and resources for a transport company. Here, you'll find details about the classes, data management, and proposed functionalities.

---

## 🔍 Overview

TransConnect is a logistics application designed for transport companies, simplifying the management of clients, employees, vehicles, and orders. The project includes real-world entity modeling, utility tools for data handling, and advanced features like real-time route updates and automated invoicing.

---

## 📂 Project Structure

### Class Overview

#### Main Classes

1. **Person** *(abstract)*: Represents an individual.
   - **Client**: Inherits from `Person` and contains client-specific information.
   - **Employee**: Represents a company employee.
      - **Driver**: A specialized employee handling goods transportation.

2. **Vehicle** *(abstract)*: Models various types of vehicles.
   - **Car**: A standard vehicle with a passenger capacity.
   - **Van**: Used for transporting goods, with specified volume and usage type.
   - **Heavy Vehicle** *(abstract)*: A category for specialized heavy vehicles.
      - **Refrigerated Truck**
      - **Dump Truck**
      - **Tanker Truck**

3. **Data Collection** *(Linked List)*:
   - `NodeDict`: Contains a key, a value, and a reference to the next node.
   - `ChainedDictionary`: A linked list containing the first node and utility functions.

4. **Graph Structure**:
   - **Node**: Represents a city with its coordinates and list of edges.
   - **Edge**: Connects two nodes with attributes for distance and time.
   - **Graph**: Stores nodes and provides necessary methods.

5. **Order**: Links clients, drivers, the company, and vehicles, containing all relevant information for a single order.

6. **Company**: Manages all company resources, including clients, employees, vehicles, and orders.

7. **Tools**: Utility functions to support other classes, especially for user input validation.

8. **Program.cs**: The main menu and navigation interface for the user.

9. **IsToString Interface**: Ensures implementing classes define a `ToString` method.

---

## 📁 Data Storage

### Backup Files

Company data is stored as CSV files in the `Backup` folder, including information on clients, vehicles, orders, and employees. These files are read at startup to initialize objects and updated whenever a modification is made, ensuring data consistency.

### Invoices

Each order generates a corresponding invoice, also stored in the `Backup` folder, with an option to send it to the client via email.

---

## ✨ Features and Enhancements

### 1. Real-Time Route Updates
   - The application connects to the MapBox API to update distances between cities based on traffic, weather conditions, and time of day, improving the accuracy of route estimates.

### 2. Chained Dictionary
   - Using `NodeDict`, the `ChainedDictionary` functions as a linked list for efficient data storage and retrieval. This dictionary is particularly useful in the `Tools.Saisie` function for managing user input with conditions and custom error messages.

### 3. Automated Invoice Generation
   - The `CreateInvoice` function in the `Order` module generates PDF invoices by retrieving details from the order, client, and company.

### 4. Emailing Invoices
   - Using the SMTP protocol, the application can send invoices as attachments to clients, facilitating customer relationship management directly from the platform.

---

## 🎉 Getting Started with the Project

1. **Run the Application**: Navigate through the main menu in `Program.cs`.
2. **Explore the Classes**: Familiarize yourself with the class structure and their relationships.
3. **Generate and Send Invoices**: Take advantage of the invoice creation and emailing features to streamline your operations.

---

### 🚀 Thank you for exploring TransConnect!
