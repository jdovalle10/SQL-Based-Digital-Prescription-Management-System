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
