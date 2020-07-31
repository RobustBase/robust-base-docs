# JDBC Drivers
---
JDBC Drivers are categorized in four types

## Type-1 Driver: JDBCD-ODBC Bridge Driver
- Type-1 Driver acts as bridge between JDBC and other database connectivity mechanism like ODBC.
- Type-1 Driver example is Sun JDBC-ODBC bridge driver(in sun.jdbc.odbc package)
- This driver converts JDBC calls into ODBC calls and redirects the request to ODBC driver
- ODBC driver uses SP(Stored Procedure) APIs to make DBMS specific call

![Type 1 JDBC Driver](https://docs.google.com/drawings/d/1Le9ajun9PPHVF1b8fN1DZkGWF_xT-h_N2MExlDJDto0/export/png)

## Advantages
- Single driver implementation for different databases
- Vendor independent driver
- Supports all databases supported by the ODBC driver

## Disadvantages
- Slow execution speed due to large number of calls and translations
- Fully dependent on ODBC driver
- ODBC client library should be installed at client machine

## Note
- The JDBC-ODBC Bridge has been removed in JDBC 4.2
- Type-1 driver should not be used in production environment and with auto-installation applications likes Applets.

## Type-2 Driver: Java to Native API(Partly Java Driver)
- Type-2 Driver converts JDBC calls into database vendor specific native call using JNI
- These database specific calls then dispatched to db specific native libraries
- Native libraries sends request to db server by native protocol
- Example: Weblogic Type-2 Driver by BEA Weblogic

![Type 2 JDBC Driver](https://docs.google.com/drawings/d/1ETmHjQpP4IcBgJZR-4Qf2ivLoDZF93Z6k6M6JBCojPw/export/png)
