# Data Discovery: Customer Balances

## Data Flows 

* Customer Balance App <- CustomerProfile
* Customer Balance App <- Data Warehouse <- ShoppingCart

## Data Mapping

| Element | Data Type | Source System | Source Table/File/Field | Notes |
| --- | --- | --- | --- | --- |
| First Name | Text | CustomerProfile | customer.fname | |
| Last Name | Text | CustomerProfile | customer.lname | |
| Account Balance | Number | ShoppingCart | (calculated) | Total of all order values minus all payment values |

## Data Source Profiles

| Data Source Name | CustomerProfile System (CPS) |
| --- | --- |
| Interface | database/SQL in AWS Aurora (PGSQL) |
| Development | Have to create custom mock DB |
| Authentication | System-generated username/password credentials injected in app in pipeline |
| Points of Contact | Joe Doe, System Owner; Sara Sims, Data Architect/DBA |
| Data Quality | name fields are required and generally 100% present |

| Data Source Name | Data Warehouse/ShoppingCart |
| --- | --- |
| Interface | Elastcsearch web JSON API |
| Development | sandbox exists at dev.enterprisedw.thisorg.gov |
| Authentication | requires API key manually issued |
| Points of Contact | Jane Jackson, System Architect |
| Data Quality | hit or miss depending on which legacy ordering system it comes from |
