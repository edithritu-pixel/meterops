Author: Edith Nderitu
Project: MeterOps System
Version: 1.0
Date: June 2026

# SYSTEM_ARCHITECTURE.md



# MeterOps System Architecture



## Overview



MeterOps is a Flask-based web application designed to manage the complete lifecycle of water meter replacement activities.



The application follows a simple MVC-style structure where:



* MySQL stores application data

* Flask handles business logic and routing

* HTML templates provide the user interface

* SQLAlchemy manages database interactions



---



# Project Structure



```text

Meter System V2

│

├── app.py

├── requirements.txt

├── uploads/

├── templates/

│

├── add_record.html

├── inventory.html

├── work_plan.html

├── roq.html

├── test_bench.html

├── reports.html

└── other templates

```



---



# Core Components



## 1. app.py



### Purpose



The central application file containing all system functionality.



### Responsibilities



#### Application Configuration



* Flask initialization

* MySQL database connection

* Upload folder configuration

* Session management



#### Authentication



* Login

* Logout

* Session validation



#### Database Models



Contains all database entities:



* MeterRecord

* MeterInventory

* CustomerAccount

* WorkPlan



#### Workflow Engine



Controls movement of records through workflow stages:



```text

New Request

→ Allocated

→ Awaiting Work Order Update

→ Pending Batching

→ Pending Test Bench

→ Passed Testing / Failed Testing

→ Reabsorbed / Disposal

```



#### Inventory Management



Functions include:



* Meter allocation

* Inventory updates

* Reabsorption

* Disposal tracking



#### Reporting Engine



Generates:



* Workflow reports

* Meter replacement reports

* Batching reports

* Disposal reports

* Technician performance reports



#### Excel Export Services



Exports operational data to Excel using:



* Pandas

* OpenPyXL



---



## 2. Templates Directory



### Purpose



Contains all user interface screens.



### Key Screens



#### Dashboard



records.html



Displays:



* Workflow statistics

* Regional summaries

* Operational KPIs



---



#### ROQ



roq.html



Displays:



* New requests

* Workflow queue

* Status tracking



---



#### Work Plan



work_plan.html



Displays:



* Planned work

* Allocations

* Field activities



---



#### Inventory



inventory.html



Displays:



* Available meters

* Allocated meters

* Meter status information



---



#### System Updates



system_updates.html



Displays:



* Pending work order updates

* Update tracking



---



#### Batching



batching_queue.html



Displays:



* Pending batching records

* Batch creation functions



---



#### Test Bench



test_bench.html



Displays:



* Testing queue

* Meter evaluation activities



---



#### Disposal



pending_disposal.html



Displays:



* Disposal workflow

* HQ disposal processing



---



#### Reports



reports.html



Displays:



* Available operational reports

* Report navigation



---



## 3. Uploads Directory



### Purpose



Stores uploaded files including:



* Meter photographs

* Return documents

* CSV uploads

* Supporting workflow files



---



## 4. Requirements File



requirements.txt



### Purpose



Defines Python dependencies required to run the application.



Examples include:



* Flask

* Flask-SQLAlchemy

* Pandas

* OpenPyXL

* PyMySQL

* Werkzeug



---



# Workflow Architecture



## Stage 1: Request Creation



Work plan is created.



System generates:



* WorkPlan record

* MeterRecord record



---



## Stage 2: Meter Allocation



Supervisor allocates:



* Replacement meter

* Technician



Inventory status changes:



Available → Allocated



---



## Stage 3: Field Installation



Technician performs field work.



Possible outcomes:



* Installed

* Returned to Store



---



## Stage 4: Work Order Update



System update team processes completed field activities.



Possible outcomes:



* Updated

* Not Updated



---



## Stage 5: Batching



Completed updates are grouped into testing batches.



---



## Stage 6: Test Bench



Removed meter is tested.



Possible outcomes:



* Pass

* Fail



---



## Stage 7: Final Processing



### Pass



Meter is reabsorbed into inventory.



Status:



Reabsorbed



### Fail



Meter enters disposal workflow.



Status:



Pending Disposal



---



## Stage 8: Disposal



HQ acknowledges receipt.



Meter status becomes:



Disposed



Workflow closed.



---



# Security Controls



Current implementation includes:



* Login authentication

* Session validation

* Protected routes

* Controlled workflow transitions



Future enhancements:



* Role-based access control

* Password encryption

* Audit logging

* User permissions



---



# Scalability Considerations



Current Version:



* Single Flask application

* Single MySQL database

* Monolithic architecture



Future Improvements:



* Modular blueprint architecture

* Separate service layers

* API integration

* Cloud deployment

* Mobile access



---



# System Objective



Provide a centralized platform for managing meter replacement operations, inventory control, testing, disposal, reporting, and accountability across the complete meter lifecycle.