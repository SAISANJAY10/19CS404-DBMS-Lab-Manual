# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission:

##### Student Name: SAI SANJAY R

##### Student Register No: 212223040178

## Scenario Chosen:

### Hospital 

## ER Diagram:

![diagram](https://github.com/user-attachments/assets/d0accfa2-65c2-4d04-b353-5c37fc318969)

## Entities and Attributes:

###### Department

Attributes: DEP_ID (Primary Key), DEP_NAME, DEP_HEAD

###### Doctor

Attributes: ID (Primary Key), NAME, PHONE, EMAIL, SPECIALIZATION, DEP_ID (Foreign Key)

###### Patient

Attributes: PATIENT_ID (Primary Key), NAME, ADDRESS, PHONE, EMAIL, INSURANCE_DETAILS

###### Appointment

Attributes: ID (Primary Key), DATE/TIME, DOCTOR_ID (Foreign Key), PATIENT_ID (Foreign Key)

###### Medical Record

Attributes: ID (Primary Key), RESULTS, TREATMENT, DIAGNOSIS, APPOINTMENT_ID (Foreign Key)

###### Billing

Attributes: ID (Primary Key), TOTAL_AMOUNT, DATE, PAYMENT_STATUS, PAYMENT_METHOD, APPOINTMENT_ID (Foreign Key)
 

## Relationships and Constraints:

###### Contains (Department ↔ Doctors)

Cardinality: 1 Department : N Doctors

Participation: Total on Department (each department must contain at least one doctor) and Partial on Doctor (a doctor belongs to one department)

###### Schedules (Doctor ↔ Patient)

Cardinality: N Doctors : N Patients

Participation: Partial for both (a doctor may schedule many patients; a patient may be scheduled by multiple doctors)

###### Books (Patient ↔ Appointment)

Cardinality: 1 Patient : N Appointments

Participation: Total on Appointment (every appointment must be booked by a patient)

###### Has (Appointment ↔ Medical Record)

Cardinality: 1 Appointment : N Medical Records

Participation: Partial for both (some appointments may have medical records; a record must be linked to an appointment)

###### Generates (Appointment ↔ Billing)

Cardinality: 1 Appointment : 1 Billing

Participation: Total on Billing (each billing entry must be generated by an appointment)

## Extension (Prerequisite / Billing):

Billing is designed as a separate entity linked to the Appointment entity via a one-to-one relationship. Each appointment generates a billing record that includes payment method, status, and total amount.

## Design Choices:

Entities: Chose Department, Doctor, Patient, Appointment, Medical Record, and Billing to reflect key operational areas in a hospital system.

Relationships:

Department Contains Doctors (1:N) – A department has multiple doctors.

Doctor Schedules Patient (N:N) – Doctors can see many patients; patients can see many doctors.

Patient Books Appointment (1:N) – A patient can have multiple appointments.

Appointment Has Medical Records (1:N) – Each appointment can produce multiple medical records.

Appointment Generates Billing (1:1) – Each appointment generates one billing entry.

Assumptions:

Each doctor is associated with one department.

Each appointment is booked by exactly one patient.

Medical records are only created after appointments.

Billing is tied directly to appointments and not handled independently.

## RESULT:

Thus, this project effectively models a hospital management system using an ER diagram, clearly representing the relationships among departments, doctors, patients, appointments, medical records, and billing.
