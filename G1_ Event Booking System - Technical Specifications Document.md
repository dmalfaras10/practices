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

This paper presents the purpose, scope, features, user roles, and requirements of the proposed G1 Event Booking System. It outlines the system’s expected functionalities and operational environment, as well as the assumptions and dependencies considered during development. As a mock system and side project, the application focuses on demonstrating the fundamental concepts of web-app development, database management, user authentication, and booking management, and thus, is not intended to be fully complete in functionalities outside the disclosed scope.

### **Purpose**:

  The purpose of the G1 Event Booking System is to develop a web-based event ticketing platform that provides users with a convenient and organized way to discover events, view event details, book tickets, and manage their bookings. The system aims to simplify the booking process by allowing users to check event schedules and ticket availability, access digital tickets, and review their booking history. It also aims to enhance user experience through membership and subscription features, offering exclusive benefits, which may include special discounts, presale access, and member-only offers.
  
  Additionally, the system will serve as a management tool for administrators, enabling them to create, update, and manage event listings, monitor bookings, and maintain user records. By centralizing event information and booking activities, the system aims to improve the organization and efficiency of event management. The primary beneficiaries are event attendees and administrators who manage the platform, with the overall goal of providing a user-friendly and reliable event booking experience. 

### **Scope**:

  The scope of the G1 Event Booking System encompasses the development of a web-based platform that aims to simplify event discovery, ticket booking, and booking management. The system will allow users to register and login to their accounts, browse available events, view event details and ticket availability, book tickets, access booking confirmations, and manage their bookings. It will also include membership and subscription features that provide eligible users with exclusive benefits, such as special discounts, presale access, and member-only promotions. Administrators will be responsible for creating, updating, publishing, and managing event listings, ticket categories, membership plans, user records, and booking information. Physical ticket printing and delivery, transportation and accommodation booking, venue management, and a separate mobile application will remain outside the project’s scope.

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

  The G1 Event Booking System is a web-based application designed to provide a centralized platform where users can browse upcoming events, view event details, check ticket availability, and purchase tickets online. It aims to simplify the booking process by reducing manual procedures and making event information more accessible.
  
  The system will serve different users, including event attendees and administrators. Users can register and log in, purchase tickets, access digital tickets, view booking history, and manage membership benefits. Administrators can create and manage events, organize ticket categories, monitor bookings and transactions, and maintain user records.

### **Product Functions**:

  The G1 Event Booking System will provide the following high-level functionalities:
  
  1. **User Registration and Authentication**  
      * Users are able to create accounts, log in, log out, and manage their profile information securely  
  2. **Event Browsing and Search**   
      * Enables users to browse upcoming events, search for specific events, view event details, check ticket availability, and explore  Bronze, Silver, and Gold ticket options.   
  3. **Administrative Management**   
      * Enables administrators to manage user records, monitor ticket sales and booking transactions, track ticket availability, and oversee event operations.   
  4. **Event Booking & Payment**  
      * Enables users to select tickets, complete online bookings, and process payments through an integrated payment service.   
  5. **Booking Management & Ticket Management**  
      * Generates booking references and digital tickets for successful transactions. Allows users to view booking history, check ticket status, and access their ticket information.   
  6. **Membership Subscription**  
      * Enables users to explore and subscribe to Bronze, Silver, and Gold membership plans to unlock exclusive perks such as ticket discounts, presale access, and member-only offers. Allows users to monitor their subscription status and manage plan renewals through their accounts.

### **User Classes and Characteristics**:

  The system will support two primary user classes:
  
  * **Users/Attendees**  
    * Individuals who access the platform to:  
      * Browse events  
      * View event details  
      * Purchase tickets  
      * Manage bookings  
      * Access digital tickets  
      * Manage their profiles  
      * Experience membership benefits  
    * The users’ access will be limited to their:  
      * Personal account  
      * Bookings  
      * Available event services  
  * **System Admins**  
    * System administrators are responsible for:  
      * Managing, and maintaining the platform's event-related information  
      * Managing, and maintaining booking records  
      * Creating, updating, and removing event listings  
      * Manage ticket categories and membership plans  
      * Monitor user transactions   
    * The admins’ access will include:  
      * Administrative functions necessary to oversee system operations  
      * Ensure that information is accurate and properly maintained

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
  
  * Users will have access to an internet-connected device and a compatible web browser.  
  * Users will provide accurate information when registering and managing their accounts.  
  * Administrators will provide correct and updated event details, ticket prices, and membership information.  
  * The development team will receive the necessary requirements, business rules, and workflows from the project stakeholders.  
  * Users will have the appropriate permissions to access the system's features.  
  * The selected technologies will support the required functionalities of the system.  
  * Payment transaction processing features and integration with third-party payment gateways will be implemented in the future once the MVP requirements have been finished.  
  * Email or notification service features will be implemented in the future once the MVP requirements have been finished.
  
  Dependencies
  
  The G1 Event Booking System will depend on the following resources and services: 
  
  * Database Service: MongoDB will be required to store and manage user accounts, event details, booking records, and transaction information.  
  * Application Technologies: Vue.js, Node.js, and Express.js will be required to develop and operate the frontend and backend components.  
  * Hosting Environment: A suitable hosting platform will be needed to make the application accessible online.  
  * Internet Connectivity: A stable internet connection will be necessary for users and administrators to access the system.  
  * Payment Gateway: If online payment integration is implemented, the system will depend on a third-party payment provider to process transactions.  
  * Email or Notification Service: If implemented, an external service may be required to send booking confirmations and ticket notifications.  
  * Stakeholder Support: Timely feedback, approved requirements, and testing from stakeholders will be necessary to guide development and testing. 


## 5. Visual Mockup Reference
- **Link or Screenshot**: [G1: Event Booking System Figma Visual Mockup](https://www.figma.com/design/GEkylbxWNNZ7c7XL5YBRtb/Event-Booking-Side-Project?node-id=0-1&t=MZUb4SSz7qulHcHh-1)

## 6. Features
- **Feature 1**: Description
- **Feature 2**: Description
- **Feature 3**: Description
- (Add more features as necessary)

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
