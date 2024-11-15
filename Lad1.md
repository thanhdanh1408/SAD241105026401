# Payroll System Analysis and Design

## 1. Architectural Analysis

### 1.1. Proposed Architecture
The recommended architecture for the Payroll System is a **3-tier Architecture**. This model divides the system into three main layers, which ensures scalability, maintainability, and meets the business requirements of the system.

- **Presentation Layer**:
  - The user interface that employees and administrators interact with, allowing input and data queries.
  - Supports tasks like submitting timecards, selecting payment methods, and viewing reports.

- **Business Logic Layer**:
  - Responsible for executing the core business logic of the system, including:
    - Automatic payroll calculations.
    - Timecard processing and order management.
    - Managing and verifying payment information.
  - Implemented as services on a central server, handling scheduled payroll runs.

- **Data Access Layer**:
  - Manages the storage and retrieval of employee data, payroll information, timecards, and other related data in a DB2 database.
  - Communicates with the existing project management database without disrupting the current system.

### 1.2. Rationale for Architectural Choice
- **Scalability**:  
  - The 3-tier architecture allows each layer to be scaled independently, enabling interface upgrades without affecting the business logic or database layers.
  
- **Maintainability**:  
  - Clear separation of interface, business logic, and data access enables easier development and maintenance.

- **Security Requirements**:  
  - By restricting access to the Business Logic and Data Access layers, sensitive data is protected, ensuring only authorized users can access necessary information.

- **System Integration**:  
  - The data access layer is designed to interact with the legacy DB2 database, preserving the current system and saving on costs.

### 1.3. Explanation of Each Component
1. **Client Layer**:
   - The interface where employees and administrators interact with the system.
   - Examples: Employees submit timecards, select payment methods; administrators add new employees or generate reports.

2. **Application Layer**:
   - Manages processes such as:
     - Calculating wages based on working hours, orders, and employee type.
     - Validating conditions for timecards and payment methods.
   - Executes automated payroll schedules to ensure timely payments.

3. **Database Layer**:
   - Responsible for storing and managing data.
   - Ensures requirements such as:
     - Retrieving employee and project data from the DB2 database.
     - Storing payroll data, timecards, and reports.

### 1.4. Package Diagram
The package diagram below shows the main components and their relationships:
![Diagram](https://www.planttext.com/api/plantuml/png/V5D1JiCm4Bpx5LOlmA52ujW3AhG7aAY42eZprjbI2ySEkqwh2FLb77WINy19ar8NDpvwPcTdP-sVh-ynUo1VvaOKeDxX3ULWOZHQBn-WGXh8Jo73KGQOvU25aUIzzKXBKDY1kwDjKVfddQC2oiul3X16Wye_GfK7tHdwbOlnZnAfccFXoBVtMx4LVuPkYi9e1LuxctGLbCaP8oTWL6aQNcnDjG3UkP9CzHfKENAm9po10TAOzL0cBiyrSsYoDtlWfGj0pi06ZNhYs0l36fCfhS7eBEWVWTkZIMl5a-85EONCBItsx-nIKvxQGfps53miW34PzVJsIdQ4excy8woXg2kX3t6k3u6csvcSusvJlD85omNw3QBTjK6MO3FPEcBnxzaDXzSdjZwI9P-iIEwcjoALTrUGxDzKnI6DGWYGNMv8UnHf3ycg9b2HjD335sEqMVsTVm400F__0m00)

