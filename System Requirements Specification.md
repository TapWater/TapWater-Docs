- Jonathan: Other Nonfunctional Requirements, Other Requirements, Appendices
- Cody: System Features
- David: Overall Description
- Kon-Kon: Introduction, External Interface Requirements


# System Requirements Specification

## Introduction

### Purpose 

Identify the product whose software requirements are specified in this document, including the revision or release number. Describe the scope of the product that is covered by this SRS, particularly if this SRS describes only part of the system or a single subsystem.

### Document Conventions

Describe any standards or typographical conventions that were followed when writing this SRS, such as fonts or highlighting that have special significance. For example, state whether priorities  for higher-level requirements are assumed to be inherited by detailed requirements, or whether every requirement statement is to have its own priority.

### Intended Audience and Reading Suggestions

Describe the different types of reader that the document is intended for, such as developers, project managers, marketing staff, users, testers, and documentation writers. Describe what the rest of this SRS contains and how it is organized. Suggest a sequence for reading the document, beginning with the overview sections and proceeding through the sections that are most pertinent to each reader type.

### Product Scope

Provide a short description of the software being specified and its purpose, including relevant benefits, objectives, and goals. Relate the software to corporate goals or business strategies. If a separate vision and scope document is available, refer to it rather than duplicating its contents here.

### References

List any other documents or Web addresses to which this SRS refers. These may include user interface style guides, contracts, standards, system requirements specifications, use case documents, or a vision and scope document. Provide enough information so that the reader could access a copy of each reference, including title, author, version number, date, and source or location.

## Overall Description

### Product Perspective

Describe the context and origin of the product being specified in this SRS. For example, state whether this product is a follow-on member of a product family, a replacement for certain existing systems, or a new, self-contained product. If the SRS defines a component of a larger system, relate the requirements of the larger system to the functionality of this software and identify interfaces between the two. A simple diagram that shows the major components of the overall system, subsystem interconnections, and external interfaces can be helpful.

### Product Functions

Summarize the major functions the product must perform or must let the user perform. Details will be provided in Section 3, so only a high level summary (such as a bullet list) is needed here. Organize the functions to make them understandable to any reader of the SRS. A picture of the major groups of related requirements and how they relate, such as a top level data flow diagram or object class diagram, is often effective.

### User Classes and Characteristics

Identify the various user classes that you anticipate will use this product. User classes may be differentiated based on frequency of use, subset of product functions used, technical expertise, security or privilege levels, educational level, or experience. Describe the pertinent characteristics of each user class. Certain requirements may pertain only to certain user classes. Distinguish the most important user classes for this product from those who are less important to satisfy.

### Operating Environment

Describe the environment in which the software will operate, including the hardware platform, operating system and versions, and any other software components or applications with which it must peacefully coexist.

### Design and Implementation Constraints

Describe any items or issues that will limit the options available to the developers. These might include: corporate or regulatory policies; hardware limitations (timing requirements, memory requirements); interfaces to other applications; specific technologies, tools, and databases to be used; parallel operations; language requirements; communications protocols; security considerations; design conventions or programming standards (for example, if the customer’s organization will be responsible for maintaining the delivered software).

### User Documentation

List the user documentation components (such as user manuals, on-line help, and tutorials) that will be delivered along with the software. Identify any known user documentation delivery formats or standards.

### Assumptions and Dependencies

List any assumed factors (as opposed to known facts) that could affect the requirements stated in the SRS. These could include third-party or commercial components that you plan to use, issues around the development or operating environment, or constraints. The project could be affected if these assumptions are incorrect, are not shared, or change. Also identify any dependencies the project has on external factors, such as software components that you intend to reuse from another project, unless they are already documented elsewhere (for example, in the vision and scope document or the project plan).

## External Interface Requirements

### User Interfaces

Describe the logical characteristics of each interface between the software product and the users. This may include sample screen images, any GUI standards or product family style guides that are to be followed, screen layout constraints, standard buttons and functions (e.g., help) that will appear on every screen, keyboard shortcuts, error message display standards, and so on. Define the software components for which a user interface is needed. Details of the user interface design should be documented in a separate user interface specification.

### Hardware Interfaces

Describe the logical and physical characteristics of each interface between the software product and the hardware components of the system. This may include the supported device types, the nature of the data and control interactions between the software and the hardware, and communication protocols to be used.

### Software Interfaces

Describe the connections between this product and other specific software components (name and version), including databases, operating systems, tools, libraries, and integrated commercial components. Identify the data items or messages coming into the system and going out and describe the purpose of each. Describe the services needed and the nature of communications. Refer to documents that describe detailed application programming interface protocols. Identify data that will be shared across software components. If the data sharing mechanism must be implemented in a specific way (for example, use of a global data area in a multitasking operating system), specify this as an implementation constraint.

### Communications Interfaces

