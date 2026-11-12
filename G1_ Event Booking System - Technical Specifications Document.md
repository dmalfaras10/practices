**Table of Contents**

1. [Introduction](#introduction)
2. [Overall Description](##overall-description)
3. [Visual Mockup Reference](#5-visual-mockup-reference)
4. [Features](#6-features)
5. [Functional Requirements](#7-functional-requirements)
6. [Non-Functional Requirements](#8-non-functional-requirements)
7. [Data Requirements](#9-data-requirements)
8. [External Interface Requirements](#10-external-interface-requirements)
9. [Glossary](#11-glossary)
10. [Appendices](#12-appendices)


# **Introduction** {#introduction}

The G1 Event Booking System is a web-based application designed to provide users with a platform convenient for browsing upcoming events, viewing event information, and booking tickets for events online. The system also provides admin privileges that allows authorized individuals to add, update, delete, and manage event listings as well as monitor user/event bookings. Users can also avail for memberships/subscriptions to get exclusive offers and benefits depending on the tier. By centralizing event information and the booking process, the system aims to make event booking more accessible, organized, and efficient.

This paper presents the purpose, scope, features, user roles, and requirements of the proposed G1 Event Booking System. It outlines the system’s expected functionalities and operational environment, as well as the assumptions and dependencies considered during development. As a mock system and side project, the application focuses on demonstrating the fundamental concepts of web-app development, database management, user authentication, and booking management, and thus, is not intended to be fully complete in functionalities outside the disclosed scope.

## **Purpose:** {#purpose:}

The purpose of the G1 Event Booking System is to develop a web-based event ticketing platform that provides users with a convenient and organized way to discover events, view event details, book tickets, and manage their bookings. The system aims to simplify the booking process by allowing users to check event schedules and ticket availability, access digital tickets, and review their booking history. It also aims to enhance user experience through membership and subscription features, offering exclusive benefits, which may include special discounts, presale access, and member-only offers.

Additionally, the system will serve as a management tool for administrators, enabling them to create, update, and manage event listings, monitor bookings, and maintain user records. By centralizing event information and booking activities, the system aims to improve the organization and efficiency of event management. The primary beneficiaries are event attendees and administrators who manage the platform, with the overall goal of providing a user-friendly and reliable event booking experience. 

## **Scope:** {#scope:}

The scope of the G1 Event Booking System encompasses the development of a web-based platform that aims to simplify event discovery, ticket booking, and booking management. The system will allow users to register and login to their accounts, browse available events, view event details and ticket availability, book tickets, access booking confirmations, and manage their bookings. It will also include membership and subscription features that provide eligible users with exclusive benefits, such as special discounts, presale access, and member-only promotions. Administrators will be responsible for creating, updating, publishing, and managing event listings, ticket categories, membership plans, user records, and booking information. Physical ticket printing and delivery, transportation and accommodation booking, venue management, and a separate mobile application will remain outside the project’s scope.

## **Definitions, Acronyms, and Abbreviations:** {#definitions,-acronyms,-and-abbreviations:}

The following terms are used throughout the documentation to describe the different components, and aspects of the G1 Event Booking System

| G1 Event Booking System | Refers to the web-based application that allows users to browse events, and create bookings |
| :---- | :---- |
| User | Refers to an individual visiting the website to browse events, create bookings, and update their profile |
| Admin | Refers to an authorized individual responsible for creating, updating, managing events, and overseeing booking records |
| Event | Refers to an organized activity, such as a concert listed in the system |
| Booking | Refers to a record created when a user submits a request to reserve a ticket or more for an event |
| Database | Refers to an organized collection of data used to store and manage user accounts, event information, and booking information (Silberschatz et al., 2020\)  |

## **References:** {#references:}

Coulouris, G., Dollimore, J., Kindberg, T., & Blair, G. (2011). *Distributed systems: Concepts and design* (5th ed.). Addison-Wesley.

Silberschatz, A., Korth, H. F., & Sudarshan, S. (2020). *Database system concepts* (7th ed.). McGraw-Hill Education.

Sommerville, I. (2016). *Software engineering* (10th ed.). Pearson.

# 

# **Overall Description** {#overall-description}

## **Product Perspective:** {#product-perspective:}

The G1 Event Booking System is a web-based application designed to provide a centralized platform where users can browse upcoming events, view event details, check ticket availability, and purchase tickets online. It aims to simplify the booking process by reducing manual procedures and making event information more accessible.

The system will serve different users, including event attendees and administrators. Users can register and log in, purchase tickets, access digital tickets, view booking history, and manage membership benefits. Administrators can create and manage events, organize ticket categories, monitor bookings and transactions, and maintain user records.

## **Product Functions:** {#product-functions:}

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

## **User Classes and Characteristics:** {#user-classes-and-characteristics:}

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

## **Operating Environment:** {#operating-environment:}

The G1 Event Booking System will operate as a web-based application accessible through an internet-connected device and a compatible web browser. It will use the MEVN stack (MongoDB, Express.js, Vue.js, and Node.js) to support event browsing, ticket purchasing, booking management, and administrative operations. The below describes the expected operating environment of the system. 

**1\. Client Environment**

The system will be accessible through desktop computers, laptops, tablets, and smartphones using modern web browsers such as Google Chrome, Microsoft Edge, Mozilla Firefox, and Safari. The interface will be designed to accommodate different screen sizes and devices.

**2\. Application Environment**

Vue.js will be used to develop the user interface, while Node.js and Express.js will handle backend processing, application logic, and communication between the frontend and database.

**3\. Database Environment**

MongoDB will serve as the database management system for storing and managing user accounts, event details, ticket categories, membership information, booking records, and transaction details.

**4\. Hosting Infrastructure**

The application’s frontend and backend will be deployed on their suitable hosting providers. The frontend will be hosted using Github’s free hosting service. While the backend will be hosted in a cloud hosting service like Amazon’s Web Services (AWS).

**5\. Network Requirements**

A stable internet connection will be required to access the system and use its features. HTTPS will be implemented to secure communication between users and the application.

**6\. Security Infrastructure**

The system will implement user authentication via JSON Web Token, role-based access control, secure password storage utilizing Bcrypt, and appropriate safeguards for user information and booking records. If an external payment gateway is integrated, payment transactions will be processed through the selected service.

**7\. Hardware Requirements**

Users will need a computer or mobile device capable of running a modern web browser. The server will require adequate processing power, memory, and storage to handle application operations, database management, and expected user traffic.

## **Assumptions and Dependencies** {#assumptions-and-dependencies}

This section identifies the assumptions made during the development of the G1 Event Booking System and the external resources, services, and conditions required for its successful development and operation. 

The development of the G1 Event Booking System is based on the following assumptions: 

**Assumptions**

The development of the G1 Event Booking System is based on the following assumptions:

* Users will have access to an internet-connected device and a compatible web browser.  
* Users will provide accurate information when registering and managing their accounts.  
* Administrators will provide correct and updated event details, ticket prices, and membership information.  
* The development team will receive the necessary requirements, business rules, and workflows from the project stakeholders.  
* Users will have the appropriate permissions to access the system's features.  
* The selected technologies will support the required functionalities of the system.  
* Payment transaction processing features and integration with third-party payment gateways will be implemented in the future once the MVP requirements have been finished.  
* Email or notification service features will be implemented in the future once the MVP requirements have been finished.

**Dependencies**

The G1 Event Booking System will depend on the following resources and services: 

* **Database Service**: MongoDB will be required to store and manage user accounts, event details, booking records, and transaction information.  
* **Application Technologies**: Vue.js, Node.js, and Express.js will be required to develop and operate the frontend and backend components.  
* **Hosting Environment:** A suitable hosting platform will be needed to make the application accessible online.  
* **Internet Connectivity**: A stable internet connection will be necessary for users and administrators to access the system.  
* **Payment Gateway:** If online payment integration is implemented, the system will depend on a third-party payment provider to process transactions.  
* **Email or Notification Service:** If implemented, an external service may be required to send booking confirmations and ticket notifications.  
* **Stakeholder Support:** Timely feedback, approved requirements, and testing from stakeholders will be necessary to guide development and testing. 

# **Visual Mockup Reference** {#visual-mockup-reference}

[G1: Event Booking System Visual Mockup Link](https://www.figma.com/design/GEkylbxWNNZ7c7XL5YBRtb/Event-Booking-Side-Project?node-id=0-1&t=MZUb4SSz7qulHcHh-1)**:**  
https\://www\.figma.com/design/GEkylbxWNNZ7c7XL5YBRtb/Event-Booking-Side-Project?node-id=0-1\&t=MZUb4SSz7qulHcHh-1

# 

# **Features** {#features}

* ## **Search & Navigation** {#search-&-navigation}

  * The Search and Navigation feature allows users to find events and shows through a search bar and navigate the website using its main pages. It provides access to the Homepage, Event Listings, About Us, Contact Us, and Membership pages, ensuring a convenient and organized browsing experience

* ## **User Accounts & Profile Management** {#user-accounts-&-profile-management}

  * The User Accounts and Profile Management feature allows users to register, log in, and securely manage their personal information. Users can update their profiles, change account settings, view booking history, and check upcoming events. The system also provides password recovery functionality to help users regain access to their accounts.

* ## **Homepage & Featured Shows** {#homepage-&-featured-shows}

  * The Homepage displays featured performances, popular events, and upcoming shows through a hero carousel and event highlights. It presents essential information, including event dates, venues, and ticket prices, along with quick links to important pages. A Frequently Asked Questions (FAQ) section is also provided to address common inquiries about bookings, venues, and event policies.

* ## **Event Listings**  {#event-listings}

  * The Event Listings feature allows users to browse available events and view their images, dates, venues, and ticket prices. Events can be organized by category and month, with search and filtering options to help users find events based on criteria such as location, venue, price, and genre. An interactive calendar may also be provided to support date-based event discovery. The page can display ticket availability, event announcements, and special promotions.

* ## **Event Details & Booking** {#event-details-&-booking}

  * The Event Details and Booking feature provides comprehensive information about each event, including its description, schedule, venue, performers, and applicable rules. Users can review available ticket categories, compare prices, select tickets, and view an order summary before proceeding to payment. Upon successful payment, the system provides a booking confirmation and access to digital ticket information.

* ## **Contact Us and About Us Page** {#contact-us-and-about-us-page}

  * The About Us page provides information about the organization, its background, and the services it offers. The Contact Us page displays contact details, such as email addresses, phone numbers, and social media accounts. It also includes a contact form where users can submit inquiries, feedback, and concerns, along with links to relevant terms and policies.

* ## **Membership and Subscriptions** {#membership-and-subscriptions}

  * This feature presents available membership plans—such as Bronze, Silver, and Gold—along with their respective pricing and benefits. It allows users to compare membership tiers and review eligible perks, including ticket discounts, priority booking, presale access, and exclusive offers. Additionally, the system enables users to register for a membership, view their current status, and manage renewals or upgrades when applicable.

* ## **Email and Notifications** {#email-and-notifications}

  * This feature keeps users informed about critical activities and updates regarding their accounts, bookings, and memberships. The system sends email notifications for successful bookings, payment confirmations, digital ticket availability, and membership status changes or renewals. It also provides automated reminders for upcoming events, schedule modifications, cancellations, and key platform announcements to maintain clear, reliable communication with users.

# 

# **Functional Requirements** {#functional-requirements}

The following use cases define the core functional requirements and user interactions for the proposed G1 Event Booking System, which caters to concerts and special events. Designed to translate high-level client goals into actionable technical specifications, this section outlines the foundational workflows for event discovery, account management, and standard ticket purchasing. Furthermore, it specifically details the specialized processes for securing exclusive VIP packages and celebrity meet-and-greets, ensuring the platform delivers an elevated customer experience and increases the perceived value of premium offerings compared to existing market solutions. 

## **Use Case 1: Register and Manage User Account**  {#use-case-1:-register-and-manage-user-account}

**Title:** User Account Registration and Profile Management  
**Description:** Allows users to create accounts, authenticate, update profile information, and access their booking history.  
**Actors:** Guest, Registered User  
**Preconditions:** The guest has access to the application and has a valid email address that is not yet registered.  
**Postconditions:** The account is created, accessed, or updated successfully.

**Main Flow:**

1. The user selects the registration or login option.  
2. The system displays the appropriate form.  
3. The user enters the required information.  
4. The system validates the submitted information.  
5. The system creates the account or authenticates the user.  
6. The user can access their profile and available account features.

**Alternate Flows:**

* **4a.** If the required fields are empty or in the wrong format (for example, an invalid email), the system shows an error message and asks the user to correct them.  
* **4b.** If the password does not meet the requirements, the system explains what is needed and asks the user to enter a new one.  
* **4c.** If the email is already registered, the system informs the user and offers to log in or reset the password.  
* **5a.** If the login credentials are incorrect, the system shows an error message and lets the user try again.  
* **5b.** If the user forgot their password, they select “Forgot password”. The system sends a reset link to their email, and the user sets a new password.  
* **6a.** If the user is not logged in and tries to open a profile or booking page, the system redirects them to the login page.  
* **6b.** If the user updates their profile with invalid information, the system rejects the update, shows what is wrong, and keeps the previous details.

## **Use Case 2: Browse Events and View Event Details** {#use-case-2:-browse-events-and-view-event-details}

**Title:** Event Listings

**Description:** Allows users to browse, search, and filter events and view detailed event information.

**Actors:** Guests, Registered users.

**Preconditions:** Event information is available in the system.

**Postconditions:** The user views the selected event's information and ticket availability.

**Main Flow:**

1. The user opens the event listings page.  
2. The system displays available events and relevant information.  
3. The user searches or filters events by category, date, location, venue, price, or genre.  
4. The system displays matching results.  
5. The user selects an event.  
6. The system displays its description, schedule, venue, performers, rules, and available ticket categories.

**Alternate Flows:**

* **2a.** If there are no events available, the system displays a message that no events are currently listed.  
* **2b.** If the events fail to load (for example, a connection problem), the system shows an error message and lets the user retry.  
* **4a.** If no events match the search or filters, the system shows a “No results found” message and suggests clearing the filters or viewing upcoming events.  
* **4b.** If the search text is invalid, the system asks the user to enter a different keyword.  
* **5a.** If the selected event is no longer available (for example, it was removed or cancelled), the system informs the user and returns them to the event listings.  
* **6a.** If all tickets for the event are sold out, the system shows the event details with a “Sold out” label and disables the option to select tickets.  
* **6b.** If the event information cannot be loaded, the system shows an error message and lets the user go back or retry.

## 

## 

## 

## **Use Case 3: Book Tickets and Complete Payment** {#use-case-3:-book-tickets-and-complete-payment}

**Title:** Event Booking and Payment

**Description:** Allows users to select tickets, review booking details, and complete online payments.

**Actors:** Registered users, payment gateway.

**Preconditions:** The selected event is available, tickets can be purchased, and the user meets the booking requirements.

**Postconditions:** A successful transaction updates the booking and seat statuses to confirmed/booked, records the payment, and generates digital tickets. 

**Main Flow:**

1. The user selects an event and ticket category (ticket type).  
2. The system displays ticket prices, remaining tier quantities, and seat availability.   
3. The user selects the desired ticket quantity and specific seats   
4. The system calculates the total cost and displays the booking summary.   
5. The user confirms the selection to proceed to checkout.  
6. The system creates a booking record with a timer and locks the selected seats for a limited time.   
7. The user selects a payment method, and the system creates a payment record and submits the request to the payment gateway.  
8. The system verifies the payment result.  
9. Upon successful payment, the system updates the payment and booking statuses to confirmed, marks the seats as booked, and records the tickets.  
10. The system displays the booking confirmation and makes the ticket available to the user.

**Alternate Flows:**

* **1a.** If the user is not logged in, the system redirects them to log in or register, then returns them to the booking.  
* **2a.** If the selected ticket type is sold out, the system shows it as unavailable and asks the user to choose another category.  
* **3a.** If the quantity is more than the available tickets or more than the allowed limit, the system shows an error and asks the user to enter a valid quantity.  
* **3b.** If a selected seat is already booked or locked by another user during checkout, the system notifies the user to select a different seat.   
* **4a.** If the user has an active membership, the system applies the membership discount to the total before showing the summary.  
* **6a.** If the user cancels or leaves before paying, the system updates the pending booking to cancelled and releases the locked seats.   
* **6b.** If the countdown timer runs out before payment is completed, the system expires the pending booking, releases the held seats, and informs the user.   
* **7a.** If the payment gateway is unavailable, the system shows an error message and asks the user to try again while the hold timer remains active.   
* **8a.** If the payment fails or is declined, the system records the failed attempt, displays the reason, and lets the user retry or choose another payment method before the hold expires.   
* **8b.** If the payment is still pending, the system shows a pending status and does not issue tickets until the payment is confirmed.  
* **9a.** If the payment succeeds but the booking cannot be saved, the system informs the user and flags the transaction for review or refund, so the user is not charged without a ticket.

## 

## **Use Case 4: Manage Events and System Records** {#use-case-4:-manage-events-and-system-records}

**Title:** Administrative Management

**Description:** Allows administrators to maintain event listings, ticket categories, membership plans, user records, booking transactions and override booking statuses when needed.

**Actors:** System administrators.

**Preconditions:** The administrator is authenticated and has the required permissions.

**Postconditions:** The selected information is created, updated, or managed successfully.

**Main Flow:**

1. The administrator logs in to the system.  
2. The system verifies the administrator's credentials and permissions.  
3. The administrator selects a management function.  
4. The administrator creates, updates, or removes permitted records.  
5. The system validates and saves the changes.  
6. The system displays a confirmation of the completed operation.

**Alternate Flows:**

* **2a.** If the credentials are incorrect, the system shows an error message and lets the administrator try again.  
* **2b.** If the account does not have administrator permissions, the system denies access and redirects the user to the homepage or login page.  
* **3a.** If the administrator’s session expires, the system asks them to log in again, then returns them to the management function.  
* **4a.** If the administrator tries to change a record they do not have permission to manage, the system denies the action and shows a message.  
* **4b.** If the administrator tries to remove a record that is in use (for example, an event with existing bookings), the system warns them and either blocks the removal or offers to archive or cancel it instead.  
* **4c.** If the administrator cancels the operation before saving, the system discards the changes and keeps the original record.  
* **5a.** If the entered information is missing or invalid (for example, an event end date before its start date, or a negative ticket price), the system shows what is wrong and does not save the changes.  
* **5b.** If the record was changed by another administrator in the meantime, the system warns about the conflict and asks them to review the latest version before saving.  
* **5c.** If the changes cannot be saved because of a system or database error, the system shows an error message and keeps the previous record unchanged.

## **Use Case 5: Membership and Subscription Benefits** {#use-case-5:-membership-and-subscription-benefits}

**Title:** Membership and Subscription 

**Description:** Allows users to view membership plans, register for a plan, and access applicable benefits. Users can also view their membership status and renew their membership when applicable. 

**Actors:** Registered users, payment gateway.

**Preconditions:** The user is logged in, and membership plans are available.

**Postconditions:** The user's membership status is recorded or updated.

**Main Flow:**

1. The user opens the Membership page.  
2. The system displays available plans, prices, and benefits.  
3. The user compares plans and selects a preferred option.  
4. The system displays the selected plan's details.  
5. The user confirms the membership registration. If the selected plan is a paid plan, the user completes the payment.   
6. The system records the membership and displays its status and benefits.

**Alternate Flows:**

* **1a.** If the user is not logged in, the system redirects them to log in or register, then returns them to the Membership page.  
* **2a.** If no membership plans are available, the system shows a message that no plans are currently offered.  
* **2b.** If the plans fail to load, the system shows an error message and lets the user retry.  
* **3a.** If the user already has an active membership, the system shows their current plan and status, and offers to renew or change plans instead of registering again.  
* **5a.** If the user cancels before confirming, the system returns them to the Membership page and no membership is recorded.  
* **5b.** For a paid plan, if the payment fails or is declined, the system shows the reason and lets the user retry or use another payment method. No membership is recorded.  
* **5c.** For a paid plan, if the payment is still pending, the system shows a pending status and does not activate the membership until the payment is confirmed.  
* **5d.** For a paid plan, if the payment gateway is unavailable, the system shows an error message and asks the user to try again later.  
* **6a.** If the membership cannot be saved after a successful payment, the system informs the user and flags the transaction for review or refund.  
* **6b.** If the membership has expired and the user chooses to renew, the system extends or restarts it and shows the updated status. 

## **Use Case 6: Receive Email Notifications** {#use-case-6:-receive-email-notifications}

**Title:** Email and Notifications

**Description:** Sends users important updates about bookings, payments, digital tickets, memberships, and events.

**Actors:** Registered users, notification service.

**Preconditions:** A relevant system event occurs, and the required notification details are available.

**Postconditions:** The notification is sent, and its delivery status is recorded when supported.

**Main Flow:**

1. The system detects an event requiring a notification, such as a successful booking or membership registration.  
2. The system prepares an email containing the relevant information.  
3. The notification service processes the email.  
4. The system records the notification status when supported.  
5. The user receives the email if delivery is successful.

**Alternate Flows:**

* **1a.** If the event does not require a notification (for example, the user has turned off optional notifications), the system does not send an email.  
* **2a.** If the required details are missing or incomplete (for example, no email address on file), the system does not send the email and records the problem for review.  
* **3a.** If the notification service is unavailable, the system keeps the notification in a queue and tries again later.  
* **3b.** If sending still fails after several attempts, the system marks the notification as failed and records it for review. The booking, payment or membership itself is not affected.  
* **4a.** If the notification status cannot be recorded, the system still sends the email and logs the error.  
* **5a.** If the email address is invalid or the email bounces, the system marks the notification as undelivered. The user can still see their booking or ticket in My Tickets or their account.  
* **5b.** If the email goes to the user’s spam folder or is not received, the user can still view the information in the system and, where applicable, resend the ticket or confirmation.

## **System Features** {#system-features}

The following functional requirements define the expected system behavior for each major feature. Priorities indicate the relative importance of each feature to the core operation of the system.

### **Feature 1: Search and Navigation**

* Description: The system shall allow users to search for events and navigate the main website pages.  
* Priority: High  
* Inputs: Search keywords, selected navigation links, and search criteria.  
* Processing: The system shall process search queries, retrieve matching events, and load the selected page.  
* Outputs: Search results, event listings, or the requested page.  
* Error Handling: The system shall display a message when no results are found or a page cannot be loaded.

### **Feature 2: User Accounts and Profile Management**

* Description: The system shall support user registration, login, logout, profile updates, booking history, and password recovery.  
* Priority: High  
* Inputs: Registration details, login credentials, profile information, and password recovery requests.  
* Processing: The system shall validate user information, authenticate credentials, manage account sessions, and save permitted profile changes.  
* Outputs: Account confirmation, login status, updated profile information, booking history, and password recovery instructions.  
* Error Handling: The system shall reject invalid information, prevent duplicate registrations, deny unauthorized access, and display appropriate error messages.

### 

### 

### **Feature 3: Homepage and Featured Shows**

* Description: The system shall display featured events, upcoming shows, event information, and FAQs.  
* Priority: Medium  
* Inputs: Homepage content, featured event records, and user selections.  
* Processing: The system shall retrieve and display available featured events and related information.  
* Outputs: Homepage content, event highlights, ticket prices, and FAQ information.  
* Error Handling: The system shall display an appropriate message if featured content is unavailable.

### **Feature 4: Event Discovery and Listings**

* Description: The system shall allow users to browse, search, and filter events based on available event information.  
* Priority: High  
* Inputs: Event categories, dates, locations, venues, prices, and genres.  
* Processing: The system shall retrieve event records and filter results according to the user's selected criteria.  
* Outputs: Matching event listings, event details previews, ticket prices, and availability information.  
* Error Handling: The system shall notify users when no events match their criteria or event information cannot be retrieved.

### **Feature 5: Event Details and Booking**

* Description: The system shall allow users to view event information, select tickets, review booking summaries, and complete payments.  
* Priority: High  
* Inputs: Selected event, ticket category, ticket quantity, assigned seat, booking details, and payment information handled through the configured payment service.  
* Processing: The system shall validate ticket and seat availability, calculate the total cost, submit payment requests, verify transaction results, and record successful bookings.  
* Outputs: Booking reference, payment status, booking confirmation, and digital ticket information.  
* Error Handling: The system shall prevent bookings that exceed available ticket quantities, notify users of failed payments, and avoid confirming bookings before payment is verified.

### **Feature 6: About Us and Contact Us**

* Description: The system shall display organizational information, contact details, and a form for submitting inquiries.  
* Priority: Medium  
* Inputs: Contact form details, user inquiries, and feedback.  
* Processing: The system shall validate submitted information and process inquiries through the configured submission method.  
* Outputs: Organizational information, contact details, and submission confirmation.  
* Error Handling: The system shall identify missing or invalid fields and notify users when an inquiry cannot be submitted.

### **Feature 7: Membership and Subscription**

* Description: The system shall display membership plans and allow users to register for memberships and view applicable benefits.  
* Priority: Medium  
* Inputs: Selected membership plan, user account details, and payment information if required.  
* Processing: The system shall validate plan availability, process required payments, and update membership records and status.  
* Outputs: Membership details, registration confirmation, membership status, and applicable benefits.  
* Error Handling: The system shall notify users of unavailable plans, unsuccessful payments, and invalid membership requests.

### **Feature 8: Email and Notifications**

* Description: The system shall send email notifications for relevant booking, payment, membership, and event updates.  
* Priority: Medium  
* Inputs: User email address, booking details, transaction status, membership information, and event updates.  
* Processing: The system shall generate notification messages and submit them to the configured email service.  
* Outputs: Booking confirmations, payment notifications, digital ticket information, membership updates, and relevant event announcements.  
* Error Handling: The system shall handle failed notification requests, record delivery status when supported, and retry unsuccessful deliveries when configured.

# 

# **Non-Functional Requirements** {#non-functional-requirements}

## **Performance** {#performance}

* The website should load pages efficiently under normal operating conditions.  
* API requests should respond within an acceptable time under normal workloads.  
* Database queries should be optimized using appropriate indexes.  
* Event listings should support pagination to avoid loading excessive records at once.  
* Event searches and filtering should return relevant results efficiently.  
* Ticket inventory must be updated safely to prevent overselling when multiple users purchase tickets simultaneously.  
* Membership eligibility and discount calculations should be processed efficiently during checkout.  
* Payment processing should provide timely status updates without unnecessarily delaying other website operations.  
* The system should handle an increasing number of users, events, bookings, and tickets without significant performance degradation.

## **Security** {#security}

* Passwords must be securely hashed before being stored in the database using Bcrypt.  
* User authentication and role-based authorization must be implemented using JSON Web Token (JWT).  
* Input validation must be performed on the backend before processing user requests.  
* Payment information must be handled securely through the selected payment gateway.  
* Only authorized administrators can manage system records and configurations.  
* Membership perks must be validated by the backend before discounts or exclusive access are granted.  
* Users must only access their bookings, tickets, and membership and subscription information unless additional permissions are explicitly granted.  
* API endpoints must verify authentication and authorization before performing restricted operations.  
* The system must protect against common web application vulnerabilities, including injection attacks, cross-site scripting, and unauthorized access.  
* Sensitive information, such as passwords, authentication tokens, and payment credentials, must not be exposed in API responses or application logs.  
* Database credentials and API keys must be stored securely using environment variables or an appropriate secrets-management mechanism.  
* Payment notifications from the payment gateway must be verified before updating payment or booking statuses.

## **Usability** {#usability}

* The website must provide a simple, consistent, and user-friendly interface.  
* Navigation and event information must be clear and easy to understand.  
* The interface must support desktop, tablet, and mobile devices.  
* Membership and subscription prices, ticket prices, and applicable discounts must be clearly displayed.  
* Users must be able to view event details, select tickets, and complete checkout through a straightforward process.  
* The membership and subscription page must clearly explain subscription benefits, eligibility requirements, duration, and expiration conditions.  
* The system must provide clear confirmation messages for successful registration, booking, payment, and subscription enrollment.  
* Error messages must explain the problem and, where appropriate, indicate how the user can resolve it.  
* Text, buttons, forms, and navigation elements should remain readable and accessible across supported screen sizes.  
* The website should provide clear ticket statuses so users can distinguish valid, used, cancelled, and refunded tickets where applicable.

## **Reliability** {#reliability}

* The system must maintain consistent booking, payment, ticket, and subscription records.  
* Failed transactions must not generate confirmed paid tickets.  
* Database backups should be maintained according to the deployment environment and recovery requirements.  
* The system must handle errors without exposing sensitive information.  
* Repeated payment notifications must not create duplicate bookings or duplicate ticket issuance.  
* Ticket availability must remain accurate during simultaneous purchase attempts.  
* A ticket must not be successfully redeemed more than once.  
* Subscription benefits must not be granted when the subscription is inactive, expired, or otherwise ineligible.  
* Temporary failures in external services must not incorrectly mark unsuccessful transactions as completed.  
* The system must distinguish pending, successful, failed, cancelled, and refunded payment states as applicable.  
* Database updates involving related booking, payment, and ticket records must use appropriate transactions or other consistency mechanisms.  
* The system should recover gracefully from unexpected server errors and temporary database connection failures.  
* Appropriate error logs should be maintained to help developers identify and resolve operational issues.

## **Supportability** {#supportability}

* The source code must be organized into maintainable modules.  
* API endpoints and database structures must be documented.  
* Version control should be used during development.  
* The system must support future updates and additional membership perks.  
* Testing must cover the main ticketing and membership functions.  
* Changes to existing features must be tested to reduce the risk of breaking other system functions.  
* Dependencies should be reviewed and updated when necessary to address compatibility issues and security vulnerabilities.  
* The database structure should be designed to allow additional fields and features without unnecessary duplication of stored information.

# 

# 

# **Data Requirements** {#data-requirements}

The Data Requirements section defines how the G1 Event Booking System stores, organizes, validates, retrieves, updates, and protects its information.

The system uses MongoDB as its database, Node.js and Express.js for backend processing, Vue.js for the user interface, and Mongoose as the Object Data Modeling (ODM) library.

## **Data Models** {#data-models}

![][image1]

## 

## **Data Dictionary** {#data-dictionary}

The data dictionary defines the nine MongoDB collections used by the system: Users, Subscription\_Plan, User\_Subscriptions, Events, Venues, Seats, Bookings, Payments, and Tickets. Every document uses an auto-generated ObjectId as its primary key, relates to other documents via ObjectId references, stores monetary values as Decimal128, and tracks record creation and updates with DateTime timestamps.

**Users**

| Field | Type | Key / Reference | Required | Description |
| :---- | :---- | :---- | :---- | :---- |
| \_id | ObjectId | PK | Yes | Unique user identifier |
| firstName | String | None | Yes | User given name |
| lastName | String | None | Yes | User family name |
| email | String | None | Yes | Unique login email |
| password | String | None | Yes | Hashed account password |
| mobileNo | String | None | No | User contact number |
| isAdmin | Boolean | None | Yes | Administrator role flag |
| createdAt | DateTime | None | Yes | Record creation timestamp |
| updatedAt | DateTime | None | Yes | Last update timestamp |

**Subscription\_Plan**

| Field | Type | Key / Reference | Required | Description |
| :---- | :---- | :---- | :---- | :---- |
| \_id | ObjectId | PK | Yes | Unique plan identifier |
| user\_id | ObjectId | FK to Users | Yes | Managing admin reference |
| subscriptionType | String | None | Yes | Membership tier name |
| subscriptionPrice | Decimal128 | None | Yes | Plan purchase price |
| subscriptionPerks | String | None | No | Included tier benefits |
| subscriptionStatus | String | None | Yes | Plan availability status |
| createdAt | DateTime | None | Yes | Record creation timestamp |
| updatedAt | DateTime | None | Yes | Last update timestamp |

**User\_Subscriptions**

| Field | Type | Key / Reference | Required | Description |
| :---- | :---- | :---- | :---- | :---- |
| \_id | ObjectId | PK | Yes | Unique enrollment identifier |
| user\_id | ObjectId | FK to Users | Yes | Subscribed customer reference |
| subscriptionPlan\_id | ObjectId | FK to Subscription\_Plan | Yes | Selected plan reference |
| subscriptionStatus | String | None | Yes | Active, expired, cancelled |
| startDate | DateTime | None | Yes | Membership start timestamp |
| endDate | DateTime | None | Yes | Membership expiration timestamp |
| createdAt | DateTime | None | Yes | Record creation timestamp |
| updatedAt | DateTime | None | Yes | Last update timestamp |

**Events**

| Field | Type | Key / Reference | Required | Description |
| :---- | :---- | :---- | :---- | :---- |
| \_id | ObjectId | PK | Yes | Unique event identifier |
| user\_id | ObjectId | FK to Users | Yes | Managing admin reference |
| venue\_id | ObjectId | FK to Venues | Yes | Hosted venue reference |
| eventImage | String | None | No | Event banner path |
| eventName | String | None | Yes | Official event title |
| eventDescription | String | None | No | Full event details |
| eventCategory | String | None | Yes | Event genre classification |
| eventStartDateTime | DateTime | None | Yes | Event start timestamp |
| eventEndDateTime | DateTime | None | Yes | Event end timestamp |
| eventStatus | String | None | Yes | Upcoming, ongoing, cancelled |
| ticketType | Array | Embedded Subdocuments | Yes | Available ticket tiers |
| ticketType.ticketType\_id | ObjectId | PK (Subdocument) | Yes | Unique tier identifier |
| ticketType.ticketType | String | None | Yes | Tier name |
| ticketType.ticketPrice | Decimal128 | None | Yes | Unit price |
| ticketType.ticketPerks | String | None | No | Included tier perks |
| ticketType.ticketDescription | String | None | No | Tier access details |
| ticketType.availableQuantity | Number | None | Yes | Remaining unsold inventory |
| artistName | String | None | Yes | Performing artist name |
| createdAt | DateTime | None | Yes | Record creation timestamp |
| updatedAt | DateTime | None | Yes | Last update timestamp |

**Venues**

| Field | Type | Key / Reference | Required | Description |
| :---- | :---- | :---- | :---- | :---- |
| \_id | ObjectId | PK | Yes | Unique venue identifier |
| venueName | String | None | Yes | Official venue name |
| venueAddress | String | None | Yes | Physical street address |
| mapURL | String | None | No | Location map link |
| venueCapacity | Number | None | Yes | Maximum attendee capacity |
| createdAt | DateTime | None | Yes | Record creation timestamp |
| updatedAt | DateTime | None | Yes | Last update timestamp |

**Seats**

| Field | Type | Key / Reference | Required | Description |
| :---- | :---- | :---- | :---- | :---- |
| \_id | ObjectId | PK | Yes | Unique seat identifier |
| venue\_id | ObjectId | FK to Venues | Yes | Parent venue reference |
| event\_id | ObjectId | FK to Events | Yes | Associated event reference |
| seatSection | String | None | Yes | Venue section name |
| seatRow | String | None | Yes | Section row identifier |
| seatNumber | Number | None | Yes | Individual seat number |
| seatStatus | String | None | Yes | Available, held, booked |
| expiresAt | DateTime | None | No | Seat lock expiration |
| lockedBy | ObjectId | FK to Users | No | User holding seat |
| isActive | Boolean | None | Yes | Seat availability flag |

**Bookings**

| Field | Type | Key / Reference | Required | Description |
| :---- | :---- | :---- | :---- | :---- |
| \_id | ObjectId | PK | Yes | Unique booking identifier |
| user\_id | ObjectId | FK to Users | Yes | Booking customer reference |
| event\_id | ObjectId | FK to Events | Yes | Booked event reference |
| items | Array | Embedded Subdocuments | Yes | Reserved ticket line-items |
| items.ticketType\_id | ObjectId | FK to Events.ticketType | Yes | Selected tier reference |
| items.ticketType | String | None | Yes | Snapshot tier name |
| items.ticketQuantity | Number | None | Yes | Quantity of tickets |
| items.ticketPrice | Decimal128 | None | Yes | Snapshot unit price |
| items.seat\_ids | Array of ObjectId | FK to Seats | No | Reserved seat references |
| bookingStatus | String | None | Yes | Pending, confirmed, cancelled |
| expiresAt | DateTime | None | No | Pending checkout expiration |
| totalAmount | Decimal128 | None | Yes | Total payable amount |
| bookingRef | String | None | Yes | Public booking code |
| createdAt | DateTime | None | Yes | Record creation timestamp |
| updatedAt | DateTime | None | Yes | Last update timestamp |

**Payments**

| Field | Type | Key / Reference | Required | Description |
| :---- | :---- | :---- | :---- | :---- |
| \_id | ObjectId | PK | Yes | Unique payment identifier |
| booking\_id | ObjectId | FK to Bookings | No | Settled booking reference |
| userSubscription\_id | ObjectId | FK to User\_Subscriptions | No | Settled subscription reference |
| paymentMethod | String | None | Yes | Selected payment channel |
| paymentStatus | String | None | Yes | Pending, succeeded, failed |
| totalAmount | Decimal128 | None | Yes | Total amount charged |
| transactionRef | String | None | Yes | Gateway reference number |
| paidAt | DateTime | None | No | Payment completion timestamp |
| createdAt | DateTime | None | Yes | Record creation timestamp |
| updatedAt | DateTime | None | Yes | Last update timestamp |

**Tickets**

| Field | Type | Key / Reference | Required | Description |
| :---- | :---- | :---- | :---- | :---- |
| \_id | ObjectId | PK | Yes | Unique ticket identifier |
| booking\_id | ObjectId | FK to Bookings | Yes | Parent booking reference |
| ticketType\_id | ObjectId | FK to Events.ticketType | Yes | Purchased tier reference |
| seat\_id | ObjectId | FK to Seats | No | Assigned seat reference |
| ticketCode | String | None | Yes | Unique QR string |
| ticketStatus | String | None | Yes | Valid, used, cancelled |
| createdAt | DateTime | None | Yes | Record creation timestamp |
| updatedAt | DateTime | None | Yes | Last update timestamp |

## **Database Requirements:** {#database-requirements:}

* MongoDB will store and manage user, event, venue, seat, booking, ticket, payment, and membership data.  
* Each document will have a unique identifier to ensure accurate record identification and retrieval.  
* ObjectId references will associate related documents, such as users, events, venues, seats, bookings, tickets, payments, and memberships.  
* Mongoose will be used to define schemas, establish document relationships, and validate stored data.  
* Appropriate database indexes will improve query performance, particularly for event searches, venue details, seat availability, bookings, ticket records, and membership verification.  
* Access to user profiles, booking records, payment information, and membership data must be restricted to authorized users based on their assigned roles.  
* The system must validate document references and apply appropriate rules to prevent invalid seat assignments, duplicate seat reservations, invalid ticket quantities, negative prices, incorrect venue capacities, and invalid event date ranges.  
* Personal information must be protected and retained according to the application's privacy policy and applicable regulations.  
* Database backups and recovery procedures should be configured according to the project's deployment requirements.

## **Data Storage and Retrieval:**  {#data-storage-and-retrieval:}

The backend will utilize Express.js routes and MongoDB queries to perform Create, Read, Update, and Delete (CRUD) operations on authorized records. The system will ensure efficient storage, retrieval, and management of information related to events, users, bookings, tickets, payments, seats, venue, and memberships.

* The system will retrieve and display published events, including event descriptions, schedules, venues, ticket categories, prices, available seats, and event capacity. Administrators will be able to create, update, and manage event information.  
* The system will store and manage user account information, including personal details, login credentials, contact information, and account status. Authenticated users will be able to access their own profiles, booking history, and purchased tickets.  
* The system will store and retrieve membership records, including membership types, levels, expiration dates, renewal status, and benefits. Membership eligibility will be verified before applying discounts or granting access to exclusive events and privileges.  
* The system will manage bookings and seat reservations by recording selected events, ticket categories, seat numbers, ticket quantities, booking references, and booking statuses. Seat availability will be updated accordingly to prevent duplicate reservations and overbooking.  
* The system will store payment transaction records, including payment references, amounts, methods, dates, and payment statuses. Payments must be verified before confirming bookings, updating seat availability, and issuing tickets.  
* The system will generate individual ticket records after successful payment confirmation. Each ticket will contain a unique ticket ID, event details, ticket category, assigned seat number, booking reference and ticket status for event entry verification.  
* The system will provide authorized administrators with access to user, event, booking, ticket, payment, seat, and membership records for monitoring and report generation. Role-based access control and data validation will prevent unauthorized access or modification, while data retention and deletion will follow applicable privacy requirements.

## **Entity Relationship Diagram** {#entity-relationship-diagram}

This Entity Relationship Diagram (ERD) outlines the database structure for an Event Ticketing Platform. It manages everything from event creation and venue hosting to seat selection, payments, ticket issuance, and subscription plans.  
![][image2]

* Users (USERS): Stores account details, login credentials, and user roles (customers vs. admins).     
* Events (EVENTS): Holds event details (name, category, start/end dates, venue) and ticket options.     
* Venues (VENUES): Manages physical location details, address, maps, and maximum seating capacity.    
* Seats (SEATS): Tracks specific seat assignments, live availability, and temporary seat locks during checkout.     
* Bookings (BOOKINGS): Manages customer checkout sessions, reserved seats, ticket quantities, and session expiration timers.     
* Payments (PAYMENTS): Processes transactions for both event ticket bookings and user subscriptions.     
* Tickets (TICKETS): Generates final digital tickets with unique verification codes after a successful payment.     
* Subscription Plans (SUBSCRIPTION\_PLAN): Defines available subscription tiers, pricing, and associated perks.     
* User Subscriptions (USER\_SUBSCRIPTIONS): Tracks active user subscription memberships, start dates, and expiration dates.   

# 

# **External Interface Requirements** {#external-interface-requirements}

This section specifies every boundary at which the G1 Event Booking System exchanges data, credentials, or content with an entity outside the application core. Each interface is labeled internal (owned and versioned by the development team) or external (operated by a third party and subject to that party's availability, rate limits, and breaking-change policy). The interfaces specified are: the browser-based user interface and the REST API consumed by the frontend (internal), and the managed database hosting service, payment gateway, and email/notification service (external).

## Key Interface Components {#key-interface-components}

The following reusable components recur across pages and shall behave consistently wherever they appear

| Component | Behaviour |
| :---- | :---- |
| Global Search Bar | Present in the header on every page. Accepts free-text queries across events and venues. Submits on Enter or on selection from the typeahead. |
| Header Navigation | Links to Events, VIP, Account, and Support. Renders an authenticated variant (avatar, My Tickets, Sign Out) and a guest variant (Sign In, Register). |
| Hero Carousel | Rotating banner on Homepage and VIP Exclusives. Each slide carries a single primary CTA (e.g., “Book Now”). Supports manual pause and keyboard navigation. |
| Event Card | Thumbnail, title, date, venue, category, starting price, and a real-time availability badge (Selling Fast, Low Stock, Sold Out). Clicking navigates to Event Details. |
| Ticket Selection Table | Rows per ticket tier with unit price, quantity stepper, and line subtotal. Enforces per-tier purchase limits and disables sold-out tiers. |
| Interactive Calendar | Month and agenda views. Selecting a date filters the attached listing. |
| Seat-Hold Countdown | Visible timer on Checkout showing remaining hold time. On expiry the UI releases the hold and returns the user to Event Details. |
| Membership Plan Comparison | Side-by-side columns for Bronze, Silver, and Gold plans with a "What's Included" checklist, pricing, and enrollment call-to-action. Shows the user's current plan and status when signed in. |
| Payment Status Panel | Distinct visual states for success, pending, and failed, each with recovery guidance |
| Booking History Table | Per-row booking reference, ticket status (Valid, used, cancelled), with View Details, Cancel, and Download actions. |

### 

### **Page Inventory**

The following pages constitute the external user-facing surface. Each maps to one or more functional requirements:

| Page | Route (client) | Purpose | Auth |
| :---- | :---- | :---- | :---- |
| Homepage | / | Hero carousel, featured events, upcoming shows, FAQ preview | Public |
| Event Listings | /events | Filterable, searchable catalogue with interactive calendar | Public |
| Event Details | /events/:id | Full event info, ticket tier table, rules, booking policy | Public |
| Venue Details | /venues/:id | Address, capacity, transit, layout | Public |
| Memberships | /membership | Bronze, Silver, and Gold plan comparison, perks checklist, pricing, enrollment | Public |
| Checkout | /checkout/:bookingId | Ticket checkout details, seat-hold countdown, payment form | Registered User |
| Booking Confirmation | /checkout/:bookingId/confirmation | Success state, e-ticket, VIP timeline | Registered User |
| Sign In / Register | /auth/:mode | Credential entry and account creation | Public |
| Profile | /account/profile | View and update personal details, password | Registered User |
| My Tickets | /account/tickets | Booking history, ticket status, cancel, download | Registered User |
| Contact / About | /contact | Inquiry form and company information | Public |
| Admin Dashboard | /admin | Event CRUD, booking monitoring, inventory oversight | System Admin |

## **API Interfaces** {#api-interfaces}

The backend exposes a JSON REST API consumed exclusively by the Vue.js frontend. The API is owned and versioned by the development team and is the sole mechanism through which the client reaches the database — the client never connects to MongoDB directly.

### **Conventions**

**Authentication**: POST /api/v1/auth/login returns a short-lived access token and a refresh token. The access token is sent as Authorization: Bearer \<token\> on every protected request.   
**Authorization**: Roles are guest (user not logged in), user, and admin. Every endpoint below declares its required role.

### **Endpoint Table \- Public**

| Method | Path | Auth | Purpose |
| :---- | :---- | :---- | :---- |
| POST | /auth/register | Guest | Create an account. |
| POST | /auth/login | Guest | Exchange credentials for tokens. |
| GET | /events | Public | List events. Supports q, category, genre, venue, city, priceFrom, priceTo, from, to, featured, sort, and cursor pagination. |
| GET | /events/:id | Public | Full event detail including embedded venue and ticket tiers. |
| GET | /events/calendar | Public | Events grouped by date for the interactive calendar. |
| GET | /membership | Public | Available membership plans (Bronze, Silver, Gold) with prices and perks. |
| GET | /membership/:id | Public | Single membership plan detail. |
| GET | /search | Public | Unified search across events and venues. |
| POST | /contact | Guest | Submit an inquiry from the Contact form. |

### **Endpoint Table \- Registered User**

| Method | Path | Auth | Purpose |
| :---- | :---- | :---- | :---- |
| GET | /users/me | User | Fetch the authenticated profile. |
| PATCH | /users/me | User | Update profile fields. |
| POST | /users/logout | User | Revoke the current session token. |
| PATCH | /users/me/password | User | Change password (requires current password). |
| GET | /bookings/:id | User | List the caller’s bookings (booking history). |
| POST | /bookings/:id | User | Create a booking and place a temporary seat hold. |
| GET | /bookings/:id/ticket | User | Retrieve the e-ticket payload. |
| GET | /bookings/:id/ticket.pdf | User | Download the e-ticket as PDF. |
| DELETE | /bookings/:id/delete | User | Voluntarily release a ticket and seat hold |
| POST | /payments/intent | User | Create a payment intent for a held booking. |
| GET | /payments/:id | User | Poll payment status. |
| GET | /membership/subscriptions/me | User | Retrieve the caller's membership status, plan, and benefits. |
| POST | /membership/subscriptions | User | Enroll in a membership plan (creates the subscription record). |

## 

### **Endpoint Table — System Admin**

| Method | Path | Purpose |
| :---- | :---- | :---- |
| GET | /admin/events | List all events including drafts. |
| POST | /admin/events | Create an event. |
| PATCH | /admin/events/:id | Update an event. |
| DELETE | /admin/events/:id | Remove an event. |
| GET | /admin/bookings | List all bookings with filters. |
| PATCH | /admin/bookings/:id | Override a booking status. |
| GET | /admin/contact | List submitted inquiries. |
| GET | /admin/users | List user records with search and filters. |
| PATCH | /admin/users/:id | Update a user record or administrative role. |
| GET | /admin/subscriptions | List all user subscriptions and their statuses. |
| POST | /admin/membership | Create a membership plan. |
| PATCH | /admin/membership/:id | Update plan pricing, perks, or availability status. |
| DELETE | /admin/membership/:id | Remove a membership plan. |
| GET | /admin/payments | List payment transactions with filters. |
| GET | /admin/tickets | List issued tickets and their statuses. |

### 

## **Hardware Interfaces** {#hardware-interfaces}

The application requires no specialized hardware. All hardware interaction is through standard, commodity equipment already owned by the user base.

## **Software Interfaces** {#software-interfaces}

* ### **Payment Gateway**

  Online payment processing is a post-MVP deliverable per the project assumptions. Payment information is handled ideally solely by the selected provider and the system never stores card details.

  The booking status is updated only by the backend, in response to a webhook whose signature has been verified, or an authenticated gateway status fetch. A client-side “payment succeeded” signal is never sufficient. Webhook handling must be idempotent: repeated delivery of the same event must not create duplicate bookings, double-decrement inventory, or apply duplicate payment updates.

* ### **Database Service**

  The primary database service is a managed MongoDB Atlas cluster, reached from the backend through outbound connections established by the official MongoDB Node.js driver using connection pooling.  
    
  Credentials, including connection strings, are maintained exclusively within server-side environment configuration secured by IP allowlisting and least-privilege database user access. The client never connects to Atlas. All reads and writes pass through the backend so that validation, authorization, and concurrency control are enforced in one place.

* ### **Authentication Session Store**

  JWT issuance and refresh-token storage are owned by the application backend. Refresh tokens are persisted server-side so they can be revoked. Logout and password change invalidate outstanding refresh tokens.

* ### **Notification Service**

  The notification service is an external email delivery provider (e.g., an SMTP relay or API-based email service) that the backend calls to send booking confirmations, payment notifications, digital ticket availability notices, and membership updates. The integration is internal to the backend; no client-side code calls the provider directly.  
    
  Outbound emails are accepted into an internal queue first. Deliveries that fail are retried a limited number of times; after repeated failure, the notification is marked failed and recorded for review without affecting the booking, payment, or membership it relates to. Delivery status is recorded when the provider supports it. Per the project assumptions, the notification service is a post-MVP deliverable; the interface described here is the design target.


## **Glossary** {#glossary}

| Term | Definition |
| :---- | :---- |
| **API (Application Programming Interface)** | A set of rules and protocols that allows the frontend website to communicate with the backend server and third-party services.  |
| **Application / System** | Refers to the web-based platform designed for event discovery, ticketing, and booking management.  |
| **Backend** | The server-side component responsible for processing requests, enforcing user authorization, and communicating with the database.  |
| **Booking** | The completed process of reserving and purchasing a ticket or VIP package for a specific event.  |
| **BSON (Binary JSON)** | The binary-encoded format in which MongoDB stores its documents.  |
| **Client-Server Environment** | A distributed application architecture where the user's web browser (client) requests data and services from the central database and application host (server).  |
| **Concurrency Control** | A database management mechanism used to prevent overselling of limited inventory (such as tickets and membership-dependent discounts) when multiple users attempt to purchase the same item simultaneously.  |
| **CTA (Call to Action)** | Interface elements, typically buttons (e.g., "Book Now", "Send"), designed to prompt an immediate response or action from the user.  |
| **Cursor-Based Pagination** | A data retrieval method using an identifier pointer to fetch subsets of event records sequentially without degrading query performance.  |
| **Database** | An organized collection of data used to store and manage user accounts, event information, and booking records.  |
| **Electronic Ticket (E-Ticket)** | A digital ticket generated by the system and delivered to the user upon successful payment, accessible via the user's "My Tickets" portal.  |
| **Event** | A scheduled public or private occasion, such as a concert or special show, listed on the platform for users to attend.  |
| **Frontend** | The client-side presentation layer executing in the user's browser, responsible for UI rendering and direct interaction handling.  |
| **Hero Carousel / Banner Slider** | A large, visually prominent web banner at the top of the homepage or event page that rotates to display featured tours, or promotional content.  |
| **IDE (Integrated Development Environment)** | A software application that provides comprehensive facilities to computer programmers for development.  |
| **Idempotency** | System handling ensures repeated delivery of the same webhook or request does not create duplicate bookings, double-decrement inventory, or duplicate payments.  |
| **Interactive Calendar Layout** | A visual UI component that allows users to view and filter upcoming events chronologically.  |
| **JWT (JSON Web Token)** | An authentication mechanism issuing short-lived access tokens and refresh tokens to verify user identity across API endpoints.  |
| **MEVN Stack** | The technology stack consisting of MongoDB, Express.js, Vue.js, and Node.js used to build and operate the application.  |
| **MongoDB** | The NoSQL database system used by the application to store data in flexible, JSON-like collections.  |
| **Mongoose (ODM)** | The Object Data Modeling library used on Node.js to define data schemas, manage document relationships, and enforce validation rules.  |
| **ObjectId** | A unique identifier used in MongoDB to distinguish individual records (documents) and map relationships between them.  |
| **Payment Gateway** | A secure, third-party e-commerce service that authorizes and processes card, e-wallet, or direct digital payments for ticket and membership purchases.  |
| **Responsive Design** | A web design approach ensuring the platform's layout and features adapt seamlessly across desktop, tablet, and smartphone screens.  |
| **REST API (Representational State Transfer API)** | An architectural style for the backend endpoints that handle client data retrieval and updates over HTTP.  |
| **Role-Based Access Control (RBAC)** | An access-management approach enforcing permissions and restrictions based on defined user classes: guest, registered user, and system admin.  |
| **Seat Hold / Temporary Hold** | A system feature that temporarily reserves a selected ticket for a user during checkout via a countdown timer, preventing others from booking it while payment finishes.  |
| **Session Token** | A unique, encrypted string generated by the server after login to authenticate the user during subsequent navigation.  |
| **System Admin** | Authorized individuals responsible for maintaining event listings, ticket categories, membership plans, user records, and booking transactions.  |
| **Ticket Tier** | The classification of tickets available for a specific event (e.g., Bronze, Silver, Gold), dictating the price and level of access.  |
| **Typeahead** | An interactive search input feature that displays matching auto-suggest results as the user types.  |
| **Users / Attendees** | Individuals visiting the website to browse events, purchase tickets, manage profiles, and access digital tickets.  |
| **Membership Plan** | A subscription tier (Bronze, Silver, or Gold) that grants recurring benefits such as ticket discounts, presale access, and member-only offers for the duration of the subscription.  |
| **WCAG 2.2 Level AA** | A widely used set of accessibility guidelines covering readability, contrast, and keyboard navigation  that serves as guidance for the platform's interface design.  |
| **Webhook** | An automated HTTP notification sent by an external payment provider to inform the backend of real-time transaction updates. |

# 

# **Appendices** {#appendices}

[image1]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAArwAAAESCAYAAAAfRAZAAABNmUlEQVR4Xu3dCfwO1eI/8GvflxCypEipRCnVjdItLbRrLyo3ipLtSio3JUpFWtxW1BXSRpSQLRHXEhGlEtm3ZN+X8/9/jt8ZZ853vt9nm5nvLJ/36zWvZ54z88zMM9vzeWbOzPxNEBERERFF2N/MAiIiIiKiKGHgJSIiIqJIY+AlIiIiokhj4CUiIiKiSGPgJSIiIqJIY+AlIiIiokhj4CUiIiKiSMs48BYtWlT87W9/Y8MmpYbCr0KFClmWK5vsGyJKnrn9sMmsIQZeNrnUUPgx8KbWEFHyzO2HTWYNuRh4iZJx9tlnc32JCBV4KWc//vgj5xNRihjU3MH5eEzGc4GBl1LBwBsdDLzJYeAlSh2Dmjs4H4/JeC4w8FIqGHijg4E3OQy8RKljUHMH5+MxGc8FBl5KBQNvdDDwJoeBlyh1DGru4Hw8JuO5wMBLqWDgjQ4G3uQw8BKljkHNHZyPx2Q8Fxh4KRUMvNHBwJscBl6i1DGoucOcj/Xq1dO6xkvGaxMDL6WCgTc6GHiTw8BLlDozqFF6zPkY53ma8Tdn4KVUMPBGBwNvchh4iVJnBjVKjzkf4zxPM/7mDLyUCgbe6GDgTQ4Dr13//v1t7//66y8xdepUW1mmXnvtNdt7c5y6b7/91izKVk7DOXz4sFi8eLFZTGkygxqlR83HMDRey3gMDLyUCgbe6GDgTQ4Dr505L37++WfRvn17W1kmPvvsM7F8+XLrfffu3cVNN90k9u7dq/V1zL/+9S+zKFt16tQxi2zKlSsnjhw5YhZTGvwKQVFnzsegzlM/pivjMTDwUioYeKODgTc5DLx25rxwO/CWLFnS9h6/UUuXLhUdO3a0lSupBN5EVqxYISZNmmQWUxrMoEbpMedjUOepH9OV8RgYeCkVDLzRwcCbHAZeO3Ne6IE3b9684oUXXhDFixcXc+bMkWVXXHGFuPbaa8WTTz4pChQoIMtuuOEGUaxYMfHoo49aw4E33nhDnHzyybaysmXLyld9vM8884w455xzRIcOHUT+/Pmt8sKFC4sbb7xR3HXXXeIf//iHuPPOO8XVV18tbr75ZtldDQOvGA+mtUSJEmL+/PnWMMzvR+kxgxqlx5yPQZ2nfkxXxmNIJfDu27dPNG3aVPaPHcrBgwetbvfff7+47777tL6PUsPGv3C14NBceuml4o8//rD1u2rVKnHqqafK7m+99ZatG2zdulU0aNBAdq9bt658r6jvoTevv/669mn7AjH7ffDBB2U56nGZ3VSjjjDow4E1a9aI008/XZa/8sorYufOnbbuZv/ZlZkwP/Xxn3LKKeLXX3+1uqMM8yw7mA6n8WBePfDAA7ayhQsXivLly9vKnKjAu2nTJrMThQwDb3IYeO3MeaEHXoTP9evX27qjf+zr0TzyyCNi2bJlMvD+9NNPtv5Uv926dbPe33PPPeK7776T7aeddpoVTPVpaNWqldWulzu1m68wb9480bVrV+u9+f0oPZiPnJeZC8t89GMaMx5DsoH30KFDsr+5c+eKbdu2yZ2E/rlkAi/+5eOzaCZOnCi7bd68WXb/6quvRJ48ecSGDRtkd+zo8uXLZw3n5Zdflv3jlBO6r1u3Tr4fPXq07I7v8eGHH1rD37JlizzKgICu6NOLdtUvGhwVKFSokOyml+v9qTpk+nAuu+wy+R47efTTokUL+R7fR8H7448/3nqvyhLB/EQwVeNX33nBggWyO9pzCrxVq1YV11xzjfj6669t5WqZ42ITJdXAe8EFF8jh7Nq1y+xFKl26tDyao47OZAp17ypWrGgWSzhKhB/dRJKdFny/b775xnqv1oOoOOGEE+QrA29yGHjtzHnx/fffW4EXByHUn/+ePXuKPXv2yPbVq1dbzYEDB2TgdYJ+e/ToYXuPI7mqUUeI9WkYPHiw1a6XO7Wbr8DA6w3MR87LzIVlPvoxjRmPIdnAix2V2d9ZZ50lhg4dKtuTCby48EDXr18/0aZNG9leo0YNMW3aNFt3nB7bv3+/bDfHDSoYA77HmDFjbN1xBNppp2e2Z1Lm1B07dL0cRz2wo9a/n9PnTJif7dq1s5XhhwLhHDCMnAIvuuMHCPNGh/fvvfeenL9KqoEXcHHHVVddJY477jixdu1aqx/1xwG2b99u++OSLpx2RGDVLyiZMWOG/EOgB15chd27d2/x4osvyvetW7e2jgo99NBD8vXee++VfxrwimVlwvfTp7lIkSK25dWrVy/5WVXX791335V/hlD2+++/W/3hDAPKVq5caZVNmTJFThOofjHt6E//A9K5c2fbkS43qeXMwJscBl47nGXT76KA7X337t3yTz+qEChO4RR/wvHHPbvAW716dXlgRDnjjDO0rkd/EwDDVAcgcKGZkt2+WbWbr8DA6w3MRzfnJfaRTo3q5kSVowqM+Tn9M06fx+819sNgfs78PM6m4vcFZV988YVV7ga356NX/JjGjMeQbOBF0MAR2IYNGzreBibVwDt9+nTZTZ3+RyjBe+x4fvvtN6s/wC1vzCOkJjPwYueLnesdd9xhlTntABVUFTDLIKcy7NxV4DYhoKn5pOqY5TR+J06BF0etP/roI9mOYWQXeN9//31x5ZVXynb0pwdFzCuExQsvvFAeoYZUAy+GrzcoQ4NTlggIOvyxeeedd7J8JpkG8Ioj5jgV2rx5c1k2fvx4a4eDi1xU4FXzFfOtSpUqtjK9LuCSJUts3XQoQ9UaBUdEVX94VVV5MHysvy1bthS33nqrLFN/LnBmQVX7UMsfwQDbCWBbmj17tjxDgepBgCNjqDZUsGBBeUYF7eedd57s5qZKlSrJVwbe5DDwZoVQinUY297nn39ulWN/i3l14oknWtsJwnDlypXln0j1Jy67wIv9lJrX2NfhjJ7uiSeekNs9qp6hihe2N/XnFvTl5NRuvoIZeBs3bmy1U2Jm1UH8fmP+qsYtGBYOsI0YMcLWqG5mVUIcEFMHX84//3z52+H0WVDrrG7QoEGiWrVqsl31j3rfOGChf/7ZZ5+VdcfxJxBl+E3V65Vnyu356BU/pjHjMSQbeBX8e8E/arUQVJBKJvBiJUAQRIOdH7phZ6jr1KmT3NGhm7p4YcCAAfKff07wPXAkDsPGUQB83rzaVv+eavpVg2lzOj3vNG9UGUI4dsBOsIPH7XVArfyoa4Yj2eA0XJNZhxeNPh/wPrvAi26o1gGPP/64LcyqwKv6w1HYVAOvTtUVxuex85s5c6atO8Zv7oxSgZ2JOh2qxn3JJZdY3RGIVeBVoRY7XVVHXM1zp4tfzO+iyhCu//vf/8o/Yuq0rLJx40Z5QQ7WNxxBR+BVEFoVVNcZOXKk9Vn9iPoPP/wgAy/+lOEsh2q6dOki64rjMy+99JL8YccpY4RTzF+sc9j+8F3KlCkjj66j+kipUqVk+MD6j+0HFwSpbQLzDzt+NAjTCCpYJ9U65QWn4WJ+Yv1RcHT9+uuvl/3ijyNCvqKmzWyy616rVi1rfXebGXixTNCQNxAg1Jk9v6l9BSVPBV6cocJ2Ur9+ffne3GYzhWHhIICTL7/8Uu4DdehfHdhA4MX+NDvoF/tEvSqbHngVPNbXvL7I6TuizOnsYTrcno9e8WMaMx5DqoFXh39MjRo1ku2or2VWWUAwUP+wzCO8gFO9OY0b3XA7Ghyt1cOCTv27N4/w4kcfV+nq9HHlNF6dU3+q7Pnnn7c2bhMCvbqXpP5vD59FSHUarsnpCK9ODcuEI4tqI9EbRQ+8CHbolk7gxZ8dBC4cDdV/oPRlhSM0CFnpQgjCEUl8JzTXXXednFa8KqjfrQIvjvpApoEX8N3M07JqnuNPAv7pZxd4ETQxbxGWVZ1ZBE0FQRiBN6fnomM8+IzTH7FMqD9NXh7hdRquHnhRpQb94LQhlivOhpjLBWdd1HJXjd5dL581a5bjON1gBl5s1/p9Ysl92H/7Dfua7A5ghAmOrOMAA35/sf/FwzSwr8GZUgRDnCHE9ocDSQirmTY4u4U/2Niv4KJtVY5txs1tEsPKLvCCOS79fTKBF8PWP5Ns4MWZUoRtzG8vuD0fveLHNGY8hmQDL05hmQESARMLG/DvzqyriRCMIy/gFHjVP0LAK47g6TBt6kpedDePBuOImLqQyQy8gM/oT87Rv2cy3xmc+jOH8+eff2pdj1XPUPTAi4CU7AqcbuDFMsGRQh1CqH6Bnwq8ULNmTVlXLpXAixCHnUh2/2JvueUWecpf1dFOF04vmqc18Sdqx44d8mimOoLqReDFfFFVClQZXvGDgWoaCPIIW06BF0EZO32cKlXbBf4gYp7g4kp8B/wIoe4zjtTibAB+NPBjhZ0qfnjx44Gw7/bRRFVdIzcDr9M2gAsTP/jgA6u7XqfZZH4WcErSqbpVphh44wdnHHAmBUEG+0tsz2qddbvBvgDjwf4X6zD2O7g+BvseVCHEHY1wazVUA7n99tvltOHPNqqPYT+PB3PgqDgCHU6rI5ANHDhQbm/Dhw8Xn3zyiax2gmphuFgcRzFx5wtczIyL0DNtcA3FmWeeKc80IVSrcvX93GLON3P4mH/qeg3so9XBOMBvlfk5/bOqHWeY1QGKZAMv4GzySSedZA1XVXFzgzmtQeXHNGY8hmQDL6iNHhueqteoH9nDj7Pqjg1YHy4CLz6DbmiwIqG7usIWP/x4j9Oy6I52BBoFp4dRhlO6qrsesJ0CL1Z6fRqya8+JU396GY42mtOFcKkHQbM+Dyq3Ow3XlEzgRT1dNU9VvTinYePuF6rcDLyAI4mpBF5KHS5YU/r06ZNroUndkzQ3Ay/qYGOdw485gr8Jn08l8GIYZplbVOBFcEDzn//8RzbqvZsNAj/quyO44OwVLrZBlSD8EOPPI/YJCD3Y1rHt4yAE/uBivuK2XdivYrliP4o/ZJhuNxt9HSYC/LFX1IGTVA7sJAvDyukIL86EqfGZ403mCK/ejuCcSuA14SDG22+/bRanxe356BU/pjHjMaQSeIkYeNOHP3wIIf/85z+znA3JDbkZeBUcecIfW7VTV9cEoB11j81G0bujHXWhvcIjvKnBGRmn5Y8jmU2aNDGLKeT0wKvo27RbMKycAi/gTzT2Icg1ulQCL84k4z3+WCYTePX9loKL63A3Eze4PR+94sc0ZjwGBl5KBQNvdHgZeHGEA2cVdP/+97+zVGvS4W4V6jQkpivZI7zqHuGoL+0FBt7UIPDiD8i4ceNs5Qy88eJ2UMOw+vbtK289qTc6VK/Aujd27FhbOQIvzoqYn8UZWjCnU104nEzgxRlbBO27775bDhMXVDuF4HS5PR+94sc0ZjwGBt7chTpbTo0Xt6NyAwNvdHgZePHkQrPOP6pEqcfNYrx45KwOdQz1K7yTDbyAagDZXdiaKQbe1CDwtm3b1nbh2bBhw8THH39sBV5U3UB3nPHAhVSAefzqq6/Kuva4y40KDKjqgSpyWH/QDviTg7r5qDeKOvEKrmnAeo3+1e0tsazQHxqnp7uRN9wOajhC69SYnMpwxNX8HBrcAQecPvPpp59mqZYwZMgQeYcdE+4JjQsBMZxRo0aZnTPi9nz0ih/TmPEYGHgpFQy80eFl4FV3IsEFnajnjzCL9+oCPFzAh/eoZ4/uqv4dLqoBtOOqZ3TTG3VvV6fpRpkXj7w2Ay/qJ+qPNSc7FXgxz1Roveiii2S9SBV41fzUry3Aq7rfOi7Matasma1fVS8UateuLTp06GCrt6n6RX+4i4o+XLxHAM7kjjGUGsx3p+2UUhOW+ejHNGY8BgZeSgUDb3R4GXgBF5rWrVtXjgMP4tDvswuoK4cL6NAdV6Xrd2lRO3mzUXfEcJpudSGc28zASzlTgRd/atQdQRA09cCr4Ciamrf6PNbv4KOgvrdTv7iAUME6jXvCo1EPWEG/uNsB7uxC/lHbLGXGnI/Ylty+c48b/FjWGY+BgZdSwcAbHV4H3qhg4E2NCryA+YYjrqhTaR7hxa39UMXAKcSat6zEHStwi0mnftWt7HB0H486d4Jx497dXI7+MYMapcecj7jrk1v1g93kx7LOeAwMvJQKBt7oYOBNDgNvavTA26JFC3l/aVCBF3VqVf1u/Z7lToEXR/1VvW48NUv1g/q/6h7r+ufQro7k6sNVV/dzOfrHDGqUHnM+enWtQqb8WNYZj4GBl1LBwBt+avkx8CaHgTc1euBVjx0H/Qjv008/LY9UIdjiYSygz2P9CC8uBMKPPJ64iQccKHgsNS5cw90/dLiSXtUFVvAUMLOMvGUGNUqPmo+ZNl7zZRxmQaoYeCkVDLzhp5YfA29yGHiDB8tD3fYuqEe84s6voBV15nxMZ57iHuheS2e6UpXxGBh4KRUMvOHHwJsaBt5gwgMP8EhdCiYzqFF6zPmYzjxl4P0/DLyUijgHXtQbxOnXsDdYfnjFkbG4LstUMPASpc4MapQecz62atVK65ocBt7/owIvGzapNHHUvn17syiU1PLjEd7kMPASpS7OvxVucmM+MvBqzDDDhk1OTVwx8MYTAy9R6uL+e+EWN+YjAy8l5McCpPCISuDFc+KBgTc5DLxEqXMjqJE785GBlxLyYwFSeEQl8CoMvMlh4CVKnRtBjdyZjwy85EitXE4NxRsDbzwx8BKlzvz9ZJNZkwkGXkrIjwVI4cHAG08MvETpMUMbm/SaTDHwUkJ+LEAKDwbeeGLgJQqODz74wCzKdaNHjxZdu3aV7Vu3bhU333yzbO/evbv49NNP9V5zBQMvJeTHAqTwYOCNJwZeouAIYuAF7COWLl1qC7xB2W8w8FJCfixACo+oBt577rmHTQ7N9ddfz30BUS758ssvbdtjw4YNrfZdu3aZveeayZMny/2ECry9evUS48aNM3vLFQy8lJAfC5DCI2qBF7COs0ncbNiwwZx1RJQLgnqEF2644QYxZcoUGXix3wgKBl5KyI8FSOERxcAbRG5td6iK8NJLL5nFRBRiQQ68gP1XmTJlxJw5c8xOuYaBlxLyYwFSeDDw+sOt7Y6Blyh6gh54UdXCrX2YWxh4KSE/FiCFBwOvdz7//HPRtm1b2WC7U+1oUqU+d9ttt4m///3v1vvOnTubvRJRyAQ98KIOb9OmTc3iXMXASwn5sQApPBh4/eHWdscjvETRE4bAq+7SEBQMvJSQHwuQwoOB1x9ubXcMvETRw8CbOgZeSsiPBUjhwcDrD7e2OwZeouhh4E0dAy8l5McCpPBg4PWHW9vdq6++Km666SazmIhCjIE3dQy8lJAfC5DCg4HXH25sdxgGHvc5c+ZMUaBAAS47oohg4E0dAy8ltGTJErOIYoyhyR+Z7jh79OghBg8ebL3fuHFjxsMkomBg4E0dAy8RpYSB1x+Z7jjLlStnFomzzz7bLCKiEGLgTR0Db0wdOHBArF271iy2zJ8/X0ybNk1MmjTJ7EQxx8Drj0x3nJdffrlYvny5rSzTYRJRMDDwpo6BN6ZwelM/3WnCIwGJnDDw+sONHSeG8dprr4mRI0fK9ueff97shYhCiIE3dQy8MXL48GHRpEkTkSdPHjFx4kQr8N5+++1yIdWpU0e+RzuaGTNmWAsPp0Lvu+8++f7666+XZfv37xelS5cWBQsWFEuXLpVlXbt2lcOvXLmyHAdFDwOvP9zacU6YMEF0797dLCaiEGPgTR0Db4wUK1ZM9OrVS7YPHDhQBt7p06eLjh07yjIc9X366afF5s2bRcOGDWWZHnhXr14t2/Pnz2/rBhi2/rpr1y7xzjvvWN0pOhh4/eHWjpP34SWKHgbe1DHwxggWxIoVK2T7tm3bZOBt27atdUQXzYknnpht4FUKFSpkddMbwCnTvHnzyqO+Y8eOtT5D0cHA6w+3dpwMvETRw8CbOgbeGMGC+OSTT2T7unXrZODFUdhhw4ZZ/bRp0yalwKuce+658vWss86Sr6g+4ceCJ/8x8PrDre2HgZcoehh4U8fAGyP79u2TR3Br1KghTj75ZKsOb6VKlWQZFhTu3pBs4F24cKHIly+fKF++vDxSDBdffLGoUqWKrPbQsmVL6zMUHQy8/nBrx8nASxQ9DLypY+AlopQw8PrDrR0nAy9R9DDwpo6Bl4hSwsDrD7d2nAy8RNHDwJs6Bl5KyI8FSOHBwOsPt7Y7Bl6i6Al64N25c6d44oknzOJcxcBLCfmxACk8fvnlF7OIPODWdsfASxQ9QQ+8QcTASwn5sQCJyM6t7Y6Blyh6GHhTx8BLCfmxAInIzq3tLmyBN5XvnUq/RFHideBNZttq1qyZWeSoU6dO1tNYlSuuuML2PjvNmzc3i9LGwEsJ+bEAKTh69uxpFmWB+zdv2bLFLHZ15xR3bm13DLxE0eN14E2GH4G3YsWKZlHaGHgpIT8WIAUHAi8eUPLNN99YZXgy3/vvvy/WrFkj3+uBF/duRrdDhw5Zgff777+XZXv27LGGQalxa7sLa+DFK9ahWrVqialTp8qH2eApjnhQTsmSJW39Nm7cWMyePVu24z7gw4cPF3ny5Dk6QKII8jrwqm3r3//+t+jSpYvo0aOHvH+/DoEX9+H/8MMPrf779Okj79U/YsQIeZ/+I0eOWIF38eLFok6dOmLAgAGiVKlStmEBnhOA8Tz77LOiSJEisqx06dJyWG5g4KWE/FiAFBwqKDRt2lTMnTtXbNiwQYYIuOCCC8SMGTOswIsQUrhwYdntzDPPlIEXDy554YUXZBl2eJQet7a7MAbeUaNGiaFDh9rKnH7gUY4QrHcrVqyYWL9+vdYXUfQ4bQ9uUvufu+66S7Rq1Urs2LHD6MN+hPf000+Xr/jcH3/8IQ+SYN/zyCOPWIFX36fldHQYd3hQ/fIIb1bejyHG/FiAFBz4R698/fXXcmenw2OkVeBFMJk2bZrVDYEXR3URdO+8807tU5Qqt7a7MAbe9957T4wePdpW9swzz2h9HSv/66+/bPNq//79cv1U3YiiyK/AC/gDefnll4sCBQpofWQfeHEnH9WsXLnSMfAiCOuw3eJo7mWXXSZmzpzJwJsD78cQY34sQAoOvQ4vAm+bNm20rkeP8qrA+9VXX4kxY8ZY3fQ6vEuWLJE7MEqPW9tdGAMvlC1bVr6iesKDDz4oNm3aJKpXry7LUP9v9+7dVr8LFiyQf8QQcNWP8NVXXy1+/fVX2U7hhipW1apVk+0lSpSwd0zR5MmT5TYRdn4FXmxzqvqauU9yCrwIqLfffrtsx0GP33//3Qq8b7/9tnj99ddlN3NYEyZMsMqwfBh4s+f9GGLMjwVIwWEG3l27donixYuLhQsXyqoNy5cvt9XhRRUIBA7U5ULgRfnZZ58t+zePCFDy3NruwhZ4b731VvmKMwVo14/0Yt1CGY4a6f2qdhwlQt1ztGOdpHDCU7o+/vhjMW/ePPneKfDimgH0g+sFlL1798qydevWWWXYD6Fs1apV8n2HDh1Ev379rO4jR46UdUuVn376SfaPzwWZ14FX37a6du3qeEGyvl/p2LGj1Y59Dj6v6tWjLv7atWtlO+rj3nfffWLw4MFW/wrmPT6Hea/Gj98bfVoywcBLCfmxAInIzq3tLmyBl+INYbdq1aqyHafRp0+f7hh41fUBCK8IZLg4SnWrXbu2rHP6xhtviCFDhsgy/DHHNQe4wEod4VXXKzz33HPizTffFAcPHhRPPvmkLMNRyXHjxsn2IPI68EYRAy8l5McCJCI7t7Y7Bl4CrE9haHQIvLh40Qy8c+bMkVVdFHzu1VdfFRs3brTKdCtWrJBX/e/bt88KvDhL0Lp1a9G/f3/ZFCxYUPaLVwRmXDgF5vQFpQl64EWVI/yJCBIGXkrIjwVI4fHUU0+ZReQBt7Y7Bl4Ct9Ynr02cOFHeIWb+/Pnis88+cwy8qK6C+qAKvhtudfXbb79ZZbNmzRL16tWTt8nCaXHcDksPvKtXrxbffvut1b8OR4I7d+4s645Tev7888/AXbjMwEsJ+bEAKTzat29vFpEH3Nru1AUgbLxtgi4M0wiqigJCLa4BeOutt7IEXsD3QV3Pe+65xzqSiPu//vzzz/JaA4Rb9ItqCQi2qAKBeuEI0ajCoIbxww8/yOoLCLi4pWL9+vXlNoO71bz44ouyP0odbmd57733msW5ioGXEvJjAVJ4MPD6g9tdeIRhWYVhGik6cJGaeUvL3MbASwn5sQApPBh4/cHtLjzCsKzCMI0UHagyErQqIQy8lJAfC5DCg4HXH9zuwiMMyyoM00jRgQsF27VrZxbnKgZeyhEeKoAbuvft29fsRDHFwOsPP3ac5I4wLKswTCNFx7Jly2Td6CBh4KVslSlTRl4sgPsZ4upXPxYkBR8Drz+4vYVHGJZVGKaRogNPVnvsscfM4lzFwEuO8BSbli1b2sqmTZsmBg0aZCuj+GHg9YcfO05yRxiWVRimkaIDj5bv3r27WZyrGHjJ0YEDB+R9DXW4UXfbtm1tZRQ/DLz+8GPHSe4Iw7IKwzRSdCxatMj2mPogYOClbJkLrnTp0vKG3BRvDLz+MLc/Cq4wLKswTCNFBx4c8vzzz5vFuYqBl7KFZ5pj4alm8eLFZi8UQwy8/vBjx0nuCMOyCsM0UnTMnTs3cBe7M/BSQliAa9asMYspphh4/eHHjpPcEYZlFYZppOjAo51fe+01szhXMfBSjvAsbHWElwgYeP3BbS48wrCswjCNFB0zZsywHvkcFAy8lCMVduvVqycfFUjEwOsPP3ac5I4wLKswTCNFB+7qNHDgQLM4VzHwUraaNGkiFi5caC3AkiVLGn1QHDHw+sOPHSe5IwzLKgzTSNExefJkXwJmKvyYHj+2M+/HEDNHjhyxFpx6veKKK8Rff/2l90YxxMDrDz92nOSOMCyrMEwjRcfXX38thg8fbhbnKgZecjRnzhyrwrlagHg2dv369fXeKIYYeP3hx46T3BGGZRWGaaToGD9+vPj444/N4lwVm8CLiWDDxu8mihh4/RHV9SeKwrCswjCNFB1jx44Vo0aNMotzVewC77333suGjedNpUqVfFnxcwMDrz+iuv5EURiWVRimkaJj9OjRMvQGSewCL5EfUN85qusbA68/orr+RFEYllUYppGiY+TIkbIeb5Aw8BJ5gIGXMhXV9SeKwrCswjCNFB2ovzt16lSzOFcx8BJ5gIGXMhXV9SeKwrCswjCNFB0ffvih+O6778ziXMXAS+QBBl7KVFTXnyjZuHGjXE7XXHONqFy5snjsscfMXnLdjh075DQ2btxY1KxZU9xwww1mL0SuGzp0qLzbU5Aw8BJ5gIGXMhXV9SdKzGV03HHHiS1bttjKcps5jbfddpv4+eefbWVEbnv//ffFggULzOJcxcBL5AEGXspUVNefKDGX0Z49e8Tnn39uK8tt5jQeOHBAXHvttbYyIrcNGjRILF682CzOVQy8RB5g4CWKPnMbP//888X69ettZbnNnMbHH39czJ4921ZG5LZ33nlH/PLLL2ZxrmLgJfIAAy9R9OGULbbzIUOGiL///e/i3HPPNXvJdatXr5bT+Prrr8v6u9WrVzd7IXLdG2+8IZ/OGiQMvEQeYOAlN0R1HYqaOnXqmEWBc+ONN5pFRJ7BH6w1a9aYxbmKgZfIAwy85IaorkNRg+XUr18/szhQMI133XWXWUzkif79+8u7mAQJAy+RBxh4yckdd9whb1+FdePuu+8WVapUsdYT3D4qT548olq1aqJAgQKyTHV74YUXRPfu3WX7qaeeKooVKyby588vlixZYvWHz0V1nQuyzp07y/leokQJs1Ng4IlX/A0kr916663WeqaavHnzisKFC5u95goGXiIPMPCSk/POO0++NmvWzLpw6KWXXhKrVq2SYVjBxU+AdQhX/T/88MPyPW55hScYKWodC2Ld0bhQvy1XXnml2L17t9k5ENQ0Pvnkk4G7iwRF04svvij/xAcJA28CTp/BvRZnzpwp23EbGhyVUcNHM2nSJKtfvVw1FStWlN2OP/74LN3QtGzZ0vp8drBjrVChgu1zEyZMsLrjvQllTZs2tdrNRh0tgh49eti64YjTvn37rO5QpkwZWz8LFy60upnDRlOwYEGr+8033yyvFoaLLrooS79odu7cKZ/WYparRo1Ht3fvXpEvXz6rHxwF27Rpk9Udy6p8+fLaJ47Sh4MfLn08LVq00PpMjgq8VatWFYcPHzY7hxoDb/patWolXxF4Vf02FXjXrVsn102sNyVLlpTd0N61a1dRr149+b5bt26O28G4cePkul28eHH5nvyBB03g8alYDocOHcqyPwoCBFxMp5q2IE4jRc9zzz2XJTPkNgbeBJw+owdedN++fbutu/4Zp88rCLwjRoywlSW708SPm35ECPdWTDRelOmBd+XKlVY3rJjqM07TMGXKFBkkFXSfPHmy9X7//v0Jx4+A3LNnT9luBt4333xT71Ve9YywqitbtqwtlIM+HiwHvN+wYYNVhtCMMgRhwHzD9/jss8+sfkAN5/fffxelS5fO0k19Plkq8GK+1K5dW7aPHz/e1s+8efNkeadOneTp6EceecTWPagYeNOXU+DV1+Vy5crJV1V2wQUXiLVr18ojvE899ZTVH4IxhtOmTRv5ftq0aeLll1+2upO31PJRr/Xr1xfLli3Te8l15jQ+/fTTYtSoUXovRK579tlnA3ewh4E3AafPmIE3pyfrOH1ecQq8kNNnFDPwmpyGgbLsAu+RI0eszxw8eFC2Z7eyIugWKVLELLZxGj9Ou6qwlCjwgjmMRIEXV0r37t1b63rUQw89JBo0aCDbMd/+/PNP+blZs2ZZ/ajh/PDDD3L5ZsqpSgO+O8rU88X1PxCAkBPUU6I6Bt705RR48acS6wfWgy5duohdu3bZ1iHVfvvtt4uiRYvKenHLly+XZagqge4nn3yy1T85w3xi414Td+b8YJNZ4yUG3gScPqMHXgQU9KNOJ5pX6qIbfpz0BrfrAATeQoUK2bphOCqc5UQd0UWDqgKoL6Nzmm6U6YEXoVWNF+/1G6bjKSkoQ4Vz9KffQLpGjRrimWeesd47Mb83phFlCNaQU+DFUSr0ixtX6xIFXqfvrKhuKvDiKEd2n8Uz5/EeR5jTvZWPCrzZNZiOU045xfYZBCCzvyA2DLwUZub6zCazJu7M+cEms8ZLDLwJOH1GD7w61OVq0qSJ7TNo/+mnn2zNX3/9Jbsh8CIgo2zRokXyiB9O5acKz0VHkMW41FFZp+lGmR54caRWTRNCuNNncJRpxowZolSpUlb9wEaNGsnT8DnRvzfqwCIk68zAizqKOOqF5oEHHsgSbMHNwAuop4xloHfXoWoEgj26/fjjj2bnHDkd4cUFIyhDfUswq2zg6n3MbyLyjrldUnowHzkvj86HnM7yUnL8WJ8YeBPAZ8xT+7iAC/eX27x5szxCa7rmmmvE22+/LdtzGqdTlQb0r19k5QR1bNVti3RXXXWVGDNmjGx3Gi/KEPJUu16lAVB3FUdXEX5bt25t6wZqmOqotgkX0akVyuyOq85Rh1cxA69TlQZTosB72223yXlvQhlOA4MeeAFHr1GfVw3nsssus1V1AAR+fdqToQIvjsSr081mvWH8aUJ5r1695NHee++919ad4s3chsgdnK/uwHzkvDw6Hxh4M+fH+sTAm0ClSpXkEU0FRyz14aB95MiR1nszDOY0TqfA+8knn8hQlgj6wR0AFNwtAuPCRVKAo9D63R5wwRQ+o8I0+tUDr6oigYvXcAQa7XgkpYJ+9e+CKgodO3a03qMKhD7dTt8bZZh/4EXgVe/1CzLUFdSKGXhBXzfwhwHt+oWImM/qHqjJUoEX9THNP0xEyTDXbXIH56s79P1mnGEeMPBmzo/1iYE3CTj6pj6PwISLuhSEGRzlVd3R4MInRS/XG3AKvIDu9913n1lsg6O8OKKpD1MPg6gri4CouuH0uao/C+b0oMHRXUWFXr1RYVpRN81Hg3mgBzuUmTB9qtyrwIvviOoXarpwFbs+XU6BFzf114ej36QdTaphF5yqNBClguuPNzhf3aH2j3GHecDAmzk/1icGXiIPMPBSprj+eIPz1R38TT2KgdcdfqxPDLwBhnrATg0FHwMvZYrrjzc4X90Rxt9ULzDwusOP9YmBl8gDDLyUKa4/3uB8dQd/U49i4HWHH+sTAy+RBxh4KVNcf7zB+eoO/qYexcDrDj/WJwZeIg8w8FKmuP54w4/5+tZbb8k72eCiWfMBOuq3SG/Mpy7i3uoo15+8aH5GNeqOMp9//rkoX768LMP+x7zI2G1q/OqJgbrvv//eLPLE3LlzzSIbr5b1woULrXaMw4vAi4c+mRdpAy7KxlMWwVwX0OD2pKob1kOd/kRVfAen+aPKcEcnc9iq8YKXw1YYeIk8wMBLmeL64w2v5yseooPHnCunnXaabZzJjB/9NG/eXFSvXt3sJB8YVLNmTVsZbhGJIKTgkdMYBm436RX1m4ppweu2bdusbt26ddP6TAxBDI/X3rlzp1WGwLV27Vrr/Y4dO6z+1B+BYcOGyfeAu/GgHQ8MUlQ3DAd3HtJvtYk/BPqwUqECJ+C7exF4v/zyS3lvfBPGt3XrVqs9O06ZJ53A6xen6XUbAy+RBxh4KVNcf7zh9Xx1Gj6O4KrbITp11+G2l+hHvZqcAi/u920+DbJ27drWUx29oP+mIlife+658og2AmSqgRdHM/EwJ9zz/tdff5W3vJwwYYK8/7t6yBKeSlqxYkUZxNQDn3Dfev3e8mjHg3zwhExVpoaP24XOnz9fXHjhhbIMfxDQf61ateT7VPgReMFc/k888YS45ZZbrPdmdx264RkB+hM9GXgZeIlcx8BLmeL64w2v52vv3r3lOPCI9HXr1pmdE46/bdu21qPbL7/88iz3AXcKvHgaJIaLe7O/9957tm5eUb+pmF7VtGnTxrE8pwbfZ+jQobZh608wxb4UEHhV9Qn1UCXcM900cOBAeZ93UPNan+eqHfdk79y5s/xjgfvam9OVU4M/MKodw/Mq8J511lky1Ctm1Zec1iX9uw8YMEC2M/Ay8BK5joGXMsX1xxt+zdcuXbrII68YHx5hruA9qjnojf6gIX36EKTM6XUKvAoeotOgQQP5GQQ6BDmvOP2mquBdrVo1W3lO8BRQ/QFMCGLqqC5ceeWV8hWBV3EKvHgwkRpOMoEXcAQZ83LixIlWWTL8OsKLJ6gWL17ceu8UeM11Se8GKuSiCkc6gdccPqraeMFpfXIbAy+RBxh4KVNcf7zh9XxFXVETTtH3799ftuc0fpxyV79VeoOL2BSnwKvqdOp69uyZUvBMlf6biuoUaMcRXkinSgOqQmC/+ccff8jwOmfOHHlBHrqBU+BFUEU/qAbRuHFjOQxUVbjxxhtldzV9+jxX7UWLFpX9N2vWTD6CPhV+BV5Q04uwaR7Rzmld0ru9++678iJKPfAuW7bM8fOqjEd40+P1d4CEY/BjZhIpDLyUKa4/3vB6vjoNH3VThwwZItuduiuVK1cWw4cPt5XhSnv9FL9T4MUwzbsljB07VtStW9dW5ib1m4qjjma1i1QDLy44Qx1bPbgjkOl3KVB1dQFHZpUFCxbIIIcydfcElDm96u04eor2zZs3W92S5Wfgfe655+SfF6f1xqlMMbvhAjgsK1WOeW72o+4OAgy86fH6O0DCMfTt29eaoWzY+NFgnSNKF9Yhcp/X8xVX12McOKpbv3592W4GJJSbjermRC93CrwIe+gHF41hWAg3qNKA+qleUfu5uMM88DLwAoIqLkI0Oa1LDRs2tLqZcJRXL7/99tutYRx//PGyXd1tQwVec/hqXXWbH+tTbAIvpc+PBUhEdtzuvMH56g4/AkoY+BF448CP9YmBlxLyYwESkR23O29wvrrDj4ASBgy87vBjfWLgpYT8WIBEZMftzhucr+7wI6CEAQOvO/xYnxh4yRFu3K0aLED9PRF5z48dZxxxvrrDj4ASBgy87vBjfWLgpYT8WIBEZMftzhucr+7wI6CEAQOvO/xYnxh4KSE/FiAR2XG78wbnqzv8CChhwMDrDj/WJwZeSsiPBUhEdtzuvMH56g4/AkoYMPC6w4/1iYGXsrVz505rJUSzYsUKsxci8ogfO8440vdpbDJv4s6cH2wya7zEwEvZwoLD01gU/ZneROQtP3accTRgwIAsP7Js0mvo6JPbzPnCJr3Gawy85OjAgQPi1VdftZXhCG+7du1sZUTkDT92nBRMTo99JaLMMPCSIzySslWrVray6dOni3feecdWRkTe8GPHScHEwEvkPgZeyhaexz5+/HixZ88esW7dOl8WJBEdxe0tfsxTvKpp3ry52SsRpYiBl3I0dOhQUbduXT5wgshnfuw4KZh4hJfIfQy8lJAfC5CI7LjdxRcDL5H7GHgpIT8WIBHZcbuLLwZeIvcx8FJCfixAIrLjdhdPU6ZMseruVqhQwexMRGli4KWE/FiARGTH7S5+Jk+eLJo2bWq9xxO8ChQooPVBROli4KWE/FiARGTH7S5+GjVqZBaJvHnzmkVElAYGXkrIjwVIRHbc7uKncuXKZpHInz+/WUREaWDgpYT8WIBEZMftLn4+/PBD2wN/Dh06xPWAyCUMvJSQHwuQiOy43cVTv3795LJHg4f/HDlyxOyFiNLAwEsJ+bEAiciO21188bZkRO5j4KWE/FiARGTH7S6+GHiJ3MfASwn5sQCJyI7bXXwx8BK5j4GXEvJjARKRHbe7+GLgJXIfAy8l5McCJCI7bnfxxcBL5D4GXkrIjwVIRHbc7uKLgZfIfQy8lJAfC5CI7LjdxRcDL5H7GHiJiALIjx0nBRMDL5H7GHiJiALIjx0nEVFcMPASEQWQHztOIqK4YOCNkO7du5tFaWvYsKF8rVy5slV24YUXWu3ZWb16tfjggw9sZW3btrW9J6LE/NhxUmpeeukls8g1L7zwglmUkXHjxoldu3bZypYvX257TxQnDLwRomb0vHnzZPtNN91k9CHEtm3bRNmyZUXdunXFgQMHZJnqv0uXLvI92tEsXLjQagcVeLHTLFKkiLjjjjuODvT/GzFihMifP79YsmSJY+BdsGCByJMnj5g2bZosw+eVokWLWu1EdJQfO06Kroceekhs2LDBVsZ1iuKMgTdC1IxWrwimU6dO1foQMnTCkSNHxHnnnSfbzz77bPm6adMm8eSTT8r2nI7wquHv3LlTnHHGGbL9vvvus16dAm+PHj1ke/Xq1eXrcccdZ3VXwyCiY/zYcVJqSpUqJV/79+8vl0++fPnE9u3bbf1MnDhR7mfRvW/fvrJs8eLFsixv3rzWUdYCBQrIfk477TT5vnjx4vL1xx9/lOXo/+mnnxaHDh0SV111lWjRooUsxwELBeNH2ahRo+T7rVu3yuHis2bg7dChg+z3kksukQc71Gd79+5t9UMUZX4E3r1795pFruMvgzj2A4mdI3asV199tdHH0QWO/hB29+3bJ0+jnXDCCaJGjRqywecgu8C7aNEiUa5cOat/tVNetmyZ7OfPP/90DLzKzJkzxbBhw8TPP/8s+vTpI384VqxYcaxnIpIYeINHBV592SxdutRqhzJlyljt5kEImD9/vgyi33//vXw/adIk+aoCLwKrUqJECSvwYp8JxYoVk69qXw01a9aUrxjPqlWrZDv2z9kd4dWnp169eqJ58+bWe6Ko8iPw+oG/DOLYTgyBEtasWSN3mMrBgwfF4MGDZbu67c2YMWPEm2++afUzcuRI+Zpd4MXO9N5777XKPvroI7nDnjx5snyfXR1eVX0C1SZQvQGww1Y7eSKyY+ANHhV4586dK/etWEZqf6Zgn1qxYkW5f1PLEGfPKlSoIN+ro7E333yzfN+gQQP5Xu0LEUAVHCFWgVfRQ7fegL4/RTWzZALv66+/znWNYsHPwPvyyy+bRa7h1iqO7cRQXaBp06aicOHC4o8//rD1c+utt8pTaOeee6647rrrZBl2krfccovcQaujrThyu3LlStkfjugiIKsqDccff7xo3LixPBLx3XffybJChQrJ6gyom+sUeHHU4+6777Z21nDqqaeK66+/XuuTiBSGkOBR+y+EV8VcTuo9qo2pdlVtQXVH6F27dq1837lzZ/nqdIQX48su8KrqaaCqp2HY69evl+2XXnppUoEXARvhmyjq/Ay8XuIvQwg9/vjjWeq/EdFRZpCi3KfCJqpjIZjqBwmUSpUqyYMNaFR4nTVrlryoFw3OiCEM47M4QIADCqACL6p9oX5twYIFRbNmzeTBBqfAu2PHDrmO4GDDgw8+KMu2bNkix4Fxd+zYMUvgRXWIOnXqiN27d8vPYhyPPvqorR+iqEom8N5///3yDDe2QcA2im2lXbt2Vj/YxlGm/vjiDA76x7aHbQvQHePDGR9F7dNxsA/tVapUsbphW8Sf2Pbt21tl2eEvQ8hgp83qDETZY+CNJ/1HkHewIXJPsoH322+/le0IsHv27JHt1157rQy9X3zxhXjjjTdkWc+ePWU1TvSnmGdR1EWm+GOMP5dTpkwRo0ePlmW4E9Zbb70lLr/8crF//35Z9tVXX8nXnPCXwUP84SXyH7e7eMJ1EVj2OEqLdiJyR7KBV8F2aDatW7fW+nbuT5UB/sAiQKu6+vXr13fsH9WS0P7www8fHWgO+MvgIbVAiMg/3O7iS11UTETuSTXwotoR6tADjs7imiNco/Tpp5/Ksrffflve+hXVihR1lxa1/arnGaijwIMGDRL/+9//ZDtuLHDXXXfJa6gUfVjZ4Z7BQ9zxEvmP2118MfASuS/VwAvYDlH9slatWlb4Rb3ekiVLyruxwIwZM2SgRZ398ePHW59TcNtA/WwNqjngLi+qnjDu3Yv6uyhTR4Jzwj2Dh7jjJfIft7v4YuAlcl8ygTcMuGfwEHe8RP7jdhdfDLxE7mPgpYS44yXyH7e7+GLgJXKfH4EX1R28xj2Dh7jjJfIft7t4euihh+SyR4P75uKevUSUOT8Crx/7be/HEGN+LEAisuN2Fz+4J2e3bt2s9zzSS+QeBl5KyI8FSER23O7ip3z58maR7ab2RJQ+Bl5KyI8FSER23O7ip3HjxmaRvBcoEWWOgZcS8mMBEpEdt7t4wr05Z82aJbZv3y4aNmwounbtavZCRGlg4KWE/FiARGTH7S6+XnvtNfnEJjyJiYjcwcBLCfmxAInIjttdfPFiNSL3MfBSQn4sQCKy43YXXwy8RO5j4KVs4XQaFp5qxo4da/ZCRB7xY8dJwcTAS+Q+Bl7KlrngTjrpJLF7925bGRF5w9z+KPouvfRS2TRq1Eguf/W+d+/eZq9ElCIGXnK0f/9+MWjQIFvZunXrRMuWLW1lROQNP3acFEw8wkvkPgZecnTgwAHx4osv2sp+++030aVLF1sZEXnDjx1nHD377LOBb3r27CmXv1kexIYoLBh4KVu44fmePXus90WLFtW6EpGX/NhxxpG6JoGNOw1RWDDwUrbUaTXV4KgvEfnDjx1nHHG+uoOBl8KGgZcSwgL8/fffzWIi8pAfO8444nx1BwMvhQ0DL+WoadOm3LER5QJuc97gfHUHfxcobBh4KUeFCxeWC/Cyyy4TS5cuNTsTkUf82HHGEeerOxh4KWwYeClb5513nvjjjz+sBZgvXz6jDyLyih87zjjifHUHAy+FDQMvOTpy5Ii14NTrLbfcIlavXq33RkQe8WPHGUecr+5g4KWwYeD10FtvvRXa5txzzxXPPPOMbMcCVOXFixfP0m9YGqIw8WPHGUecr+5g4KWwYeD1kNohsAlGQxQmXGe9wfnqDu5XKWwYeD3EHUJwcDlQ2HCdzUz//v3NIsmt+Wr+odb39wMGDBCnn366rf8nnnjCugi4XLly4tChQ1Y3c5qGDBkiy1asWGF1N5uHH35Y/PTTT1nK9ekA9FegQAFZVr58eas8U2o8U6dONTuJ559/3iwiynUMvB4ydzyUe7gcKGyCtM62bNnSLMpWhw4dzCJHqDLlJX3+7du3T5xyyimiZs2ars9XfN9bb73VVmYG3jJlyoi6deta72fMmGGbDr39nXfeke+///57x+7Zceqne/fu4owzzrDef/fdd479pUP9vvXp00e+fvbZZ1a3bt26aX2Sk7Fjx4r33ntP/O9//5Pzb+7cuWYv5DIGXg+pHQLlPi4HCpuwrrMVK1Y0ixzhLjBewvzbvn27OPHEE8Vpp50mnxypyt2UKPBeccUV8jHtph49eoht27bJdjVNCLs4CmxKZpqd+qlevboMVbpWrVrZ3qfL/H1DuMZ7BDkG3qzUejBr1iz5Xs0/1eTJk0eW4xagBQsWFD///LN8j/W3SZMmcnuZM2eOPFpfsmRJsWTJEmvYlBwGXg+ZOwTKPVwOFDZBWmdPPfVU67VTp07i4osvtnWvXbu2PGUPKvDix2X27NmyHUcB1R1e0N9VV11lC7yvvPKKHPYXX3xhlbVp00YO9+DBg1ZZKjD/8ufPLx577LEs5W5KFHhxoW+FChVs3U1qmvC6ZcsWo2ty0+zUz5dffilvJzl58mSzU8acft+wjFGGQEbHPPLII+LRRx8V69evt+YZ/hRs2rRJbNy4UZah/Z///Kf847Bu3TqrPwTecePGyXmLZblhwwaxZs0axz9RlDMGXg857RAod3A5UNj4sc5iHG+++WaOzcqVK22B7MCBA/IH96STTpJlCJUwZcoU8e6771qBFyH2m2++ke3/+te/xPLly8UDDzxghWD1g33//feL8ePHy3b8II0ePVrWO127dq0sQ1icPn16lulK1Kj9780335yl3E2JAi/GhyOtOUE/OMKHur1du3Y1O1vfRW9MTmWwbNkycdFFF1mfe+qpp8xe0qKGp8/bN954w7E87o2+bJ599llZtaRnz562ealeUTUETYMGDcSqVatk4FWKFSsmbrzxRjFmzBj5/quvvsoyLjY5N17Lbjt0k/djSEN2OybyH5cDhY0f62yy49B/kBUVbBHudDkFXv3zV199tXxF2fXXX281eK8eeHPppZemfe9vNa527drJdoRmvdwtiQIvQqzTxWLz5s0Te/fule2YJhz9U+07d+7Ue01qmpPpB/AHBX9iMoXxqXHu3r1b1KpVS1SrVk1+J1ZpsNOXTe/evXMMvCY98AL+cL722muO/VLu82O5eD+GNOg7BMpdXA4UNn6ss8mOw+kHWQVbnK4FPKzm8ssvtwVhdQV/+/btZeAtVaqUfA+qWoQ5DajXumvXLus96jOmwxzuQw895Mk+OVHgVRehYf7oEDwnTpwo2/Vp+uGHH+R7Ny5aw1HjzZs328qwjMx6velQ8xLVF3DkUcfAa4czG08//bT8I6OWk1PgxR++l19+Wa7/qkwPvFieO3bssHWnYPFjuXg/hjR4sXOl9HA5UNj4sc4mOw7Vn96/CrYIbjgNj6oHCFf6RWuov9qrVy9x0003ycCLBncsQP9qWLj45vjjj5e3ssIrqkvgwqcaNWqIF198MelpNKkjpqZ0h5edRIEXcAoa473hhhvk3SkKFSokKleubHU3pwnVRfQytOM2a3qDIK0zhwHqtmU4PY7P4I4NTv2lA8NBgwsDTeYRajpavxl/ZtQfH9TFVRYsWGC1oxqD3p95cdqiRYtk/+YfKAoGt7avnHg/hjSoHYJbcFpQb3BqxIQLNIYPH269R3/qak/dc889Jz+PjQf9mLAxofzPP/+U7/v165dl/PrnnIbx6aefio8++khu2ObnzM9jB6nK1FWsbsJywMUBRGHh5r4jO36MI2jc/s6ou6xfbAcIJIMHD7aVwaBBg0Tfvn3Fb7/9ZitHmWngwIHWEyLR3WzM+ohOw1A+/vhj2V0dUXaD279vRFHgxzbh/RjS4PYOAcPCDlM1Xbp0kWW4olPvRx+nfgpF+euvv6yykSNHyvYzzzzT1g92jij//fff5fuzzz5btGjRwjZ+NAr6Na/cxlXWuAUOTlGq/lGXDad39M937NhRFClSRNZLQtlZZ52VZZozheHhccnm/NItXbpUfs/bbrvN7ETkO7e3ASd+jCNo4vidvWD+1hCRP/sX78eQBrd3CE7Dwq1OGjVqJNtxjz7Up8KFA+oCDcB9/XAfSgXD2bp1q2xH4EU3c9h4j1NueuA1jyjo1HfVbyGkAq8OpymHDRtmKzPHDbj9Cm7T4hZ9HFWrVpXvcWRGWbx4sSxXUFeKp4woNzltF27zYxxBE8fv7AW3f9+IosCPbcL7MaTB7R2C07BKly5t3WYG3ffv3y9++eUXUaJECVt/6IZ6QahDhptYK3rgVdUXEFpxc+tUAy/qHqmbZ0OygbdOnTqyYr6XAdOcd5hPOOWI8qFDh2bpjj8E5rQT+clcJ73gxziCJo7f2Qtu/74RRYEf24T3Y0iD2zsENTyzAYRUfVzmeHEhiNP0qMCLZ7bjSTDwwgsvyGoPZuA1x+s0PtxGqF69erI92cALH3zwgbxgRQ3XvFl8pjBMXBWrN5g+lF955ZVZ5guugm3cuHGWz4StMb8XBZ+6eT+q+mBbatq0qdmLa+K4fsTxO3vB/A0gIn/2L96PIQ1u7xByGhZu3q7GpxrcbFyHMlSB0KnAq7rrr2bgTXSEV8EN5XGz81QCrwnDmDRpklmcNn36PvzwQ/n+nHPOscqefPJJOS8UHDnH7V/CLqd1hoLJXGb/+Mc/5B9SL5jjioM4fmcvqN8ZIjrGj23C+zGkwe0dQk7DQjdUCdAbs3+8zynwog4rTuWrC9jSDbxq3HfffXdSgdecTsAFcrh9j1swDjy9Bq+4c4QTPPJULbPDhw+bnUPJad5SsDktM9zD0wtO44q6OH5nL6h9JREd48c24f0Y0uD2DiG7YaHurHq8pw7942Is/X1OgRf3yMRwUJ0BzMCLAIt7P+qNurDMnDbUFUZZMoEXj0rEeHEDewwTVSvw2UOHDtn6ywSGN2TIELM48szlQsFnLjM8KIBHeN2j9sts3GmI6Bg/tgnvx5AGt3cI2Q0Ld2nAU4RMbdu2lbf7UvD5nAIv6OMwA6+5o0Mzc+bMLJ9TUC0hmcAL+FHHtGI4ZcuWlY8WdZPT9MVBXL93mOGpZPgTiEe04n6tXi5DL4cdVHgohLkfY5NeQ0R2fmwX3o8hDdwpBEdcl0Ncv3fY4Y9mlSpVxH/+8x+zk6u4fhARucePfar3Y0gDA29wxHU5xPV7RwGW3a+//moWu4rrBxGRe/zYp3o/hjQw8AZHXJdDXL932OGx31h2+n2tvcD1g4jIPX7sU70fQxoYeIMjrsshrt877NS+A3Xz586da3Z2DdcPIiL3+LFP9X4MaWDgDY64Loe4fu8wwy3IPv30U2vZub0M1X7JbPDQGCIiSp/b+2sn3o8hDQy8wRHX5TBlyhSziALODLqtW7cWU6dO1fpwT1y3CyIiL/ixT/V+DGkwj6Cwyd2G4sFc7mxyt7n66qvNRUREFEnY53nN+zGkydz5s8mdxs2ntrlt7dq1ZlHadu7cabVv27ZNvuJerslw6g/3gg0bc9mzyd2GgZeI4gL7PK95PwYij2zcuNEsSlvFihWt9gcffFC+JrsBOvU3e/Zssyjw8D0KFChgFlMuYOAlojhx+h11m/djIPLIlVdeKV8XLVok8uXLJ0444YQsR1YPHz4sypUrJ4oVKybGjx8vy77++mtRuHBhUb16dXHkyBFx0UUXZTm6BuoVDzMoWbKkqFChgjhw4IAs69Onj7z11cCBAx03VDzqGU/Ma9KkiXyPdqVq1aqiV69e1vugYOANDgZeIooTp99Rt3k/BiKPqMCrbyiDBg2y2gHdEGqhW7du8rVo0aLyFWFYfTanI7x6CETZ/v375WOcYd68eY4b6l133SVfP/74Y7FkyRLRvXt32S849R8EDLzBwcBLRHHix++i92Mg8ogKvNOnTxf58+eXG4yqf6sg1OLoLrpNmDBBlqFdbyCnwGv2/+OPP4rPPvvM6t9pQ1VP+sL0nHfeebK9Vq1aYuXKlVbwDRoG3uBg4CWiOHH6HXWb92Mg8ogKvMr7778vqy84QTUGtUF16tTJ6Jpz4L3gggusbvDLL7+Idu3aWe+dNlQVajds2CBatGgh29Hf/fffb1WLCBoG3uBg4CWiOHH6HXWb92Mg8ogKvDi6O3HiRDFmzBhRp06dLP28/PLL8iIy9AcIddOmTRN9+/YVF198sSzDxrZgwQLZXr9+fasMihcvLgPziBEjRM2aNa1uCLV169Z13FAxroULF4qCBQuKgwcPyjLc8QLvg4qBNzgYeIkoTpx+R93m/RiISNqyZYt47rnnzOLAYOANDgZeIooTBl6iiHj00UdFkSJFzOJAYeANDgZeIooTBl6iXFKlShWzKPIYeIODgZeI4oSBlyiX+LHxBQ0Db3Aw8BJRnPjxm+v9GIhCyI+NL2gYeIODgZeI4sSP31zvx0AUQn5sfEHDwBscDLxEFCd+/OZ6PwaiEPJj4wsaBt7gYOAlojjx4zfX+zEQhZAfG1/QMPAGBwMvEcWJH7+53o+BKIT82PiChoE3OBh4iShO/PjN9X4MRCHkx8YXNAy8wcHAS0Rx4sdvrvdjIAohPza+IDh06JDYuXOnbHc78D788MNymKo544wzrHEpW7duFW3atBH58uUTpUuXFm+++aatO+zfv19cdtllchg1atQQ8+fPt3U3l9W+fftk2XfffZelO9p/+ukn6z1UqFBBDBs2zFbWsmVL+XjowoULiz59+ti6wYABA0SJEiXk/OrcubPZOWOYzhNPPNEsJiKKJHM/7gXvx0AUQn5sfH5ZvHixfJDGyJEjzU5i27ZtYt68ebLdi8B7yimniE6dOsmmWLFiWZ42lydPHjneO++8U1x44YWy/fXXX7f1kzdvXlmOYRQqVEi279q1y+puLisE0VKlSlnvzcCLcerMwItpRH8tWrQQl156qWzHeJXZs2fLssaNG4sHHnhAtt90001WdzdgmGjwR8D8k6Ds3r1bXHzxxaJfv35mJyKiUDH3417wfgxEIeTHxucHfI927drJo6SjR4/OEji9DrzNmjWzlenztWDBguLrr7/Wuh6FfrZv3y7bEVz79+9v675x40bZz8qVK+V7fZgnn3yyOP/88633YAZejLdv375WmR54EVzPPPNMq5tSqVIlMXbsWNmOebR3715bd7fXFwxPVWm48cYbZYhftWqV1f3zzz8Xp556qjxCjiPWmE9YlkREYeT2PtSJ92MgCiE/Nj6v4YiueVS3Q4cOYvPmzdZ7PwPvwYMHs4RPJ23btpVVGCC7fnDkU3VTr1WrVhXXXXed3pvkNE68HjhwQLbrgRfl+HOQE3yn6tWrexow9cCr4Luh/JdffnGcL05lRERh4Mf+y/sxEIVQ3bp1Q9+gisCvv/5q+16jRo0S55xzjtVP7dq15ZFCtHsReDFMvfn222+t7tnt4BYsWCAqVqwoT+Vn18+1115rC6/VqlUTZcuWFWeddZbRp3PgHT58uKyjC2bg1f3www9Ws2jRIqv8lVdekUdd1ffSj766AcPE8PXledJJJ1nf1ZxO9RlzHWDDhg2bsDRey7rXJKJIwAVpJUuWFIcPH7bKEIqOHDlivffzCC/Gi3GsWLFCvncKbdCzZ08ZyiG7fooWLWoLvHr/b7/9tt6rbRh6OwIl6gXnFHhRHQQN6hgXL17c1k1Zv359lvmaKQxPP8KL+s8I9DhKDvgzgzq8Cv4k3HPPPdZ7IiKyc/41IaJIWLJkiXURFppNmzbZuvsZeKF169aiQYMGsh3jW7Nmja07oI7twoULZTsuFpswYYLRx9HPTpo0yWpXEALN0Jpd4MUfArw/7rjjrMCLPwjt27e3+lF+/PFHK/Caw1dlKoy6AcO75JJLZDUNHIXfs2eP2Yucj2q54gI7IiLKXtY9NxHFBkKaqovqReDFXQ5mzZolmxEjRtjC4tq1a+V7VKmYMmWKvBALd2RA0NOhHxy9xDDeffdd+f6DDz6wddcNGjQo25Br9jtt2jRZpgIvjtKiqgOqRkycOFF88cUX8nZp6Of999+X/Tz44INyOj/66CM5Tc2bN7eqR7gF48ORZyIicgcDLxFJbgfeHj16yNuSqeaWW24xe5GWL18uTj/9dNGoUSNb9Qvd4MGD5TCcjmSi3IQyFZz17k79ItyOGTPGVoa6z/Xq1RO1atUSq1evtnUDHHHF0WsM77333jM7ZwzLwrxojYiI0sfAS0SS24GX0sfAS0TkLgZeIpIYeIODgZeIyF0MvEQkMfAGBwMvEZG7GHiJSGLgDQ4GXiIidzHwEpHEwBscDLxERO5i4CUiiYE3OBh4iYjcxcBLRBIDb3Aw8BIRuYuBl4gkBt7gYOAlInIXAy8RSQy8wcHAS0TkLgZeIpIYeIODgZeIyF0MvEQkMfAGBwMvEZG7GHiJSGLgDQ4GXiIidzHwEpHEwBscDLxERO5i4CUiiYE3OBh4iYjcxcBLRBJCFpq8efOyyeWGgZeIyF0MvERkUaGXTe43RETkHu5ViYiIiCjSGHiJiIiIKNIYeImIiIgo0hh4iYiIiCjSGHiJiIiIKNIYeImIiIgo0hh4iYiIiCjSGHiJiIiIKNIYeImIiIgo0v4fQDtsteDV3h8AAAAASUVORK5CYII=>

[image2]: <data:image/png;base64,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>
