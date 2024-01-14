Security Design Review Template 

Authors: Nielet D’mello and Swathi Joshi 

Publish Date: January 16, 2024


**Introduction**

This section establishes the scope and goal of the product/ service/feature/platform. In this section clearly define what needs protection (data, systems, infrastructure, etc.) and why. 

Some questions to consider- What does the application do? Provide business context, Describe the service or product. Consider walking through a User story. Business needs and value propositions are to be documented and articulated here. 

Product/ App/Service Name: 
Stage of Review: Public Beta/ Private Beta/ GA

**Audience**

List all the teams responsible for review, input, and decision-making. List all the relevant technical artifacts with links to internal sites where the artifacts are located (Git repo, JIRA, confluence etc) 

**Roles and Responsibility**

Name
Team
Role


Example:  Product Team, Security Team, Ops Teams. Legal
Contributor/ Decision Maker/Reviewer


**API Endpoints**

Endpoints
Payload / Schema/ Methods
Description


**Architecture and Data Flows**

Placeholder for architecture diagrams, data flow diagrams, etc.

**Preventative Security Controls**

Goal: Secure design hardening, understanding current security measures and solutions to evaluate their limitations and effectiveness

Security Controls
Descriptions
Implementation Notes
Business and Application Logic
How does data flow between users and applications
How and what business rules are implemented within the application code
What operations and type of operations are supported
How might the app’s logic be misused or abused




Secure Software Development Lifecycle (SDLC)
Do you follow secure coding checklists, and security requirements, and perform security testing
Is there usage of centralized, vetted, secure, and reusable security controls (paved paths/components)
Are functional security constraints tested as part of user stories during development




Authentication / Authorization
How do application components authenticate with each other
(frontends, REST/gRPC/GraphQL APIs, ORMs, middlewares, DBs)
How does the app check authorization? (e.g. a user having admin vs user privileges)


Access Control
Does the app follow the principle of least privilege at function, data, files, controllers, services, etc.
Trusted enforcement points (gateways, servers, serverless functions, etc.) enforce appropriate access controls
Does the app support Role-based (RBAC) and Location-based (LBAC)


Safe and secure I/O handling
Safe deserialization, encoding, and validation of data based on type, content, and applicable laws, regulations, and other policy compliance
Is input validation and output encoding performed


Cryptography and secure communications
This covers integrity, confidentiality, privacy and authentication
Does the app perform encryption at rest and in transit
Does the application encrypts communications between components, particularly when these components are in different containers, systems, sites, or cloud providers


Auditing
What actions are audit logged
Are audit logs decorated with attributes that identify who took the action, what action they take (read, create, delete, update, invoke), where did the action come from (user ID, IP address, service name, service routes) and what did they target?


Data Protection and Privacy
Sensitive data is identified and classified into protection levels (per your data classification standards)
Privacy is ingrained wherever applicable


Secrets handling
Where are secrets stored and what does access look like for these
Does your application avoid and prevent logging secrets in cleartext
How is secret leak detected and revocation handled
Secrets lifecycle- Generation, Rotation, Revocation, Deletion


**Detective Security Controls**

Goal: Detect abuse & misuse, ensure continuous monitoring capabilities are in place

Security Controls
Details
Implementation Notes
Log Ingestion 
Whats logs do we need from this application and infrastructure components? ex. containers, K8s clusters?  for relevant detections and monitoring and are they being ingested into a SIEM solution  


Monitoring, and Incident Response
Do we have basic level 1 triage set up? Do we have an Incident Response playbook for any incidents that will arise? 


WAF Placement and Enablement
If applicable Web application firewall to be enabled to provide DDoS related protection. Any applicable blocking rules and policies should be discussed. 


SAST  Static Application Security Testing 

DAST Dynamic Application Security Testing

SCA- Software Composition Analysis
SAST: Finding potential security issues through the static analysis of the source code and ensuring we scan for all OWASP issues via a standard tool
DAST: Scanning for secrets stored in the source code
Finding security issues in the deployed application:
API security validation
UI based security validation
Cluster Configurations




Threat Modeling
Perform threat modeling to map relevant Threat Actors and motivations against the properties of the application and data stored in it.


Pen Testing 
Internal, an external, or a third party- any or all pen testing options should be considered. After initial assessments, the remediation plan and timeline are to be agreed upon.


Relevant Compliance Framework applicability 
List any compliance frameworks this application falls under the scope for. Any regulatory obligations if regionalized need to be noted here as well. 


Third-party Dependency and Review 
Any third-party dependencies, tools libraries need to be reviewed.  




**Summary **
What is the high-level takeaway for the developers and business teams from this review? It could be a ranked list from high confidence to low confidence, it could be an aggregate score and associated guidance to your developer teams.

**Risks Identified **
List of potential risks and threats both internal and external documented here with a severity to risk attached. 

**Trade-offs**
Explicit listing of trade-offs between security, performance, reliability, cost, and usability.

**Action Items **
The Next steps and owners are to be listed here. 

