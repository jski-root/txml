# Trap XML (txml)
 Trap XML is a modeling language to describe a Domain to Environment Generation, Deployment and Application Processes using a mix of BPMN, DMN, BPEL (without WS) and XSD. txml is used to describe an Enterprise's domains and model them into a particular target such as Jakarata EE, Spring, C, Rust, Python, Web Assembly and many more with XSLT.
 
 This application is alignment with Model Base Software Engineering (MBSE) tools that can map **txml** to SysML, XMI, TOGAF, NAF and DoDAF documents. **Models** are first class citizens in txml. Integrations with PM tools for scheduling and traceability of assignments and Large Language Models (LLM) or Machine Learning (ML) to accelerate Developer's productivity. The LLM or LM is to assist in with the quering and menial tasks such as reports and boilerplate coding that doesnt require any critical thought or analysis!
 
## Standards
 Using BPMN's extension element, we can insert the BPEL algorithm. With BPMN's start element, will be transformed into a UI input element or Web Service endpoint.
 
 - BPMN 2.0
 - BPEL 2.0 without WS
 - XSD
 - XSLT
 
 
## Features
 The code will have the ability to deploy to an image with users and roles defined by a standard protocol such as OAuth 2.0 or LDAP
 
 - Simulations
 - Code Generation
 - LLM querying of Domains/Models
 
## Target Environment
 Targeting a Jakarta EE micro profile environment such as Quarkus and HTMX front end for the Application. Java 21 for modeling and generating from XSLT. Application will work as Desktop or Server Side Rendering. Shall have the exact same behavior.
 
## Trap XML Development
 This repository relies heavly on BPMN, XSD and BPEL editors with Maven Plugins. txml shall eat its own dog food and generate its self through the models.
 
 
## TXML Agent
 Shadow Agent/OS in lieu of containers. install an agent on base image and setup with certificates and configure git URLs to txml shall build the domain(s) on that asset
 
## Case Against Containerization
 seems ineffecient, why build a cluster of computers that run containers that behave like they are running on a monolith. It seems like that running JavaEE on the cluster and have the deployment of EAR file full of @Stateless EJBs would be more effecient and easier to manage.
 
## YAML or JSON Considerations
 Just say no! Both of these markups are useless and the software industry seems to be getting worse as time goes on. YAML has no schema definitions and JSON is just a serialization of data for one particular language.  