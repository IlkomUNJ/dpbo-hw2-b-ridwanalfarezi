[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/uAfN8jpt)

Name: Ridwan Alfarezi

NIM : 1313624020

# Online Marketplace System

A comprehensive C++ console-based e-commerce platform featuring buyer-seller interactions, banking system integration, inventory management, and comprehensive analytics.

## Project Overview

This project implements a full-featured online marketplace system where users can register as buyers, upgrade to sellers, manage inventory, process orders, and handle banking transactions. The system includes data persistence, transaction tracking, and advanced analytics features.

## Key Technologies

- **Language**: C++ (C++20 standard)
- **Build System**: Meson
- **Architecture**: Object-Oriented Programming (OOP)
- **Data Persistence**: File-based serialization

## System Architecture

### Core Components

1. **Bank System** (`bank/`)

   - Bank account management
   - Transaction recording and history
   - Balance operations (deposit, withdraw)
   - Analytics (dormant accounts, top users)

2. **Bank Customer** (`bank_customer/`)

   - Customer account information
   - Balance management
   - Account details and status

3. **Buyer** (`buyer/`)

   - User registration and login
   - Shopping cart management
   - Order history tracking
   - Spending analysis

4. **Seller** (`seller/`)

   - Inherits from Buyer class
   - Inventory management
   - Order fulfillment
   - Revenue tracking and analytics

5. **Item** (`item/`)

   - Product information
   - Stock management
   - Visibility control

6. **Order** (`order/`)

   - Order creation and tracking
   - Status management (Pending, Paid, Completed, Cancelled)
   - Order item details

7. **Store** (`store/`)

   - Marketplace management
   - Global order tracking
   - Store-wide analytics

8. **Transaction** (`transaction/`)
   - Transaction type tracking
   - Timestamp management
   - Transaction history

## Features Implemented (list all completed)

1. **User Management System**

   - User registration with bank account creation
   - Login authentication
   - Account status viewing
   - Buyer to Seller upgrade functionality

2. **Banking System**

   - Initial deposit on registration
   - Balance checking
   - Deposit (top-up) functionality
   - Withdrawal functionality
   - Transaction history (today, last 30 days, all time)
   - Account linking with buyer/seller profiles

3. **Shopping Features**

   - Browse multiple stores
   - View seller inventories
   - Add items to shopping cart
   - Remove items from cart
   - Cart viewing and management
   - Multi-seller checkout support

4. **Order Management**

   - Order creation and tracking
   - Order status management (Pending, Paid, Completed, Cancelled)
   - Order history viewing
   - Filter orders by status
   - Invoice generation
   - Payment processing with balance verification

5. **Seller Inventory Management**

   - Add new items to inventory
   - Update existing items (name, quantity, price)
   - Set item prices
   - Replenish stock
   - Discard stock
   - Toggle item visibility (show/hide from customers)
   - View all inventory items

6. **Payment Processing**

   - Automated payment from buyer to seller
   - Balance verification before checkout
   - Multi-order payment support
   - Transaction recording for both parties
   - Automatic stock reduction on purchase

7. **Analytics & Reports**

   - **Buyer Analytics**:

     - Spending analysis (last K days)
     - Cash flow tracking (credit vs debit)
     - Order history analysis

   - **Seller Analytics**:

     - Top K popular items this month
     - Top N loyal customers this month
     - Revenue calculation (last K days)
     - Order tracking by status

   - **Store (Admin) Analytics**:

     - Transactions in last K days
     - Paid but incomplete orders
     - Most frequent items sold
     - Most active buyers today
     - Most active sellers today

   - **Bank Analytics**:
     - Transactions within a week
     - All bank customers listing
     - Dormant account detection
     - Top N users by transaction count

8. **Data Persistence**

   - Save bank customers to file
   - Save buyers to file
   - Save sellers to file
   - Load data on program start
   - Auto-save on program exit

9. **Order Completion Workflow**

   - Sellers can mark paid orders as completed
   - Order status tracking throughout lifecycle
   - Buyer-seller transaction flow

10. **Dual Mode Support**
    - Seamless switching between Buyer and Seller modes
    - Unified account management for dual-role users

## Class Hierarchy

```
BankCustomer
    ├─ Buyer
    │    └─ seller (inherits from Buyer)
    │
Bank
    └─ manages BankCustomer objects
    └─ handles Transaction objects

Store
    └─ manages Order objects

Order
    └─ contains OrderItem objects

Item
    └─ managed by seller
```

## Build Instructions

### Prerequisites

- C++20 compatible compiler (g++/clang++)
- Meson build system
- Ninja build tool

### Build Steps

```bash
# Navigate to project directory
cd dpbo-hw2-b-ridwanalfarezi

# Configure build (if not already done)
meson setup builddir

# Compile the project
meson compile -C builddir

# Run the application
./builddir/my_app.exe
```

## Usage

### Main Menu Options

1. **Login** - Access existing account
2. **Register** - Create new buyer account (with optional seller account)
3. **Store Analytics** - Admin view of system-wide statistics
4. **Exit** - Save data and quit

### Buyer Menu Features

- View Account Status
- Upgrade to Seller
- Banking Functions
- Browse & Shop
- View Shopping Cart
- Checkout
- Manage Orders
- View Spending Analysis
- Switch to Seller Mode (if applicable)
- Logout

### Seller Menu Features

- Manage Inventory
- View Orders
- Complete Order
- Analytics & Reports
- View Revenue
- Back to Buyer Menu

## Data Files

The system creates the following data files for persistence:

- `bank_customers.dat` - Bank account information
- `buyers.dat` - Buyer profile information
- `sellers.dat` - Seller profile and store information

## OOP Concepts Demonstrated

- **Inheritance**: Seller inherits from Buyer
- **Encapsulation**: Private data members with public getters/setters
- **Polymorphism**: Virtual destructors, method overriding
- **Abstraction**: Clean interfaces for complex operations
- **Composition**: Bank has BankCustomers, Store has Orders
- **Association**: Buyers linked to BankCustomers via references

## Error Handling

- Input validation for all user inputs
- Balance verification before transactions
- Stock verification before purchases
- Duplicate ID checking for items
- File I/O error handling

## Collaborators (The person you learned from)

1. Nandana Ammar 
2. Ernando Febrian

## Students (the person you taught to complete the assignments)

1. (To be filled by student)

## AI Assistance

AI Tools: Github Copilot with Claude 4.5 Sonnet as AI Model

Paid AI Plugin (state none, if not subscribed): none

Total Prompts used (int estimate): 10

Dominant prompt used for (seek solution / implement ideas): Implement ideas