Describe the requirements associated with any communications functions required by this product, including e-mail, web browser, network server communications protocols, electronic forms, and so on. Define any pertinent message formatting. Identify any communication standards that will be used, such as FTP or HTTP. Specify any communication security or encryption issues, data transfer rates, and synchronization mechanisms.

## System Features

This template illustrates organizing the functional requirements for the product by system features, the major services provided by the product. You may prefer to organize this section by use case, mode of operation, user class, object class, functional hierarchy, or combinations of these, whatever makes the most logical sense for your product.

### System Feature 1

Don’t really say “System Feature 1.” State the feature name in just a few words.

#### 4.1.1	Description and Priority

Provide a short description of the feature and indicate whether it is of High, Medium, or Low priority. You could also include specific priority component ratings, such as benefit, penalty, cost, and risk (each rated on a relative scale from a low of 1 to a high of 9).

#### 4.1.2	Stimulus/Response Sequences

List the sequences of user actions and system responses that stimulate the behavior defined for this feature. These will correspond to the dialog elements associated with use cases.

#### 4.1.3	Functional Requirements

Itemize the detailed functional requirements associated with this feature. These are the software capabilities that must be present in order for the user to carry out the services provided by the feature, or to execute the use case. Include how the product should respond to anticipated error conditions or invalid inputs. Requirements should be concise, complete, unambiguous, verifiable, and necessary. Use “TBD” as a placeholder to indicate when necessary information is not yet available.

Each requirement should be uniquely identified with a sequence number or a meaningful tag of some kind.

- REQ-1:	
- REQ-2:	

### System Feature 2 (and so on)

...

## Other Nonfunctional Requirements

### Performance Requirements

Performance issues are not expected form TapWater.
Simplicity is a fundamental element of the design.

Performance will vary depending upon device and system version.

Changing between screens and processing button presses will be handled by the built in features of the SDK for the given mobile device and should perform at device expectations.

Sycnhronization time may vary depending on network connectivity.
The data exchanged should be optimized to assure the fastest synchronization possible.
A local cache of drinks will be kept by the system so that it does not have to load data from the server repeatedly.

### Safety Requirements

Use of the system should not present any harm to the user's device.

TapWater should not be used while operating a motor vehicle or any other kind of dangerous machinery.

Users should not use TapWater to consume more than a healthy amount of water.
What is considered a "healthy" amount of water varies from person to person. 
If a user is uncertain they should seek the advice of a doctor.

Users should not use TapWater if they have a condition in which water consumption may damage their health.

### Security Requirements

The drink data is not sensetive information.
It is still private user information and should be secured using standard database security protocols.

The system communicates usernames, passwords, and device information over the network.
This communication should be encrytpted with an HTTPS connection.
Additionally, the database should not store plain text user passwords.

Specify any requirements regarding security or privacy issues surrounding use of the product or protection of the data used or created by the product. Define any user identity authentication requirements. Refer to any external policies or regulations containing security issues that affect the product. Define any security or privacy certifications that must be satisfied.

### Software Quality Attributes

The user interfaces should be appealing to the eye.
The system should follow a consistent design style with a consistent color scheme.

The mobile applications should be available on their respective software marketplaces.
The iOS app should be available on the Apple App store.
The Android app should be available on the Google Play store.

The data synchronized to each of a user's devices should be consistent with the data on the other devices.

## Other Requirements

The database on the iOS and Android apps will be a SQLite databse.
The schema will look like the following:

#### Drinks

| Field Name | Description                                                           |
|------------|-----------------------------------------------------------------------|
| uuid       | A unique identifier for the drink.                                    |
| category   | The type of drink. Possible values are "drink", "glass", and "bottle" |
| drink_date | The date/time the drink was logged                                    |

The database on the Server will have the following schema:

#### Users

| Field Name      | Description                                        |
|-----------------|----------------------------------------------------|
| username        | The user's username                                |
| password_digest | The password hash and salt for the user's password |

#### Devices

| Field Name   | Description                                              |
|--------------|----------------------------------------------------------|
| device_token | The token this device will use to authenticate API calls |
| device_type  | The type and system version of the device                |
| user_id      | Foreign key for the user associated with the device      |

#### Drinks

| Field Name | Description                                                           |
|------------|-----------------------------------------------------------------------|
| uuid       | A unique identifier for the drink.                                    |
| category   | The type of drink. Possible values are "drink", "glass", and "bottle" |
| drink_date | The date/time the drink was logged                                    |
| user_id    | Foreign key for the user associated with the drink                    |

## Appendix A: Glossary

Define all the terms necessary to properly interpret the SRS, including acronyms and abbreviations. You may wish to build a separate glossary that spans multiple projects or the entire organization, and just include terms specific to a single project in each SRS.

## Appendix B: Analysis Models

Optionally, include any pertinent analysis models, such as data flow diagrams, class diagrams, state-transition diagrams, or entity-relationship diagrams.

## Appendix C: To Be Determined List

Collect a numbered list of the TBD (to be determined) references that remain in the SRS so they can be tracked to closure.