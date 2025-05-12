# Database-Normalization-Postgres-Installation-and-Application-Insight
Case Study File Link: https://lily-plate-b6a.notion.site/Case-Study-082bcd700e034e0b85a54bf82ba590ab?pvs=4
# Case Study

A Medical Database System is needed to enhance the efficiency and effectiveness of healthcare services. This system will be able to seamlessly integrates the information of patients, doctors, appointments, medical records, and medical facilities.

**Entities:**

1. **Patients:**
    - Attributes: PatientID (Primary Key), FirstName, LastName, DateOfBirth, Gender, ContactNumber, Email
2. **Doctors:**
    - Attributes: DoctorID (Primary Key), FirstName, LastName, Specialization, ContactNumber, Email
3. **Appointments:**
    - Attributes: AppointmentID (Primary Key), PatientID (Foreign Key), DoctorID (Foreign Key), AppointmentDate, AppointmentTime, Status
4. **Medical Records:**
    - Attributes: RecordID (Primary Key), AppointmentID (Foreign Key), Diagnosis, Prescription, TestResults, createdAt
5. **Medical Facilities:**
    - Attributes: FacilityID (Primary Key), FacilityName, Location, ContactNumber

**Relationships:**

- Patients can have multiple appointments with different doctors.
- Doctors can have multiple appointments with different patients.
- Each appointment may have a corresponding medical record, and vice versa.
- A medical facility can have multiple doctors, and a doctor can work in multiple medical facilities. This relationship is represented through a junction table.

## 6-1 understanding Anomalies
- Anomalies in database refer to unexpected issues that can occur during data manipulation or retrieval 
## there are 3 main types anomalies
![alt text](image-1.png)

## 6-2 Understanding Functional Dependency.
## What is Normalization?
- Normalization is organize data in database

# Normalization in 2 types 1.Functional Dependency 2.Normal Forms

1. # Functional Dependency
![alt text](image-2.png)
If two rows have the same value of attribute X, and in both cases the value of Y is also the same, then we say:
X → Y (X functionally determines Y)
if not same? not functional Dependency

🔹 What is Functional Dependency?
In a database table, if one column's value uniquely decides another column’s value, we call that a functional dependency.

We write it as:

X → Y
(Read as: "X determines Y")

That means:

If two rows have the same value of X, they must have the same value of Y.

✅ Example:
StudentID 	Name	Department
101 	Munna	 CSE
102 	Rakib	 EEE
103	  Munna	    CSE

Now see this:

StudentID → Name ✅ (Because each StudentID is unique and gives only one Name)

Name → Department ✅ (In this table, Munna is always in CSE, Rakib in EEE)

But Department → Name ❌ (One department can have many students with different names)

🔸 Why It’s Important?
Functional dependencies help in:

Database Design

Normalization (breaking large tables into smaller ones to remove redundancy)

Avoiding data duplication and update errors

 Real-Life Analogy:
Think of a National ID Card:=

Your NID number → Your Name ✅

But Your Name → NID ❌ (Many people can have the same name)


![alt text](image-3.png)

## 6-3 Normalization and 1st Normal Forms (1NF)
2. ## Normal Forms
![alt text](image-4.png)
![alt text](image-5.png)