# ABAP CRUD Operations Program

## Program Overview
This ABAP program provides a basic implementation of Create, Read, Update, and Delete (CRUD) operations for managing employee data stored in a custom database table (`ZEMPLOYEES`). It incorporates a user-friendly selection screen with radio buttons for operation selection and utilizes ALV (ABAP List Viewer) for enhanced data visualization.

## Key Features
1. **Create Operation**: Allows users to add new employee records.
2. **Read Operation**: Retrieves and displays all employee records using ALV.
3. **Update Operation**: Enables modifications to existing employee records based on a unique employee ID.
4. **Delete Operation**: Deletes an employee record based on a unique employee ID.

## Components
### Database Table
The custom database table `ZEMPLOYEES` is defined with the following fields:
- `EMP_ID` (Employee ID): Unique identifier for employees.
- `NAME` (Name): Full name of the employee.
- `SALARY` (Salary): Monthly salary of the employee.

### Selection Screen
The program includes a selection screen for user input:
- **Input Parameters**:
  - `P_EMPID`: Employee ID (used for all operations).
  - `P_NAME`: Employee name (used for Create and Update operations).
  - `P_SALARY`: Employee salary (used for Create and Update operations).
- **Operation Selection**:
  - Radio buttons (`rb_create`, `rb_read`, `rb_update`, `rb_delete`) for selecting the desired CRUD operation.

### Forms and Logic
- **CREATE Operation**:
  - Inserts a new record into the `ZEMPLOYEES` table with the provided details.
  - Displays a success or error message.
- **READ Operation**:
  - Retrieves all records from the `ZEMPLOYEES` table into an internal table.
  - Uses the `REUSE_ALV_GRID_DISPLAY` function to display the records in a tabular format.
- **UPDATE Operation**:
  - Finds an existing record by `EMP_ID`.
  - Updates the record with new values for `NAME` and `SALARY`.
  - Displays a success or error message.
- **DELETE Operation**:
  - Deletes the record matching the provided `EMP_ID`.
  - Displays a success or error message.

### ALV Integration
The program uses the ALV grid for displaying data in the Read operation:
- A field catalog is dynamically generated to define the structure of the ALV grid.
- The `REUSE_ALV_GRID_DISPLAY` function module is called to render the data.

## Error Handling
- Validates the selection of an operation and provides an informative message if none is selected.
- Displays error messages for database-related issues such as record not found or insert/update failures.

## Usage Instructions
1. Execute the program in the SAP GUI.
2. On the selection screen:
   - Enter the required input values.
   - Select the desired operation using the radio buttons.
   - Execute the program (F8).
3. Depending on the selected operation, the program will perform the action and display a success or error message.
4. For the Read operation, view the employee data in the ALV grid.

## Dependencies
- The program depends on the `ZEMPLOYEES` database table for CRUD operations.
- The `REUSE_ALV_GRID_DISPLAY` function module must be available in the SAP system.

