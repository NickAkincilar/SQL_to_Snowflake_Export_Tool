# WowMaker | SQL to Snowflake Export Utility




Windows export utility to automatically transfer entire set of tables from Microsoft SQL, Oracle or MySQL database servers to Snowflake. it will create Schema, Tables & transfer data with proper data type mapping and conversions for date & binary formats.
- **12/20/2020 Added PostGres as Source (Requires ODBC Driver found [here](https://www.postgresql.org/ftp/odbc/versions/msi/)**)
- **12/18/2020 Added Proxy Server option for Snowflake**
- **12/2/2020 Fixed Date Formatting issues.**

<BR><BR>

**App requires Snowflake_ODBC_driver Win64 to be installed on the machine before it can run properly.**

[1- Download SQL_to_Snowflake Installer](https://github.com/NickAkincilar/SQL_to_Snowflake_Export_Tool/raw/main/MsSQL_To_Snowflake.zip)

2- Unzip & install using Setup.exe

[3- Download & Install Snowflake Win64 ODBC Driver](https://sfc-repo.snowflakecomputing.com/odbc/win64/latest/index.html)

[4- (optional for Oracle) Download & Install Oracle OLEDB 64-bit Driver)](https://www.oracle.com/database/technologies/odac-downloads.html)

This utility will automatically move tables (in full) from a source database (MsSQL or Oracle) to Snowflake. Just select a list of tables from source db and point to an existing Snowflake account & a database with proper user cridentials to start transfering schemas, tables & data.



The tool will do the following for each table:
- Generate a DDL & Create the table in Snowflake.
- Auto map proper datatypes.
- Perform date type conversion
- if **EXPORT DATA** is checked (checked by default)
  - Export the data into a temp folder as flat files broken in to chunks (10MB - 100MB).
  - Create an internal stage in the target Snowflake database & Upload the files
  - Copy the uploaded files into the proper table in snowflake.

<br><br>

<strong>This product is a personal project & provided as is without any warranty. 
This application is not associated with Snowflake Inc. & not a supported product. Please use it at your own risk.</strong>

<br>
<br>

# Export Microsoft SQL
![Image of SQL to Snowflake tool](https://raw.githubusercontent.com/NickAkincilar/SQL_to_Snowflake_Export_Tool/main/SQL_2_Snowflake_Screenshot_S.png)

<br>
<br>

# Export Oracle

![Image of Oracle to Snowflake tool](https://raw.githubusercontent.com/NickAkincilar/SQL_to_Snowflake_Export_Tool/main/SQL_2_Snowflake_Screenshot_O.png)

<br>
<br>

# Export MySQL

![Image of Oracle to Snowflake tool](https://raw.githubusercontent.com/NickAkincilar/SQL_to_Snowflake_Export_Tool/main/SQL_2_Snowflake_Screenshot_MySQL.png)



<br><br>

# Version History

- <strong>12/02/2020 - Fixed date formatting issues</strong>

- <strong>11/30/2020 - Updated V9 - Added MySQL Schema & Data Export option (beta)</strong>
 
- <strong>11/23/2020 - Updated V8 - Added ORACLE Schema & Data Export option (beta)</strong>
  - Extraction Performance improvements for larger datasets.
  - Modified RECORD_SEPERATOR to HEX 0x02 to reduce export file size.
- <strong>11/22/2020 - Updated V7 with following changes</strong>
  - Extraction Performance improvements for larger datasets.

- <strong>11/21/2020 - Updated V6 with following changes</strong>
  - Added Windows Authentication support for SQL connection
  - Added max file size option for exporting chucks for large table exports (10, 25, 50, 75 & 100 MB)
  - Added Option to Enable/Disable client side file compression (gzip) prior to uploading to Snowflake
  - Enhanced logic to reduce redundant SQL create schema commands.
  - Fixed an issue with Column names with spaces.
  - Fixed an issue displaying status for tables with 0 records
  
  
