# Introduction
Data lies at the heart of every modern system — but raw, unstructured data often carries redundancy, inconsistency, and inefficiency. To truly unlock its value, we need a structured approach to organizing it. This project demonstrates data modelling with normalization, transforming messy, repetitive datasets into well-designed relational models that are efficient, consistent, and scalable.

Starting from 1NF (First Normal Form) and progressing to 3NF (Third Normal Form), this project walks through step-by-step normalization with illustrative examples. You’ll see how a single unoptimized table evolves into a relational schema where:

- Redundancy is minimized
- Dependencies are properly managed
- Data integrity is preserved
- Queries become simpler and better

By the end, you’ll not only understand why normalization matters, but also how to apply it in real-world scenarios such as sales transactions, customer management, and inventory systems. 


## About this project
This project explores five real-world industry scenarios, each starting with raw, unstructured data in 1NF and evolving into fully normalized tables in 3NF.

The industries covered include:

- *Flight & Airline Operations* – managing flights, passengers, and bookings

- *Fleet Operations* – tracking vehicles, drivers, and maintenance activities

- *E-commerce (B2B & B2C)* – handling customers, products, and orders

- *Fintech* – managing customers, accounts, and transactions

- *Foodtech* – organizing restaurants, menus, and orders

For each scenario, we:

* Begin with a flat table (1NF) that contains redundancies and anomalies.

* Restructure into 2NF by separating entities and removing partial dependencies.

* Refine into 3NF by removing transitive dependencies and ensuring clean relational models.


###  Case Study 1: Flight & Airline Operations

Imagine AirXpress, a fast-growing regional airline, where booking agents record all passenger details in a single spreadsheet. Every booking lists the passenger’s name, contact, flight number, seat, destination, airline name, and price.

At first, this works fine. But soon, patterns of redundancy appear:

- Every passenger on flight F101 repeats the Airline Name and Flight Details.

- If the airline changes its name, hundreds of rows must be updated.

- Queries  become messy.

By normalizing the data:

- Passenger details are separated into a Passengers table.

- Flight details live in a Flights table.

- Bookings link passengers to flights with seats.

- Airline names are managed in a clean Airlines table.

- Suddenly, AirXpress can handle thousands of bookings without redundant updates. Queries are faster, cancellations are easier to track, and customer records stay clean.




###  Case Study 2: Fleet Operations

A logistics company, LogiFleet, manages over 200 delivery vehicles. Initially, they log driver names, licenses, vehicle registrations, maintenance types, mechanic names, and costs in a single sheet.

Problems soon arise:

- Each vehicle’s registration is repeated for every service.

- Drivers who operate the same vehicle appear again and again.

- Mechanics’ names are typed differently (Mike John vs. Michael John).

By applying normalization:

- Drivers, Vehicles, and Mechanics get their own tables.

- Maintenance logs reference these entities by ID, not names.

- Service types and costs are tracked independently.

The result? LogiFleet can now generate precise reports like “Average maintenance cost per vehicle” or “Driver history per vehicle”, helping cut operational waste and improving accountability.




###  Case Study 3: E-commerce (B2B/B2C)

An online store, ShopHub, starts small, tracking all customers, products, and orders in a single Excel sheet. Each row lists the customer’s name/email, product name, category, quantity, and price.

As sales grow, issues appear:

- The same customer’s email is typed differently in multiple rows.

- Product categories like “Electronics” are repeated thousands of times.

- Changing a product’s price requires editing multiple rows.

After normalization:

- Customers are uniquely stored in a Customers table.

- Products belong to Categories and have consistent prices.

- Orders reference Customers, while OrderDetails link to Products.

Now, ShopHub can analyze repeat customers, track sales by product category, and easily update pricing — enabling scalable e-commerce growth.





###  Case Study 4: Fintech

A fintech startup, PaySmart, handles digital transactions. Their early database tracks transaction ID, account number, customer details, merchant name, category, amount, and date all in one place.

Problems start fast:

- The same customer details are copied for every transaction.

- Merchant categories like “Transport” or “E-commerce” are duplicated.

- A customer with multiple accounts has their name and email repeated unnecessarily.

Normalization fixes these issues:

- Customers are separated from Accounts.

- Transactions are linked to Accounts, not directly to customers.

- Merchants and Categories get their own tables.

With this model, PaySmart can now generate spending reports by category, detect suspicious account activity, and maintain consistent customer records across multiple accounts.







###  Case Study 5: Foodtech

A food delivery platform, Foodify, starts with a single table where every order lists the restaurant, location, customer details, menu item, category, quantity, and price.

This quickly becomes problematic:

- Restaurant names and addresses are repeated for every order.

- Menu items are inconsistently typed (e.g., “Margherita Pizza” vs. “Margarita Pizza”).

- Updating a menu price requires changing every related order row.

After normalization:

- Restaurants are stored once in a Restaurants table.

- Customers live in a Customers table.

- Menu items belong to Categories and Restaurants.

- Orders link Customers and Restaurants, with OrderDetails handling menu items.

Now, Foodify can answer critical business questions like:

- Which restaurants generate the most revenue?

- What are the top-selling dishes?

- Which customers order most frequently?
