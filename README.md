# Clinic-Management-System.
# Telemedicine Clinic Management System

## Overview
This project is a **Service-Oriented Architecture (SOA)** based system for managing a telemedicine clinic. It provides SOAP and REST services for handling medical records, prescriptions, doctors, appointments, notifications, and patient tracking.

## Table of Contents
- [Motivation](#motivation)
- [Project Objectives](#project-objectives)
- [Architecture](#architecture)
- [Database Schema](#database-schema)
- [Services Implemented](#services-implemented)
- [Testing & Validation](#testing--validation)
- [Front-End Implementation](#front-end-implementation)
- [BPMN Process](#bpmn-process)
- [Installation & Usage](#installation--usage)
- [Contributors](#contributors)

---

## Motivation
Digital transformation in the medical field is crucial for improving healthcare quality and efficiency. This project aims to provide an **integrated information system** to manage appointments, medical records, and prescriptions effectively.

## Project Objectives
We developed **three SOAP services** and **three REST services**:

### SOAP Services:
1. **Medical Record Management** (CRUD operations for patient records)
2. **Prescription Management** (Adding and viewing prescriptions)
3. **Doctor Management** (Managing doctor profiles)

### REST Services:
1. **Appointment Management** (CRUD operations for patient-doctor appointments)
2. **Notification System** (Sending notifications via email/SMS)
3. **Patient Monitoring** (Tracking patient data and history)

## Architecture
The project follows a **modular and layered structure**:

```
TelemedicineClinic/
├── src/
│   ├── config/        # Database connection settings
│   ├── models/        # Entity classes (JPA)
│   ├── repositories/  # Data access layer
│   ├── services/      # Business logic layer
│   ├── resources/     # REST controllers
│   ├── webservices/   # SOAP services
│   ├── publisher/     # SOAP service publishers
├── pom.xml            # Maven dependencies
└── README.md          # Project documentation
```

### Project Structure Image
![Project Structure](images/project_structure.png)

## Database Schema
The database consists of six main tables:
- **Patients**: Stores patient information
- **Doctors**: Contains doctor details
- **Appointments**: Manages doctor-patient meetings
- **MedicalRecords**: Stores patient medical histories
- **Prescriptions**: Holds medication prescriptions
- **Notifications**: Tracks notifications sent to patients

### Database Schema Diagram
![Database Schema](images/database_schema.png)

## Services Implemented

### SOAP Services Example: Medical Record Service
- **MedicalRecord.java** (Entity class)
- **MedicalRecordRepository.java** (CRUD operations)
- **MedicalRecordWebService.java** (SOAP interface)
- **MedicalRecordWebServiceImpl.java** (Service implementation)

### REST Services Example: Appointment Service
- **Appointment.java** (Entity class)
- **AppointmentRepository.java** (Data access layer)
- **AppointmentResource.java** (REST API endpoints)

## Testing & Validation
### SOAP Service Testing with SOAP UI
Testing SOAP services was done using SOAP UI.
#### Example SOAP Request:
```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/">
   <soapenv:Body>
      <getMedicalRecord>
         <patientId>1</patientId>
      </getMedicalRecord>
   </soapenv:Body>
</soapenv:Envelope>
```
#### SOAP UI Test Result
![SOAP Test](images/soap_test.png)

### REST API Testing with Postman
We used Postman to test REST services, sending requests to `http://localhost:8080/api/appointments`.
#### Example GET Request:
```http
GET /api/appointments HTTP/1.1
Host: localhost:8080
```
#### Postman Test Result
![Postman Test](images/postman_test.png)

## Front-End Implementation
The front-end was developed using **HTML, CSS, JavaScript, and React.js** for dynamic UI elements. It allows users to interact with the services via REST APIs.

### UI Example Screenshot
![Front-End UI](images/frontend_ui.png)

## BPMN Process
To ensure efficient service orchestration, we modeled business processes using **Bonita BPM**.

### BPMN Diagram
![BPMN Workflow](images/bpmn_diagram.png)

## Installation & Usage
### Prerequisites
- Java 11+
- Apache Tomcat 10+
- MySQL Database
- Maven

### Steps to Run the Project
1. **Clone the repository**
   ```sh
   git clone https://github.com/your-repo/telemedicine-clinic.git
   cd telemedicine-clinic
   ```
2. **Configure the database**
   - Update `src/config/DatabaseConnection.java` with your MySQL credentials.
3. **Build and deploy the project**
   ```sh
   mvn clean install
   mvn tomcat7:run
   ```
4. **Access the services:**
   - SOAP: `http://localhost:8080/ws/MedicalRecord?wsdl`
   - REST: `http://localhost:8080/api/appointments`

## Contributors
- **Raja Belemdioui**

---



