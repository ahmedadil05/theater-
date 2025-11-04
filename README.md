# theater-
OOP-Project Documentation: Event Ticketing System

1. Project Overview

This project is an Object-Oriented Programming (OOP) implementation of a basic Event Ticketing System. It is currently structured as a console application designed to handle user authentication (Customer or Organizer), event management, and ticket purchasing/booking.

Key Concepts Implemented:

Inheritance: Classes like Customer, Organizer (implied from headers), EconomyTicket, and VipTicket (implied from headers) inherit from base classes like User and Ticket.

Encapsulation: Classes manage their own data (e.g., Booked_Tickets within Customer).

Polymorphism: The Ticket class likely uses virtual functions (like displayTicketInfo() and generateSeatLabel()) overridden by derived classes (EconomyTicket and VipTicket).

2. Project Structure (C++ Files)

The project is logically divided into header (.h) and implementation (.cpp) files.

File Name

Description

Key Features / Status

main.cpp

Contains the main function and the console menu flow.

Defines customerView(), organizerC(), and placeholder functions for user interaction logic (e.g., browsing, booking, info display). Currently uses hardcoded menu options and commented-out dummy object creation.

Customer.h

Defines the Customer class, inheriting from User.

Manages a static customersList. Tracks Booked_Events and Booked_Tickets. Includes methods for addTicket, DisplayTickets, updateCustormerInfo, and cancelBookingT (empty definition).

Customer.cpp

Implementation file for the Customer class.

Currently empty, suggesting most definitions are inline in the header or still need implementing.

EconomyTicket.h

Defines the EconomyTicket class, inheriting from Ticket.

Declares the constructor and overrides polymorphic methods.

EconomyTicket.cpp

Implements the EconomyTicket class.

Implements polymorphism with displayTicketInfo() and generateSeatLabel(). The seating logic is defined: row = seatNumber / 10 + 8 (starting rows from 'I' or 'J').

Event.h / Event.cpp

(Implied/Referenced in other files)

Expected to contain event details (name, date, location, ticket limits, etc.) and core logic for handling ticket sales.

Ticket.h / Ticket.cpp

(Implied/Referenced in other files)

Expected to be the base class for tickets, defining common attributes like ticketId, price, and pure virtual functions for polymorphism.

organizor.h / organizor.cpp

(Implied/Referenced in CMakeLists.txt)

Expected to define the Organizer user type for event creation and management.

User.h / User.cpp

(Implied/Referenced in other files)

Expected to define the base User class with common attributes like name and email.

VipTicket.h / VipTicket.cpp

(Implied/Referenced in CMakeLists.txt)

Expected to define the premium ticket type, likely overriding polymorphic functions for VIP-specific seating/details.

3. Build Configuration

The project uses CMake for its build system, ensuring a standard compilation process.

CMakeLists.txt: Targets the C++17 standard and lists all project headers and source files for compilation into a single executable named OOP_Code_file.

CMakeSettings.json: Configures the project for Visual Studio/CMake integration, setting up an x64-Debug configuration using the Ninja generator.

4. Next Steps for Development

The foundational class structure is present, but much of the core logic and object interaction needs completion.

A. Core Class Implementation

Implement User & Ticket: Complete the declarations and definitions for the base classes (User.h, User.cpp, Ticket.h, Ticket.cpp) to support the derived classes.

Implement Event Logic: Ensure Event stores necessary data and contains the actual logic for creating and issuing tickets when buyTickets is called, including updating LeftTickets.

Complete Customer Functionality: Define the customersList static member and fully implement updateCustormerInfo() (currently incomplete in the header) and cancelBookingT().

Implement Organizer: Create the Organizer class to manage event creation and event-specific reports.

Implement VipTicket: Define the class, including its unique seating logic (likely rows A-H).

B. Menu and Interaction Flow

Integration: Replace placeholder comments (e.g., //! user events 1, //? function to cancel the booking) in main.cpp with calls to the actual class methods (e.g., Customer::DisplayTickets(), Customer::cancelBookingT(ticket)).

Input Validation: Add robust input validation for all user input (cin >> ...) across all menu functions.
