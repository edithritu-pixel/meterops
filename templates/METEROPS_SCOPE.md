Author: Edith Nderitu
Project: MeterOps System
Version: 1.0
Date: June 2026
SCOPE



## 1. Project Overview



MeterOps is a web-based Meter Lifecycle Management System developed to automate and track the end-to-end process of meter replacement, testing, reabsorption, and disposal within Nairobi Water operations.



The system provides visibility and accountability for meter movements, field activities, inventory management, work planning, testing activities, and disposal processes.



The application replaces manual tracking methods such as spreadsheets, paper records, emails, and fragmented reporting processes.



---



## 2. Problem Statement



Meter replacement activities involve multiple departments and stakeholders, including field technicians, supervisors, work order assistants, test bench officers, and disposal teams.



Currently, tracking meter movement and workflow progression is largely manual, resulting in:



* Limited visibility of meter status

* Difficulty tracking removed meters

* Delayed system updates

* Poor accountability for allocated meters

* Inconsistent reporting

* Challenges monitoring inventory levels

* Limited audit trails



---



## 3. Project Objectives



The system aims to:



* Digitize meter replacement operations

* Track meter lifecycle from request to closure

* Improve accountability of meter inventory

* Provide workflow visibility across departments

* Support operational reporting and decision-making

* Create a centralized repository for meter records

* Reduce manual record keeping



---



## 4. Users



### Metering Supervisors



* Create work plans

* Allocate replacement meters

* Assign technicians

* Monitor workflow progress



### Field Technicians



* Install replacement meters

* Return removed meters

* Capture field remarks



### Work Order Assistants



* Update customer and billing systems

* Record update outcomes

* Escalate exceptions



### Metering Officers



* Review completed updates

* Prepare records for batching



### Test Bench Office



* Record testing results

* Classify meters as passed or failed



### HQ Disposal Office 



* Review faulty meters

* Process disposal workflow



### Management



* Monitor operational performance

* Generate reports

* Track inventory utilization



---



## 5. Core Modules



### Dashboard



Provides operational statistics and workflow visibility.



### Regional Operations Queue (ROQ)



Tracks all requests and workflow stages.



### Work Plan Management



Manages allocation, technician assignment, and field progress.



### Meter Inventory Management



Tracks available, allocated, installed, reabsorbed, faulty, and disposed meters.



### Customer Account Management



Stores customer reference information.



### System Updates



Tracks updates to operational systems following field activities.



### Batching Module



Groups completed records for testing processes.



### Test Bench Module



Records technical testing outcomes.



### Disposal Module



Tracks faulty meters through disposal workflow.



### Reporting Module



Provides operational and management reports.



---



## 6. Workflow



New Request

→ Work Plan Creation

→ Meter Allocation

→ Field Installation

→ Work Order Update

→ Pending Batching

→ Test Bench Evaluation

→ Passed Testing OR Failed Testing



Passed Testing

→ Reabsorption into Inventory



Failed Testing

→ Regional Disposal Review

→ HQ Disposal

→ Disposal Confirmation



---



## 7. Technology Stack



Backend:



* Python

* Flask

* SQLAlchemy



Database:



* MySQL



Frontend:



* HTML

* Jinja2 Templates

* CSS



Reporting:



* Pandas

* OpenPyXL



File Handling:



* Werkzeug File Uploads



---



## 8. Current Status



Current system status is MVP (Minimum Viable Product).



Implemented functionality includes:



* Authentication

* Meter inventory management

* Customer account uploads

* Work plan management

* Meter allocation

* Field workflow management

* Work order tracking

* Batching workflow

* Test bench workflow

* Disposal workflow

* Reporting and Excel exports



---



## 9. Future Enhancements



* Role-based access control

* Email notifications

* SMS notifications

* GIS integration

* API integration with enterprise systems

* Audit logging enhancements

* Performance dashboards

* Workflow approvals

* Cloud deployment



---



## 10. Expected Benefits



* Improved operational visibility

* Reduced manual processes

* Better accountability

* Faster reporting

* Improved inventory control

* Complete audit trail for meter lifecycle management

* Improved decision-making through operational data