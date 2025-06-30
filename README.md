# airbnb-clone-project
Brief overview of the project
This is an airbnb clone Project for a rental platform that allows one to register as either a host or guests, list properties and book available accomodations.

Goals of the project
- Implement backend architecture and API design
- Practice CRUD operations, authenticatio and database relationships
- Error handling, logic design and deployment

Tech stack overview
- Html & CSS
- Javascript
- Python
- Django framework
- MySQL
- Docker container


# Team Roles
- Backend developer - maintain server logic, API and database. Ensure security performance and data flow between the frontend and database. Handels authentication, user roles and booking logic.
- Database Administrator - Design and manage database schema. Ensure data consistency, optimise queries, handle migration and setup backup
- QA engineer - Create and run tests to ensure backend functionality works correctly
- Devops Engineer - Set up CI/CD pipelines, containerization and deployment to production environment.

# Technology Stack
Python - Core programming language that will be used to build the backend logic, APIs, and data handling routines.
Django - Python web framework that will be used to build the API, handle routing, request cycles and integrate with ORM and authentication libraries.
Django ORM - Enable efficient data modeling and query abstraction.
Git and Github - Source code management tool to track changes, collaborate and maintain code history.
Pytest - Testing frameworks to validate backend logic, database interactions and API endpoints through unit and integration tests.


# Database Design
The airbnb clone project uses a relational database schema which represents the core entities and relationships.

Key entities 
Users - both hosts and guests
Key Fields
id: Primary key
name: Full name
email: email address
password: password
role: host or guest

Properties - represent rental listings created by hosts
Key Fields
id: Primary Key
title: Listing title
description: Details about the property
Location: City or address
price per night: Cost of renting per night
host_id: Foreign key referencing the Users table

Bookings - reservation made by a guest
Key Fields
id: Primary key
guest_id: Foreign key referencing the Users table
property_id: Foreign referencing the Properties table
start_date: booking start date
end_date: Booking end date
Status: Current status 

Payments
Key Fields
id: Primary key
booking_id: Foreign key referencing the bookings table
amount: Total amount paid
payment_method: paypal, credit card, klarna
payment_status: paid, pending, failed

Entity relationships
A user can be either a host or a guest
A host can create multiple properties
A guest can create multiple bookings
A booking is linked to one property and one guest
A booking has one payment record



# Feature Breakdown
User management - Handles user registration, login and role assignment. Implements authenntication using secure password hashing and token based access control to protect API routes and user-specific actions.

Property Management
Allow hosts to create, edit and delete property listings with details. This feature forms the foundation of the platform, enabling hosts to offer accomodations for booking.

Booking System
Enables guests to book properties by selecting a date range and submitting a reservation. This includes availabilty checks, conflict resolution and booking status management.

Payment handling
Capture payments information linked to confirmed bookings. Support transaction records and status tracking to simulate a real world payment flow.

Authentication and Authorisation
Secures API endpoints using JWT based authenticationd and role based authorisation. Only verified users can perform aactions appropriate to their role.


# API Security
Authentication
JWT - used to verify the identity of users. It prevents unaauthorised access to user specific data and actions, ensures only verified users can access protected resources.

Authorisation - determine what users are allowed to do. Prevents users from accessing resources they don't own.

Input validation - incoming user inputs will be validated before processing. Protects against common web attacks.

Password hashing - Passwords will be stored using hashing algorithms. Plain passwords remain protected, reduce risk of credential leaks.

Secure payment handling - payment data will be processed using secure third party services. Avoid direct handling of sensitive financial information.

# CI/CD Pipeline
These are development practices which help automate the processs of testing, building and deploying code.

Tools
Github actions
Docker
Heroku
Pytest