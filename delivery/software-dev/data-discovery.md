# Data Discovery

Early in a product or feature, we often know we'll need to acquire data from some existing source. We need to know what data exists, where, and how to get to it.

## Artifacts

See [artifact examples](data-discovery-artifact-example.md) for how you might capture this information in a markdown file.

### Data Flows (optional)

Depending on the complexity of the system and number of sources, this can be a visual diagram, or simply a few text bullets. For few sources, skipping data flows is a valid option.

### Data Mapping

List out each data element, and where it comes from. Organize as a table for each conceptual entity if there are many data elements.

Information to capture:

* Element: label we use in the context of our system.
* Data Type: the format of the data (Text/Number/Date/PDF/Image/etc). Be as precise as makes sense - `number` may be sufficint for many use cases but `float` or `double` may be important in other cases.
* Source System: where the external data lives using a meaningful system name. Could be a system, file store location, etc.
* Source Table/File/Field: where in the system does the element live? Could be a database table and column, or a CSV file and column number, etc.
* Notes: any useful additional info such as calculation logic or any interesting features.

#### Example Data Mapping

| Element | Data Type | Source System | Source Table/File/Field | Notes |
| --- | --- | --- | --- | --- |
| First Name | Text | CustomerProfile | customer.fname | |
| Last Name | Text | CustomerProfile | customer.lname | |
| Account Balance | Number | Orders, Payments | (calculated) | Total of all order values minus all payment values |


### Data Source Profile

The following basic table is filled out for each data source. This helps us capture how to get access to data. 

| Data Source Name | Descriptive Name of Data Source recognizable to stakeholders |
| --- | --- |
| Interface | (database, REST API, SOAP/WSDL API, flat file, etc.) |
| Development | Notes on how to develop against this interface - how to mock, use a sandbox version, etc. |
| Authentication | High-level notes on how system-system authentication works |
| Points of Contact | System owner, technical/troubleshooting, data SMEs, other PoCs |
| Data Quality | Notes on timeliness, quality, integrity of data |

