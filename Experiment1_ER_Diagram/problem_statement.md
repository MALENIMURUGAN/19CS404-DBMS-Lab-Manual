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

# ER Diagram Submission - Maleni M

## Scenario Chosen:
Hospital 

## ER Diagram:
![image](https://github.com/user-attachments/assets/9ef88ca8-9433-4f17-bfe9-5667c66e62af)


## Entities and Attributes:

- **Patient**: PatientID (PK), Full Name, Date of Birth, Gender, Address, Phone Number, Email, Insurance Details

- **Doctor**: DoctorID (PK), Full Name, Specialization, Phone Number, Email, Work Schedule

- **Department**: DepartmentID (PK), Department Name, Department Head

- **Appointment**: AppointmentID (PK), PatientID (FK), DoctorID (FK), Appointment Date, Appointment Time, Reason for Visit, Additional Notes

- **MedicalRecord**: MedicalRecordID (PK), PatientID (FK), DoctorID (FK), Diagnoses, Prescribed Medications, Treatments, Test Results, Additional Notes

- **Billing**: BillingID (PK), AppointmentID (FK), Amount, Payment Date, Payment Method, Payment Status



## Relationships and Constraints:Here is the section in your requested format:

- **Patient — "Has" — Appointment**
 *(Cardinality: 1:M, Participation: Total on Appointment side)*

- **Doctor — "Attends" — Appointment**  
  *(Cardinality: 1:M, Participation: Total on Appointment side)*

- **Department — "Belongs To" — Doctor**  
  *(Cardinality: 1:M, Participation: Total on Doctor side)*

- **Appointment — "Generates" — Billing**  
  *(Cardinality: 1:1, Participation: Total on both sides)*

- **Patient — "Has" — MedicalRecord**  
  *(Cardinality: 1:M, Participation: Total on MedicalRecord side)*

- **Doctor — "Writes" — MedicalRecord**  
  *(Cardinality: 1:M, Participation: Total on MedicalRecord side)*

- **Department — "Supervises" — Appointment**  
  *(Cardinality: 1:M, Participation: Optional on Appointment side)*


## Extension (Prerequisite / Billing):
Billing is modeled as a separate entity linked via a 1:1 relationship to Appointment, ensuring that each appointment has one and only one corresponding billing entry. It captures payment details such as amount, method, date, and status to support financial tracking and insurance processing.

## Design Choices:
In designing the hospital database, the relationships were structured to support normalization, reduce redundancy, and provide flexibility for querying. Each relationship reflects a logical real-world connection, and the cardinality and participation constraints were defined based on how entities interact with one another. Billing was modeled as a separate entity to maintain a clear separation of financial data, ensuring precise tracking of payments and appointments. Additionally, the inclusion of department supervision over appointments reflects real-life administrative oversight, enhancing the completeness and reliability of the database model.

## RESULT:
The ER diagram for the Hospital Database was successfully created, modeling key entities like Patient, Doctor, Appointment, and Billing. It includes correct relationships and constraints, reflecting the billing process. This exercise demonstrated the practical use of ER modeling for designing structured databases.
