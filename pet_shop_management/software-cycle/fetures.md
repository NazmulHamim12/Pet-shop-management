# Pet Shop Management & Sales System (Django/Python)

This document provides a structured Feature Analysis and a comprehensive `README.md` specification for your project based on your requirements.

---

## 🏗️ 1. Requirement Analysis & Feature Mapping

To make the unorganized requirements structured and clean, they have been analyzed and mapped into **7 Core Feature Modules**. Below is the detailed breakdown of which requirement goes into which feature:

### 🔐 Feature 1: Authentication & Session Management
*   **Requirements Included:** Login System (Email and Password), Session-Based Auth.
*   **Technical Implementation:** Uses Django's built-in session framework or custom session-based authentication middleware to restrict sales and inventory actions to authenticated users (e.g., Shop Managers/Admins).

### 📦 Feature 2: Product & Inventory Management

*   **Requirements Included:** Product Information (Store at least 10 products), Product ID, Product Name, Category (Food, Toy, Accessory, Medicine), Unit Price, Available Quantity, Inventory Update (Update stock after each purchase).
*   **Technical Implementation:** Database schema (`Product` model) tracking IDs, naming, pricing, categories, and real-time inventory decrements after checking out a shopping cart.
*   **Workable Features**:<br>
        &nbsp;1.Add product<br>
        &nbsp;2.Update product<br>
        &nbsp;3.Delete product<br>
        
    



### 🔍 Feature 3: Product Exploration & Search
*   **Requirements Included:** Display Product List (Formatted table with 'Out of Stock' status labels), Search Product (By Product ID or Product Name).
*   **Technical Implementation:** Dynamic filtering queries on the product queryset and conditional UI rendering (`{% if product.quantity == 0 %} Out of Stock {% endif %}`).
*   **Workable Features**:<br>
        &nbsp;1.Product List<br>
        &nbsp;2.Product Search<br>

<br>



### 🛒 Feature 4: Interactive Shopping Cart & Order Processing
*   **Requirements Included:** Purchase Products (Single/Multiple items), Check stock availability before confirming, Multiple Purchases (Loop/Continue purchasing until finished), Shopping Cart Summary.
*   **Technical Implementation:** Session-backed shopping cart array storing temporary item lists, quantities, and prices before running database transactional operations.
*   **Workable Features**:<br>
        &nbsp;1.Shopping cart<br>

<br>

### 💳 Feature 5: Customer Profiles & Discount Engine
*   **Requirements Included:** Collect Customer Info (Name, Mobile, Membership Number), Membership Discount (Predefined list, 5% off), Pet Type Discount (Additional 5% off if all items belong to a matching target pet category), VAT Calculation (5% VAT after discounts).
*   **Technical Implementation:** A backend processing pipeline calculating tiered deductions:
    1. Base Subtotal 
     2. Membership Discount (-5%)
     3. Pet Type Cross-Category Validation (-5%)
     4. Government VAT (+5%).

*   **Workable Features**:<br>
        &nbsp;1.Add order<br>
        &nbsp;2.Update order<br>
        &nbsp;3.Delete order<br>



<br>



### 🧾 Feature 6: Receipt Generation & Export
*   **Requirements Included:** Pet Information (Ask pet type to print), Sales Receipt Layout (Shop name, customer info, items table, discounts, VAT, grand total), Save Receipt (Download Option).
*   **Technical Implementation:** PDF rendering system using standard document workflows or file triggers (`reportlab` or text-stream downloads).
*   **Workable Features**:<br>
        &nbsp;1.Download Receipt<br>

<br>






### 📊 Feature 7: Sales Ledger & Analytics
*   **Requirements Included:** Sales History, Payment Method (Cash, Card, Mobile Banking).
*   **Technical Implementation:** A transactional `SalesHistory` database model logging completed order aggregates, associated customer metadata, and chosen payment routes.
*   **Workable Features**:<br>
        &nbsp;1.Sales History.<br>
        &nbsp;2.Sales Analysis.<br>
---

