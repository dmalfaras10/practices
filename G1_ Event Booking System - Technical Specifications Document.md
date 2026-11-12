# Technical Specifications Document

## 1. G1: Event Booking System
- **Version**: 1.0
- **Date**: October 19, 2026
- **Author(s)**: Dan Michael Alfaras, Matthew Antonio Bulaong, Jovie Cleofas, Aaron Angelo Crisologo


## 2. Table of Contents
1. [Introduction](#3-introduction)
2. [Overall Description](#4-overall-description)
3. [Visual Mockup Reference](#5-visual-mockup-reference)
4. [Features](#6-features)
5. [Functional Requirements](#7-functional-requirements)
6. [Non-Functional Requirements](#8-non-functional-requirements)
7. [Data Requirements](#9-data-requirements)
8. [External Interface Requirements](#10-external-interface-requirements)
9. [Glossary](#11-glossary)
10. [Appendices](#12-appendices)


## 3. Introduction

  The G1 Event Booking System is a web-based application designed to provide users with a platform convenient for browsing upcoming events, viewing event information, and booking tickets for events online. The system also provides admin privileges that allows authorized individuals to add, update, delete, and manage event listings as well as monitor user/event bookings. Users can also avail for memberships/subscriptions to get exclusive offers and benefits depending on the tier. By centralizing event information and the booking process, the system aims to make event booking more accessible, organized, and efficient.

### **Purpose**:

  The G1 Event Booking System is a centralized web-based ticketing platform designed to streamline event discovery, ticket purchasing, digital ticket access, and booking management for attendees, enhanced by tiered membership perks like discounts and presale access. For administrators, it provides tools to manage event listings, monitor bookings, and maintain user records—ultimately improving efficiency and organization for both attendees and platform managers.

### **Scope**:

  The G1 Event Booking System covers the development of a web-based platform for user authentication, event discovery, ticket purchasing, booking management, and tiered membership perks (such as discounts and presale access), alongside administrative tools for managing events, tickets, plans, users, and bookings. Physical ticket delivery, travel or lodging bookings, venue management, and a standalone mobile app are excluded from the project's scope.

#### **Definitions, Acronyms, and Abbreviations**:

  The following terms are used throughout the documentation to describe the different components, and aspects of the G1 Event Booking System
  
  | G1 Event Booking System | Refers to the web-based application that allows users to browse events, and create bookings |
  | :---- | :---- |
  | User | Refers to an individual visiting the website to browse events, create bookings, and update their profile |
  | Admin | Refers to an authorized individual responsible for creating, updating, managing events, and overseeing booking records |
  | Event | Refers to an organized activity, such as a concert listed in the system |
  | Booking | Refers to a record created when a user submits a request to reserve a ticket or more for an event |
  | Database | Refers to an organized collection of data used to store and manage user accounts, event information, and booking information (Silberschatz et al., 2020\)  |

### **References**:

  Coulouris, G., Dollimore, J., Kindberg, T., & Blair, G. (2011). *Distributed systems: Concepts and design* (5th ed.). Addison-Wesley.
  
  Silberschatz, A., Korth, H. F., & Sudarshan, S. (2020). *Database system concepts* (7th ed.). McGraw-Hill Education.
  
  Sommerville, I. (2016). *Software engineering* (10th ed.). Pearson.

#
## 4. Overall Description

### **Product Perspective**:

  The G1 Event Booking System is a centralized web-based application that simplifies online ticket booking by allowing attendees to browse events, check availability, purchase digital tickets, view booking history, and manage membership benefits. For administrators, it provides tools to manage events, ticket categories, bookings, transactions, and user records.

### **Product Functions**:

  The G1 Event Booking System will provide the following high-level functionalities:
  
  1. **User Registration and Authentication**  
      * Users are able to create accounts, log in, log out, and manage their profile information securely  
  2. **Event Browsing and Search**   
      * Enables users to browse upcoming events, search for specific events, view event details, and check ticket availability.   
  3. **Administrative Management**   
      * Enables administrators to manage user records, monitor ticket sales and booking transactions, track ticket availability, and oversee event operations.   
  4. **Event Booking & Payment**  
      * Enables users to select tickets, complete online bookings, and process payments through an integrated payment service.   
  5. **Booking Management & Ticket Management**  
      * Generates booking references and digital tickets for successful transactions. Allows users to view booking history, check ticket status, and access their ticket information.   
  6. **Membership Subscription**  
      * Enables users to explore and subscribe to Bronze, Silver, and Gold membership plans to unlock exclusive perks. Allows users to monitor their subscription status and manage plan renewals through their accounts.

### **User Classes and Characteristics**:

  The system will support two primary user classes:
  
  * **Users/Attendees**: Access the platform to browse events, purchase and view digital tickets, manage personal profiles and bookings, and utilize membership benefits. Access is restricted to their own account, bookings, and available event services.
  * **System Admins**: Oversee system operations and data accuracy by managing event listings, ticket categories, membership plans, booking records, and user transactions.

### **Operating Environment**:

  The G1 Event Booking System will operate as a web-based application accessible through an internet-connected device and a compatible web browser. It will use the MEVN stack (MongoDB, Express.js, Vue.js, and Node.js) to support event browsing, ticket purchasing, booking management, and administrative operations. The below describes the expected operating environment of the system. 
  
  1\. Client Environment
  
  The system will be accessible through desktop computers, laptops, tablets, and smartphones using modern web browsers such as Google Chrome, Microsoft Edge, Mozilla Firefox, and Safari. The interface will be designed to accommodate different screen sizes and devices.
  
  2\. Application Environment
  
  Vue.js will be used to develop the user interface, while Node.js and Express.js will handle backend processing, application logic, and communication between the frontend and database.
  
  3\. Database Environment
  
  MongoDB will serve as the database management system for storing and managing user accounts, event details, ticket categories, membership information, booking records, and transaction details.
  
  4\. Hosting Infrastructure
  
  The application’s frontend and backend will be deployed on their suitable hosting providers. The frontend will be hosted using Github’s free hosting service. While the backend will be hosted in a cloud hosting service like Amazon’s Web Services (AWS).
  
  5\. Network Requirements
  
  A stable internet connection will be required to access the system and use its features. HTTPS will be implemented to secure communication between users and the application.
  
  6\. Security Infrastructure
  
  The system will implement user authentication via JSON Web Token, role-based access control, secure password storage utilizing Bcrypt, and appropriate safeguards for user information and booking records. If an external payment gateway is integrated, payment transactions will be processed through the selected service.
  
  7\. Hardware Requirements
  
  Users will need a computer or mobile device capable of running a modern web browser. The server will require adequate processing power, memory, and storage to handle application operations, database management, and expected user traffic.

### **Assumptions and Dependencies**:

  The development of the G1 Event Booking System is based on the following assumptions: 
  
  Assumptions
  
  The development of the G1 Event Booking System is based on the following assumptions:
  
  * Users and administrators have access to an internet-connected device and compatible browser.
  * Users provide accurate registration details, and administrators maintain accurate event, pricing, and membership data.
  * Stakeholders will provide timely business rules, workflows, and feedback.
  * Users have appropriate permissions for their role, and the MEVN stack supports all target features.
  * Payment gateway integration and email/notification services will be implemented post-MVP once core MVP requirements are completed.
  
  Dependencies
  
  The G1 Event Booking System will depend on the following resources and services: 
  
  * Database Service: MongoDB Atlas for persistent storage.
  * Application Technologies: Vue.js, Node.js, Express.js, and Mongoose.
  * Hosting & Network: GitHub Pages, AWS (or equivalent cloud host), and stable internet connectivity.
  * External Services (Post-MVP): Third-party payment gateway for transaction processing and an external email/notification provider for transactional emails.
  * Stakeholder Support: Timely requirement approvals and user acceptance testing.


## 5. Visual Mockup Reference
- **Link or Screenshot**: [G1: Event Booking System Figma Visual Mockup](https://www.figma.com/design/GEkylbxWNNZ7c7XL5YBRtb/Event-Booking-Side-Project?node-id=0-1&t=MZUb4SSz7qulHcHh-1)


## 6. Features
- **Search & Navigation:** Offers a search bar and clear navigation across key pages (Homepage, Event Listings, About Us, Contact Us, and Membership).
- **User Accounts & Profile Management:** Supports registration, login, password recovery, profile updates, and tracking of upcoming events and booking history.
- **Homepage & Featured Shows:** Highlights popular and upcoming events via a hero carousel, displays essential event details, and includes an FAQ section.
- **Event Listings:** Enables browsing and filtering events by category, month, location, venue, price, and genre, supported by an interactive calendar, availability statuses, and promotions.
- **Event Details & Booking:** Displays full event details (schedule, venue, performers, rules), lets users compare and select ticket tiers, processes orders, and delivers digital ticket confirmations.
- **Contact Us & About Us:** Shares organizational background and policies alongside contact details, social links, and an inquiry form.
- **Membership & Subscriptions:** Allows users to compare, enroll in, and manage tiered plans (Bronze, Silver, Gold) for perks like discounts, priority booking, and presale access.
- **Email & Notifications:** Automates alerts for booking/payment confirmations, digital tickets, membership updates, event reminders, schedule changes and cancellations.


## 7. Functional Requirements
### Use Cases
- **Use Case 1**:
  - **Title**: 
  - **Description**: 
  - **Actors**: 
  - **Preconditions**: 
  - **Postconditions**: 
  - **Main Flow**: 
  - **Alternate Flows**: 

### System Features
- **Feature 1**:
  - **Description**: 
  - **Priority**: 
  - **Inputs**: 
  - **Processing**: 
  - **Outputs**: 
  - **Error Handling**: 

## 8. Non-Functional Requirements
- **Performance**: Describe performance requirements.
- **Security**: Outline security needs.
- **Usability**: Detail user interface and experience considerations.
- **Reliability**: Define reliability and availability requirements.
- **Supportability**: Specify maintenance and support requirements.

## 9. Data Requirements
- **Data Models**: Include simple diagrams if possible.
- **Database Requirements**: Describe tables and relationships.
- **Data Storage and Retrieval**: Explain how data will be stored and accessed.
- **ERD**: Add the ERD for the database models based on Specifications.

## 10. External Interface Requirements
- **User Interfaces**: Provide sketches or descriptions of the user interface.
- **API Interfaces**: Briefly describe any APIs.
- **Hardware Interfaces**: Mention any required hardware interactions.
- **Software Interfaces**: Note any software interactions.

## 11. Glossary
- **Term 1**: Definition
- **Term 2**: Definition

## 12. Appendices
- **Supporting Information**: Add any additional information here.
- **Revision History**: Record any changes made to the document with dates and descriptions.
