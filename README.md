# Healthcare Patient Management System

## Emergency Access Sequence Diagram

```mermaid
sequenceDiagram
    participant Doctor
    participant MobileApp
    participant APIGateway
    participant AuthService
    participant EmergencyAccessService
    participant MedicalRecordsService
    participant PatientDB

    Doctor->>MobileApp: Login & Emergency Access Request
    MobileApp->>APIGateway: POST /emergency-access
    APIGateway->>AuthService: Validate JWT / Role
    AuthService-->>APIGateway: OK
    APIGateway->>EmergencyAccessService: Forward Emergency Request
    EmergencyAccessService->>MedicalRecordsService: Fetch Critical Data
    MedicalRecordsService->>PatientDB: Query Allergies, Blood Type, Medications
    PatientDB-->>MedicalRecordsService: Return Critical Data
    MedicalRecordsService-->>EmergencyAccessService: Data Retrieved
    EmergencyAccessService-->>APIGateway: Return Data
    APIGateway-->>MobileApp: Response with Emergency Data
    MobileApp-->>Doctor: Display Critical Patient Info
    EmergencyAccessService->>AuthService: Log Emergency Access
