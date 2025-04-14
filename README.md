# readme
```mermaid
sequenceDiagram
    participant HR Manager
    participant Payroll System
    participant Attendance System
    participant Bank API
    participant Employee

    HR Manager->>Payroll System: Schedule monthly payroll
    Payroll System->>Attendance System: Fetch attendance data
    Attendance System-->>Payroll System: Return attendance data
    Payroll System->>Payroll System: Calculate salary, deductions, etc.
    Payroll System->>Bank API: Send payment requests
    Bank API-->>Payroll System: Confirm payment success
    Payroll System->>Employee: Notify salary disbursed
    Payroll System->>HR Manager: Send payroll report
```
## 🔄 Inventory Stock Alert Sequence Diagram

```mermaid
sequenceDiagram
    participant Inventory System
    participant Notification Service
    participant Inventory Manager

    Inventory System ->> Inventory System: Monitor stock levels
    Inventory System ->> Inventory System: Detect low stock condition
    Inventory System ->> Notification Service: Trigger alert
    Notification Service ->> Inventory Manager: Send low stock alert
    Inventory Manager ->> Inventory System: View stock report
    Inventory Manager ->> Inventory System: Create new purchase order (optional)
