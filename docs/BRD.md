




Business Requirements Document(BRD) Template
Project/Initiative
Month 20YY
Version X.XX








Company Information


Document Revisions
Date
Version Number
Document Changes
05/02/20xx
0.1
Initial Draft


















































Approvals
Role
Name
Title
Signature
Date



















































































Introduction
Project Summary
Objectives
Improve the hotel booking process by providing transparent pricing, secure payment processing, and instant booking confirmation for users, reduce booking abandonment during payment, and support integration with external payment gateways and email notification services.



[These should describe the overall goal in developing the product, high level descriptions of what the product will do, how they are aligned to business objectives, and the requirements for interaction with other systems.]

Background
[Provide a brief history of how the project came to be proposed and initiated, including the business issues/problems identified, and expected benefit of implementing the project/developing the product.]



Business Drivers
[List the business drivers that make development of this product important. These can be financial, operational, market or environmental.] 


Project Scope
[Describe what work is in scope for the project, and specifically what work is out of scope… beyond the current budget, resources and timeline as approved by the project stakeholders. This is designed to prevent “scope creep” of additional features and functions not originally anticipated.]
In Scope Functionality
Hotel room booking process;
Display of booking details and included services;
Display of cancellation policy before payment;
Secure payment processing;
Support for Apple Pay and Google Pay;
Booking status management (Pending, Paid, Confirmed);
Booking confirmation via email;
Display of active bookings in the user account;
Payment retry after failed payment;
Temporary reservation hold during payment retry;
Integration with external payment gateways;
Integration with email notification services;




Out of Scope Functionality

Hotel search and filtering functionality;
Hotel reviews and rating system;
Loyalty programs and bonus systems;
Multi-language interface support;
Chat support functionality;
Hotel management dashboard for administrators;
Dynamic pricing management;
Mobile application development;
   
System Perspective
[Provide a complete description of the factors that could prevent successful implementation or accelerate the projects, particularly factors related to legal and regulatory compliance, existing technical or operational limitations in the environment, and budget/resource constraints.]
Assumptions

Constraints


Risks


.
Issues



Business Process Overview
[Describe how the current process(es) work, including the interactions between systems and various business units. Include visual process flow diagrams to further illustrate the processes the new product will replace or enhance.
Use case documentation and accompanying activity or process flow diagrams can be used to create the description(s) of the proposed or “To-Be” processes.]
Current Business Process (As-Is)
At any point during or after deployment of web apps or web sites (internal or external) to support business activities, development/support teams may create and deploy widgets. 
CMS / database administrators for the employee portal use the CMS tool to create widgets. They can test widgets in the designated staging environment, then register them and deploy to production.
Development teams may deploy widgets to development and testing environments set up for their development projects. They must check widget code into and out of the source code repository according to their projects’ development schedule.

Proposed Business Process (To-Be)
Technical Lead searches repository 
If widget is not found, user creates a new widget name record.
WINS validates that all fields have been completed.
WINS confirms that no similar widgets exist
User confirms record to be created.

User searches repository to locate existing widget description.
WINS displays record
User selects Edit to open and modify record
WINS validates all fields completed correctly
User confirms changes.
WINS confirms changes and updates Audit table.



Stakeholder Requirements

The user wants to see the final cost of the reservation before paying.
The user needs to see all the order details and exactly which services are included in the reservation.
The user wants to see the cancellation policy before paying.
The user wants fast and secure online payment methods (Apple Pay/Google Pay).
The user wants to immediately receive a booking confirmation in the form of a PDF receipt via email.
The user wants to view their current bookings in their personal account.
The owner wants secure payment processing for the booking after the user clicks the confirm button, via a payment gateway (Stripe/PayPal).
The owner wants user data to be encrypted in accordance with the PCI DSS standard.
The owner wants the system not to store the CVV code.
The owner wants the system to give the user 15 minutes to retry the payment in case of a payment error, while holding the selected room.

The requirements in this document are prioritized as follows:
Value
Rating
Description
1
Critical
This requirement is critical to the success of the project. The project will not be possible without this requirement.
2
High
This requirement is high priority, but the project can be implemented at a bare minimum without this requirement.
3
Medium
This requirement is somewhat important, as it provides some value but the project can proceed without it.
4
Low
This is a low priority requirement, or a “nice to have” feature, if time and cost allow it.
5
Future
This requirement is out of scope for this project, and has been included here for a possible future release.


Functional Requirements
Req#
Priority
Description
Rationale
Use Case Reference
Impacted Stakeholders
General / Base Functionality
FR-G-001
1
The system shall display the final booking price including taxes and fees before payment.




To provide transparent pricing information before payment.



UC-Checkout-01


User
FR-G-002
1
The system shall support Apple Pay and Google Pay payment methods.


To provide convenient payment options for users.


UC-Checkout-02


User
FR-G-003
1
The system shall send booking confirmation to the user’s email after successful payment.
To inform users about successful booking completion.


UC-Checkout-03


User
FR-G-004
1
The system shall allow users to retry failed payments within 15 minutes while keeping the selected room reserved.


To reduce booking abandonment caused by payment failures.


UC-Checkout-04


User
FR-G-005
1
The system shall display cancellation policy before payment.


To allow users to review cancellation conditions before booking confirmation
UC-Checkout-05


User
FR-G-006
1
The system shall display booking details and included services before payment.
To provide complete booking information before payment.
UC-Checkout-06


User
Security Requirements
FR-G-007
1
The system shall display booking information in the user personal account.


To allow users to manage and review active bookings.


UC-Checkout-07


User
FR-G-008
1
The system shall hold the selected room for 15 minutes after failed payment.


To prevent room loss during payment retry.


UC-Checkout-08


User
Reporting Requirements
FR-R-009
1
The system shall log all failed payment attempts.


To allow administrators to monitor payment issues.


C-Checkout-08
Admin 
FR-R-010
2
The system shall store booking status history for each reservation.


To track booking changes and support issue investigation.


C-Checkout-08
Admin 
FR-R-011
1
The system shall generate payment transaction reports for administrators.


To provide transaction monitoring and reporting capabilities.


C-Checkout-09
Admin 
Usability Requirements
FR-U-001
3
The booking process shall be completed in no more than 5 steps.


To simplify the booking process for users.


C-Checkout-10
User
FR-U-002
1
The booking interface shall correctly display on mobile devices and tablets.


To provide consistent user experience across devices.


C-Checkout-11
User
Audit Requirements
FR-A-001
1
The system shall store logs of all payment transactions.


To support transaction auditing and issue investigation.


C-Checkout-12
Admin




Non-Functional Requirements
[Include technical and operational requirements that are not specific to a function. This typically includes requirements such as processing time, concurrent users, availability, etc.]
ID
Requirement
NFR-001
The payment page shall load within 3 seconds.
NFR-002
The system shall display a payment failure message within 2 seconds after unsuccessful payment attempt.


NFR-003
The interface shall display all included services and additional fees before payment confirmation.


NFR-004


NFR-005





Appendices
List of Acronyms
[If needed, create a list of acronyms used throughout the BRD document to aid in comprehension.]

Glossary of Terms
[If needed, identify and define any terms that may be unfamiliar to readers, including terms that are unique to the organization, the technology to be employed, or the standards in use.]

Related Documents
[Provide a list of documents or web pages, including links, which are referenced in the BRD.]
