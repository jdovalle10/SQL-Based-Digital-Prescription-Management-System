# SQL-Based-Digital-Prescription-Management-System
## Overview
The healthcare sector faces challenges in ensuring that patients can efficiently procure the medications prescribed by their doctors. Traditionally, this process involves physical visits
to pharmacies, which can be cumbersome, particularly if the required drugs are not readily available. Patients may need to visit multiple pharmacies to find their prescribed drugs, and they often lack visibility into drug availability, pricing, and the convenience of various pharmacy locations.In this project, we created a database system that aims to manage the entire workflow from the issuance of a digital prescription to the successful procurement of medication.

## Goals
- Pharmacy Coordination: Pharmacies maintain real-time inventories of available drugs, including pricing and expiration details.
- Patient-Pharmacy Interaction: Patients can search for and order their prescribed drugs from nearby pharmacies, considering availability, pricing, and location.
- Order Management: Orders are processed digitally, ensuring that patients receive their medications efficiently and can track their order status.

## Users
**Patients:** The primary users who will interact with the system to manage their prescriptions, search for drugs, and place orders.
**Doctors:** Healthcare providers who will issue digital prescriptions and monitor patient medication histories.
**Pharmacies:** Entities responsible for managing drug inventories and fulfilling patient orders.

## Business Processes
**Prescription Management:** Doctors issue digital prescriptions that are securely stored and accessible to patients and pharmacies.

**Pharmacy Coordination:** Pharmacies maintain real-time inventories of available drugs, including pricing and expiration details.

**Patient-Pharmacy Interaction:** Patients can search for and order their prescribed drugs from nearby pharmacies, considering availability, pricing, and location.

**Order Management:** Orders are processed digitally, ensuring that patients receive their medications efficiently and can track their order status.

## Major Business Rules 
**Prescription Validation:** Patients must have a valid prescription from a licensed doctor to order medication.

**Inventory Management:** Pharmacies must regularly update their drug inventories, including quantities, prices, and expiration dates.

**Order Fulfillment:** Pharmacies are required to fulfill orders accurately and within the stipulated timeframe.

**Data Privacy and Security:** All patient, doctor, and prescription data must be stored securely and accessed only by authorized users.

**Patient Consent:** Patients must consent to share their prescription and order data with pharmacies and healthcare providers.

## Relational Schema
### Table: Patient
Patient (patient_id, patient_name, patient_dob, patient_gender, patient_phone, patient_height, patient_weight, patient_address)

Primary key: patient_id
### Table: Hospital
Hospital (hospital_id, hospital_name, hospital_address, hospital_phone, hospital_is_private)

Primary key: hospital_id
### Table: Doctor
Doctor (doctor_id, doctor_name, doctor_phone, doctor_speciality, hospital_id)

Primary key: doctor_id

Foreign key: hospital_id REFERENCES Hospital (hospital_id)
### Table: Drug
Drug (drug_id, drug_name, drug_manufacturer, drug_category, drug_instructions, drug_RRP)

Primary Key: drug_id
### Table: Pharmacy
Pharmacy (pharmacy_id, pharmacy_name, pharmacy_address, pharmacy_phone)

Primary key: pharmacy_id
### Table: Pharmacy_Drug_Listing
Pharmacy_Drug_Listing (stock_id(drug_id, pharmacy_id), quantity, price, expiration_date)

Primary key: stock_id (drug_id, pharmacy_id)

Foreign key: drug_id REFERENCES Drug (drug_id)

Foreign key: pharmacy_id REFERENCES Pharmacy (pharmacy_id)
### Table: Order
Order (order_id(prescription_id, drug_id), duration, frequency, quantity)

Primary key: order_id(prescription_id, drug_id)

Foreign key: prescription_id REFERENCES Prescription (prescription_id)

Foreign key: drug_id REFERENCES Drug (drug_id)
### Table: Prescription_Drug_Order
Prescription_Drug_Order (stock_id, order_id)

Primary key: stock_id, order_id

Foreign key: stock_id REFERENCES Pharmacy_Drug_Listing (stock_id)

Foreign key: order_id REFERENCES Order (order_id)
### Table: Prescription
Prescription (prescription_id, prescription_date, prescription_priority_status, prescription_expiry_date, patient_id, doctor_id)

Primary key: prescription_id

Foreign key: patient_id REFERENCES Patient (patient_id)

Foreign key: doctor_id REFERENCES Doctor (doctor_id)
