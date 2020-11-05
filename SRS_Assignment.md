# Requirements Engineering
# Assignment 2 - SRS

# 1 Introduction
## 1.1 Purpose
This document is a manual which will provide the software requirements for the "CLup: Customer Lineup" project, which assists in managing customer queues outside essential stores, especially in a COVID-19
impacted environment.

## 1.2 Document Conventions
DB - Database
ER - Entity Relationship
JDBC - Java Database Connectivity
AWS - Amazon Web Services
EC2 - Conmpute platform for AWS
MySQL - Open source relational database management system
RDS - Relational Cloud Database Service
CI/CD - Continuous Integration / Continuous Delivery

## 1.3 Intended Audience and Reading Suggestions
This project is 

## 1.4 Project Scope
The purpose of this customer queueing software is to assist customers in finding the right store to place in-queue, reserve and book timeslots. The software is to ease store management and create engaging insights for 
store managers and employees.
The system is a mobile and web based platform, integrated with relational database and queue management features.


## 1.5 References

# 2. Overall Perspective

## 2.1 Product Perspective
The customer queueing software contains the following information:

* Store Details

* Customer Details

* Queue and Booking Features

* QR Code Generator

## 2.2 Product Features
The product is an new and innovative system to replace existing line-up processes outside stores.
The features of the system can be seen in a UML Use Case Diagram
![UML Use Case](Case.png)

## 2.3 User Classes and Characteristics
* Customer
Customers of the system should be able to find information about a store and its location. 
Customers can make bookings, which provides notification functionality and optional information about
their booking, such as the duration and type of purchase. Users can enter a queue, which updates
based on the current size of the queue and will alert the user when they are at the front of the queue.
Customers interface with the system through a qr code on their device, or printed on paper.

* Employees
Employee user privellages allow the same sub-class features as a customer, but have higher priority features
to view information about the store, scan or create QR codes. Managers are one heirarchy up, inheriting all the features
of an employee, but being able to update store information (such as hours, opening times) and generate reports.

## 2.4 Operating Environment
Operating environment for the queueing system follows:

* Server Hosting: AWS EC2 w/ Ubuntu Linux
* Database: Amazon RDS for MySQL
* Mobile: iOS and Android
* Web: Native browser (Chrome/Firefox)
* Platform: Java + JDBC (Backend), Javascript/React(Frontend)

## 2.5 Design and Implementation Constraints
Website accessibility is a concern for users of all ages and backgrounds.

Camera Scanning

Scalability and Reliability

Regulation storing customer information

## 2.6 User Documentation
* User tutorial guide component is to be placed on the website which users can visit through a link.
* Store managers can liase with product managers/developers on how to get started with the system.

## 2.7 Assumptions and Dependencies

# 3. System Features

## 3.1 Create Account
* Description: Customer and Employee Account creation. Medium priority.
* Stimulus/Response Sequences: User opens the application and selects "Create new account" option.
* Functional Requirement:
    - REQ-01: User should be able to create an account
    - REQ-02: User information should be validated via database calls

## 3.2 Log-in 
* Description: Customer and Employee Account log-in. Medium priority.
* Stimulus/Response Sequences: User logs in as user OR guest
* Functional Requirement:
    - REQ-03: Users can sign in as guest
    - REQ-04: Users can log into a valid user account

## 3.3 Queue Functionality
* Description: 
* Stimulus/Response Sequences: 
* Functional Requirement:

## 3.4 Booking System
* Description: 
* Stimulus/Response Sequences: 
* Functional Requirement:

## 3.5 Store Location
* Description: 
* Stimulus/Response Sequences: 
* Functional Requirement:

## 3.6 QR Code Generation
* Description: 
* Stimulus/Response Sequences: 
* Functional Requirement:

# 4. External Interface Requirements

## 4.1 User Interfaces
* Web Front-end software: Javascript using React framework
* iOS and Android Front-end software: React Native Modile App framework

## 4.2 Hardware Interfaces
Hardware interfaces in which the system will interact with
* Various iOS and Android Smartphones, notabily cameras
* Browsers that supports HTML and Javascript

## 4.3 Software Interfaces
The software will interface with a wide variety of devices
* Responsive Design

## 4.4 Communication Interfaces
* Public network required to connect to Amazon servers (LAN/WAN)

# 5 Other Nonfunctional Requirements

## 5.1 Performance Requiremeonts
# Queue Response Time
    - Queue real time system should not be delayed more than 30 seconds.
# Queue Throughput
    - Queue real time tracking must handle 500 customers per store 
# Notification Response Time
    - Notifications must not be delayed by more that 30 seconds.
# Application Reliability
    - Application must be available 99.5% of the year.

## 5.2 Safety Requirements
    - Database secrets/credentials must be stored securely.
    - Backups of the database are to be stored in deep storage. Must handle complete failure/ loss of data.
    - Access/Changes to the database and software must be documented in the form of logs
    - Encryption should be enforced where possible (End to End Encryption/ SSL)

## 5.3 Security Requirements
# Privacy Regulation
    - Customer information/personally identifiable information (PII) must be stored in compliance with ISO/IEC 27018:2019 Certification
# Security
    - Control Systems for access to cloud resources must be enforced by access policies

## 5.4 Software Quality Attributes
    - Scalability: system must increase or decrease resouces to meet demand
    - Flexibility and Testability: system must be able to roll back to previous version as a failsafe (CI/CD)

# 6. Other 






