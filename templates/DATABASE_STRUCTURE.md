Author: Edith Nderitu
Project: MeterOps System
Version: 1.0
Date: June 2026

# DATABASE_STRUCTURE.md



# MeterOps Database Structure



## Database Engine



MySQL 8



---



# 1. MeterRecord



## Purpose



Stores the complete lifecycle of a meter replacement request from creation through testing, reabsorption, or disposal.



## Primary Key



| Field | Type    |

| ----- | ------- |

| id    | Integer |



## Core Customer Information



| Field          | Type        | Description             |

| -------------- | ----------- | ----------------------- |

| account_number | String(100) | Customer account number |

| customer_name  | String(200) | Customer name           |

| region         | String(100) | Operating region        |



## Allocation Information



| Field           | Type        | Description                 |

| --------------- | ----------- | --------------------------- |

| allocated_meter | String(100) | Replacement meter allocated |

| allocated_to    | String(100) | Assigned technician         |

| date_allocated  | String(100) | Allocation date             |



## Meter Replacement Information



| Field                | Type        | Description                      |

| -------------------- | ----------- | -------------------------------- |

| removed_meter        | String(100) | Removed meter number             |

| final_reading        | String(100) | Final reading from removed meter |

| return_date          | String(100) | Return date                      |

| returned_meter_photo | String(300) | Returned meter image             |



## Request Information



| Field    | Type        |

| -------- | ----------- |

| source   | String(100) |

| category | String(100) |

| status   | String(100) |



## Workflow Tracking



| Field                | Type        |

| -------------------- | ----------- |

| workflow_stage       | String(100) |

| roq_status           | String(100) |

| system_update_status | String(100) |



## Testing Information



| Field              | Type        |

| ------------------ | ----------- |

| test_bench_result  | String(100) |

| test_bench_remarks | String(500) |

| testbench_remarks  | String(500) |



## Disposal Information



| Field            | Type        |

| ---------------- | ----------- |

| disposal_remarks | String(500) |



## Remarks and Comments



| Field               | Type         |

| ------------------- | ------------ |

| assistant_comment   | String(500)  |

| pending_reason      | String(300)  |

| remarks             | String(500)  |

| operational_remarks | String(1000) |

| field_remarks       | String(500)  |

| update_reason       | String(500)  |

| rts_reason          | String(500)  |



## Audit Information



| Field         | Type        |

| ------------- | ----------- |

| created_by    | String(100) |

| date_created  | String(100) |

| assigned_team | String(100) |



---



# 2. MeterInventory



## Purpose



Stores all meters available for allocation and meters returned from the field.



## Primary Key



| Field | Type    |

| ----- | ------- |

| id    | Integer |



## Meter Information



| Field        | Type        |

| ------------ | ----------- |

| meter_number | String(100) |

| meter_size   | String(20)  |

| branch       | String(100) |

| region       | String(100) |



## Location Information



| Field            | Type        |

| ---------------- | ----------- |

| current_location | String(100) |



## Inventory Status



| Field  | Type        |

| ------ | ----------- |

| status | String(100) |



### Typical Status Values



* Available

* Allocated

* Installed

* Pending Test Bench

* Test Bench

* Reabsorbed

* Faulty

* Disposed



---



# 3. CustomerAccount



## Purpose



Stores customer account information imported from enterprise systems.



## Primary Key



| Field | Type    |

| ----- | ------- |

| id    | Integer |



## Customer Information



| Field           | Type        |

| --------------- | ----------- |

| account_number  | String(100) |

| customer_number | String(100) |

| customer_name   | String(200) |

| current_meter   | String(100) |

| zone            | String(100) |

| region          | String(100) |



---



# 4. WorkPlan



## Purpose



Stores operational planning and field execution activities.



## Primary Key



| Field | Type    |

| ----- | ------- |

| id    | Integer |



## Customer Information



| Field          | Type        |

| -------------- | ----------- |

| account_number | String(100) |

| customer_name  | String(200) |

| region         | String(100) |

| current_meter  | String(100) |



## Planning Information



| Field       | Type        |

| ----------- | ----------- |

| reported_by | String(200) |

| category    | String(100) |

| priority    | String(50)  |

| status      | String(100) |

| remarks     | String(500) |

| created_at  | String(100) |



## Allocation Information



| Field           | Type        |

| --------------- | ----------- |

| allocated_meter | String(100) |

| allocated_to    | String(100) |

| date_allocated  | String(100) |



## Field Operations



| Field               | Type        |

| ------------------- | ----------- |

| field_status        | String(100) |

| date_installed      | String(100) |

| field_remarks       | String(500) |

| removed_meter_photo | String(300) |



## Office Return Information



| Field                  | Type        |

| ---------------------- | ----------- |

| office_return_document | String(300) |

| office_return_received | String(20)  |

| office_return_date     | String(100) |



## Work Order Information



| Field                  | Type        |

| ---------------------- | ----------- |

| work_order_status      | String(50)  |

| work_order_comments    | Text        |

| work_order_updated_by  | String(100) |

| work_order_update_date | String(50)  |



## Closure Information



| Field         | Type        |

| ------------- | ----------- |

| cancel_reason | String(500) |



---



# Entity Relationships



CustomerAccount

│

│ Account Number

▼

WorkPlan

│

│ Account Number

▼

MeterRecord

│

│ Meter Number

▼

MeterInventory



The system uses Account Number and Meter Number as the primary business reference points linking operational records.