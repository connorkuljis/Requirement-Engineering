---
title: Requirements Engineering Assignment 2
school: Curtin University, Perth WA
unit: CMPE2002
name: Connor Kuljis
id: 19495138

date: 2020-11-06

example: Case Study 1 Report - "Customer Line Up"

---
/newpage
# Report

# Introduction
Software applications can provide new solutions to problems existing in the world today.
The case study "Customer Line Up" is a project to help solve the issue of large queues that
violate coronavirus social distancing in essential businesses.


# Methodology
This document will cover; the suitable requirement elicitation techniques to 
analyze the requirements, and the relevant modeling diagrams to show aspects 
of the system. 

The components of this document include:
* A (2) page report
* Appendix A - UML Diagrams and i* Models
* Appendix B - Software Requirement Specification (SRS)
* Appendix C - Wireframe/Mockups

There are a wide variety of requirement elicitation (RE) techniques that suit 
the requirements gathering process for the “CLup: Customer Lineup” project. 
Requirements engineering often has no “right way” when designing requirements 
for a software system, and such requirements may change over time. Requirement 
elicitation methods include; introspection, background reading, hard data, 
interviews, surveys, meetings, focus groups, brainstorm/JAD, prototypes, 
ethnomethodology, participant observation and knowledge elicitation.

When gathering requirements, it is often important to do some background reading 
on the domain to see if there exists any similar systems within that domain. 
This may be in the form of researching related applications. Upon researching online, 
a highly relevant example is the appointment
booking website ‘HotDoc’ - https://www.hotdoc.com.au/ which allows users to book 
appointments for general practitioners around Australia. This 'hotdoc' system
overlaps with the key covid-19 related issues 'CLup' is trying to solve. Such as
incorporating a time slot booking system, mobile check-ins and 'place in queue'.
The advantage of this background reading is that it helps define business objectives
and how a similar approach could be inspired and adapted to a grocery store.


To further gather requirements, a common methodology is a brainstorm.
A brainstorm allows analysts to come up with potential ideas and characterise topics for discussion. For example - 
who are the potential stakeholders of the product? What is the ‘problem’ that the 
project is aiming to solve? By using introspection, some potential users
of the product may be - the users themselves, employees, managers, maintanence ect.

# Discussion
To reiterate there is often no such "best way" when gathering requirements. 
When writing requirements, many audiences are featured, with varying technical and
non-techinal backgrounds; this can make communicating functions into specifications rather difficult.
Good specifiactions are complete, unambiguous and consistent.
A limitation on the analysis is that it is succeptable to self
bias and a lack of external opinions. Because of the absence of feedback from others
an inherit bias may have impacted the overall design.

# Conclusion

/newpage
# Appendix A Models
![](RE_UML.png)
![](i star.png)
/newpage
---
# Appendix B SRS
title: Software Requirements Specification for **Customer Line Up**
author: Connor Kuljis
version: 1.0
date: 2020-11-06
format: Karl E. Weigers SRS Format

---
\newpage

# 1 Introduction
# 1.1 Purpose
This document is a manual of software requirements for the "Customer Lineup" project,  assisting in managing customer queues outside essential stores.

# 1.2 Document Conventions
DB - Database
ER - Entity Relationship
JDBC - Java Database Connectivity
AWS - Amazon Web Services
EC2 - Conmpute platform for AWS
MySQL - Open source relational database management system
RDS - Relational Cloud Database Service
CI/CD - Continuous Integration / Continuous Delivery

# 1.3 Intended Audience and Reading Suggestions
This document may be useful for key stakeholders such as store managers, employees as well as customers.
This document may be useful for organisations and teams such as developers, testers, project managers, marketing and customer service.

# 1.4 Project Scope
The system is a mobile and web based platform, integrated with relational database and queue management features.
The purpose of this customer queueing software is to assist customers in finding the right store to place in-queue, reserve and book timeslots. The software is to ease store management and create engaging insights for 
store managers and employees.


# 1.5 References
```
https://d1.awsstatic.com/whitepapers/AWS_Cloud_Best_Practices.pdf
https://aws.amazon.com/rds/
https://aws.amazon.com/ec2/
https://reactnative.dev/
https://www.mysql.com/
https://docs.oracle.com/javase/tutorial/jdbc/basics/index.html
https://aws.amazon.com/compliance/iso-27018-faqs/
https://www.w3.org/standaords/webdesign/accessibility
```

# 2. Overall Perspective

# 2.1 Product Perspective
The customer queueing software contains the following information:

# Store Details
* It includes store location address and postcode, along with the available opeining hours.

# Customer Details
* It includes details such as email, name, phone number, postcode. This data is used to keep record 
of customer activity and provide notifications to customers

# Queue 
It includes deatails such as queue name, the number of users in the queue, who is at the front 
of the queue, expected wait time. Verifying members of the queue

# QR Code Generator and Booking Features
It includes information about the user account such as booking time, address ect.


# 2.2 Product Features
The product is an new and innovative system to replace existing line-up processes outside stores.
The features of the system can be seen in a UML Use Case Diagram
![UML Use Case](Case.png)

# 2.3 User Classes and Characteristics
# Customer
* Customers of the system should be able to find information about a store and its location. 
Customers can make bookings, which provides notification functionality and optional information about
their booking, such as the duration and type of purchase. Users can enter a queue, which updates
based on the current size of the queue and will alert the user when they are at the front of the queue.
Customers interface with the system through a qr code on their device, or printed on paper.

# Employees
* Employee user privellages allow the same sub-class features as a customer, but have higher priority features
to view information about the store, scan or create QR codes. Managers are one heirarchy up, inheriting all the features
of an employee, but being able to update store information (such as hours, opening times) and generate reports.

