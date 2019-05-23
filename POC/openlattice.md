# OpenLattice company

**Web-site:** [https://openlattice.com](https://openlattice.com)

**CEO:** Matthew Tamayo-Rios, [https://www.linkedin.com/in/matthewtrios/](https://www.linkedin.com/in/matthewtrios/)

**Size:** 10-15 employees

**Description:** OpenLattice enables organizations to deploy data-driven workflows against data integrated across silos such as law enforcement, emergency medical services, mental health, behavioral health, and homeless management information systems into a standard data model. Building a platform that provides storage, compute, privacy, security, and compliance features necessary to support the operational workflows that help people get their assistance they need.

**Funding:** Pre-Series A

**Clients** :
- Iowa&#39;s Johnson County justice system
- Pennsylvania&#39;s Berk County healthcare, justice solutions

# OpenLattice product
**Licensing:** GPL-3.0

**Pricing:** free for core services

**GitHub:** [https://github.com/openlattice](https://github.com/openlattice?type=source)

**Code age:** around 1 year

**Demo:** [https://openlattice.com/agora](https://openlattice.com/agora/#/login)

**API Swagger:** [https://docs.openlattice.com](https://docs.openlattice.com/#/)

**Knowledge base:** [https://help.openlattice.com](https://help.openlattice.com/)

**Description:** cloud based multitenant platform deployed to AWS Gov Cloud. Intended to be used by local government entities for data collection and analytics.

**Features:**
1. 	__Graph oriented data storage__ for Entity Data Model (EDM)
2. Provide extensive __REST API__ for data manipulation and reporting (OData protocol)
3. __Data Explorer__ – provides web based search and data navigation capabilities with ability to find connections between objects
4. __Access integrated data using materialized views__
5. __Data Linking__ - machine learning technology can link disparate data sources and give you a unified profile of a consumer
6. __Machine learning capabilities__
7. __Permission/Data Sharing__ -  data can be easily de-identified and shared within other stakeholders. it was designed to handle fine-grained permissions without breaking any compliance regulations


# OpenLattice technologies and architecture
![](https://github.com/ca-cwds/development-practices/blob/master/images/openlattice/openlattice_architecture.png)
Diagram based on review of public GitHub repositories of OpenLattice Platform

## EDM
The concepts of an EDM are abstract ideas of entities (objects or nodes) and associations (relationships), constructed by properties. The 3 key concepts are:
- Entity types: Specific node objects that are top-level nouns (e.g., patients, encounters, providers, insurances, diagnoses)
- Associations: connecting one entity type to another
- Property types: define structure and characteristics of entity and association types.
![](https://github.com/ca-cwds/development-practices/blob/master/images/openlattice/EDM.png)

## OData
Allows to create queryable and interoperable RESTful APIs. Compared to GraphQL but better.

OData can be used to access table like structures much the same way ODBC does.

Entity Data Model (EDM) used to describe OData Services. EDM modeling tools available to model OData Services:
- Each entity can support Create,  Read, Update, and Delete (CRUD) operations
- Can navigate relationships
- Complex Types supported

**URI Components**

![](https://github.com/ca-cwds/development-practices/blob/master/images/openlattice/OData_URL.png)

REST OData protocol supports aggregation, sorting, pagination, change sets (transactions), etc.