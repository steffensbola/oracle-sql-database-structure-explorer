# Oracle Data types  

### Numeric Data Types  

| Data Type Syntax | Oracle 11g                                                         | Explanation                                                                                                                                             |
|------------------|--------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| number(p,s)      | Precision can range from 1 to 38. Scale can range from -84 to 127. | Where p is the precision and s is the scale. For example, number(7,2) is a number that has 5 digits before the decimal and 2 digits after the decimal.  |
| numeric(p,s)     | Precision can range from 1 to 38.                                  | Where p is the precision and s is the scale. For example, numeric(7,2) is a number that has 5 digits before the decimal and 2 digits after the decimal. |
| float            |                                                                    |                                                                                                                                                         |
| dec(p,s)         | Precision can range from 1 to 38.                                  | Where p is the precision and s is the scale. For example, dec(3,1) is a number that has 2 digits before the decimal and 1 digit after the decimal.      |
| decimal(p,s)     | Precision can range from 1 to 38.                                  | Where p is the precision and s is the scale. For example, decimal(3,1) is a number that has 2 digits before the decimal and 1 digit after the decimal.  |
| integer          |                                                                    |                                                                                                                                                         |
| int              |                                                                    |                                                                                                                                                         |
| smallint         |                                                                    |                                                                                                                                                         |
| real             |                                                                    |                                                                                                                                                         |
| double precision |                                                                    |                                                                                                                                                         |
  

### Text  

| Data Type Syntax | Oracle 11g                                                 | Explanation                                                                            |
|------------------|------------------------------------------------------------|----------------------------------------------------------------------------------------|
| nvarchar2(size)  | Maximum size of 4000 bytes. (uNicode)                      | Where size is the number of characters to store. Variable-length NLS string.           |
| varchar2(size)   | Maximum size of 4000 bytes. Maximum size of 32KB in PLSQL. | Where size is the number of characters to store. Variable-length string.               |
| char(size)       | Maximum size of 2000 bytes.                                | Where size is the number of characters to store. Fixed-length strings. Space padded.   |
| nchar(size)      | Maximum size of 2000 bytes.                                | Where size is the number of characters to store. Fixed-length NLS string Space padded. |
| long             | Maximum size of 2GB.                                       | Variable-length strings. (backward compatible)                                         |
| raw              | Maximum size of 2000 bytes.                                | Variable-length binary strings                                                         |
| long raw         | Maximum size of 2GB.                                       | Variable-length binary strings. (backward compatible)                                  |
  

### Date  

| Data Type Syntax                                                      | Oracle 11g                                                                                                                                   | Explanation                                                                                                                                               |
|-----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| date                                                                  | A date between Jan 1, 4712 BC and Dec 31, 9999 AD.                                                                                           |                                                                                                                                                           |
| timestamp (fractional seconds precision)                              | fractional seconds precision must be a number between 0 and 9. (default is 6)                                                                | Includes year, month, day, hour, minute, and seconds. For example: timestamp(6)                                                                           |
| timestamp (fractional seconds precision) with time zone               | fractional seconds precision must be a number between 0 and 9. (default is 6)                                                                | Includes year, month, day, hour, minute, and seconds; with a time zone displacement value. For example: timestamp(5) with time zone                       |
| timestamp (fractional seconds precision) with local time zone         | fractional seconds precision must be a number between 0 and 9. (default is 6)                                                                | Includes year, month, day, hour, minute, and seconds; with a time zone expressed as the session time zone. For example: timestamp(4) with local time zone |
| interval year (year precision) to month                               | year precision is the number of digits in the year. (default is 2)                                                                           | Time period stored in years and months. For example: interval year(4) to month                                                                            |
| interval day (day precision) to second (fractional seconds precision) | day precision must be a number between 0 and 9. (default is 2) fractional seconds precision must be a number between 0 and 9. (default is 6) | Time period stored in days, hours, minutes, and seconds. For example: interval day(2) to second(6)                                                        |


### Large Object (LOB) Datatypes  

| Data Type Syntax | Oracle 11g                                                                                               | Explanation                                                                                 |
|------------------|----------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------|
| bfile            | Maximum file size of 264-1 bytes.                                                                        | File locators that point to a binary file on the server file system (outside the database). |
| blob             | Store up to (4 gigabytes -1) * (the value of the CHUNK parameter of LOB storage).                        | Stores unstructured binary large objects.                                                   |
| clob             | Store up to (4 gigabytes -1) * (the value of the CHUNK parameter of LOB storage) of character data.      | Stores single-byte and multi-byte character data.                                           |
| nclob            | Store up to (4 gigabytes -1) * (the value of the CHUNK parameter of LOB storage) of character text data. | Stores Unicode data.                                                                        |