# 2.4 Operating Environment
Operating environment for the queueing system follows:

* Server Hosting: AWS EC2 w/ Ubuntu Linux
* Database: Amazon RDS for MySQL
* Mobile: iOS and Android
* Web: Native browser (Chrome/Firefox)
* Platform: Java + JDBC (Backend), Javascript/React(Frontend)

# 2.5 Design and Implementation Constraints
# Accessibility
Website accessibility is a concern for users of all ages and backgrounds. 
The web must be suit and provide access to people with diverse abilities.
Groups such as those with disabilities, the elderly and those with lower access to technology must be concidered.
    - Accessibility conventions can be found at *https://www.w3.org/standards/webdesign/accessibility*
    - Additionaly provide offline measures such as a QR code print functions

# Scalability and Reliability
Developers must conform to the AWS Well-Architected Framework Whitepaper where possible in the management and provisioning of servers.

# Regulation storing customer information
    - (PII) must be stored in compliance with ISO/IEC 27018:2019 Certification.

# 2.6 User Documentation
* User tutorial guide component is to be placed on the website which users can visit through a link.
* Store managers can liase with product managers/developers on how to get started with the system.

# 2.7 Assumptions and Dependencies

# 3. System Features

# 3.1 The system must update and vertify the database when new accounts are created
* Description: Customer and Employee Account creation. Medium priority.
* Stimulus/Response Sequences: User opens the application and selects "Create new account" option.
* Functional Requirement:
    - REQ-01: Users should be able to create an account
    - REQ-02: User information should be validated and error checked via database calls

# 3.2 The system should update and vertify the database when signing in accounts
* Description: Customer and Employee Account log-in. Medium priority.
* Stimulus/Response Sequences: User logs in as user OR guest
* Functional Requirement:
    - REQ-03: Users can sign in as guest
    - REQ-04: Users can log into a valid user account

# 3.3 The system should allow users to join a queue
* Description: Customers/Employee enter the queue. High Priority
* Stimulus/Response Sequences: User selects the "Join Queue Option"
* Functional Requirement:
    - REQ-05: Users can join a queue which will notify them when it is their turn
    - REQ-06: The system must generate a QR code for users who join a queue
    - REQ-07: Users can leave the queue

# 3.4 The system should provide booking appointments
* Description: Users can select timeslots for designated appointments. Low priority
* Stimulus/Response Sequences: User selects the "Book Appointment Option"
* Functional Requirement:
    - REQ-08: System should have a timeslot booking function
    - REQ-09: The system must generate a QR code for users who place a booking
    - REQ-10: Users can cancel a booking
    - REQ-11: Users must be notified of thier bookings
    - REQ-12: Users can note the type, purpose and duration of their appointment
    - REQ-13: The system must record/log appointments for reporting

# 3.5 The system should allow users to find and designate a store location
* Description: Users can set their local store preference
* Stimulus/Response Sequences: Users selects the "Find Store Search"
* Functional Requirement:
    - REQ-14: Users can search for a nearby store by current location
    - REQ-15: Users can search for a nearby store by postcode
    - REQ-16: Users can search for a nearby store by address
    - REQ-17: The system must record a users selected location

# 3.6 The system must generate QR Codes
* Description: QR Code which acts verifies entrance to the sotre
* Stimulus/Response Sequences: Acts upon queue or booking
* Functional Requirement:
    - REQ-18: The system by able to view the QR Code

# 3.7 The system must allow employees to scan QR Codes
* Description: employees scan customer QR codes to update the database
* Stimulus/Response Sequences: Employee uses camera to scan QR code on app
* Functional Requirement:
    - REQ-19: The system must provide QR scanning features only for employees
    - REQ-20: The system must update the database and verify codes.

# 4. External Interface Requirements

# 4.1 User Interfaces
* Web Front-end software: Javascript using React framework.
* iOS and Android Front-end software: React Native Modile App framework.

# 4.2 Hardware Interfaces
Hardware interfaces in which the system will interact with:
* Various iOS and Android Smartphones, notabily cameras.
* Browsers that supports HTML and Javascript.

# 4.3 Software Interfaces
The software will interface with a wide variety of devices.
* Responsive Design

# 4.4 Communication Interfaces
* Public network required to connect to Amazon servers (LAN/WAN).

# 5 Other Nonfunctional Requirements

# 5.1 Performance Requiremeonts
# Queue Response Time
    - Queue real time system should not be delayed more than 30 seconds.
# Queue Throughput
    - Queue real time tracking must handle 500 customers per store .
# Notification Response Time
    - Notifications must not be delayed by more than 30 seconds.
# Application Reliability
    - Application must be available 99.5% of the year.

# 5.2 Safety Requirements
    - Database secrets/credentials must be stored securely.
    - Backups of the database are to be stored in deep storage. Must handle complete failure/ loss of data.
    - Access/Changes to the database and software must be documented in the form of logs.
    - Encryption should be enforced where possible (End to End Encryption/ SSL).

# 5.3 Security Requirements

# Privacy Regulation
    - Customer information/personally identifiable information (PII) must be stored in compliance with ISO/IEC 27018:2019 Certification.
# Security
    - Control Systems for access to cloud resources must be enforced by access policies.

# 5.4 Software Quality Attributes
    - Scalability: system must increase or decrease resouces to meet demand.
    - Flexibility and Testability: system must be able to roll back to previous version as a failsafe (CI/CD).

# 6. Other 
Assertions: The application is a web and mobile based platform. Managers may want to edit opening hours through the application. Instead of having seperate accountsfor employees, they can download the app and create QR codes via guest.1


# Appendix C Wireframe/Mockups
![](Wireframe.png)
![](qr.png)
![](desktop.png)






