# JDBC Drivers
---
JDBC Drivers are categorized in four types

## Type-1 Driver: JDBCD-ODBC Bridge Driver
- Type-1 Driver acts as bridge between JDBC and other database connectivity mechanism like ODBC.
- Type-1 Driver example is Sun JDBC-ODBC bridge driver(in sun.jdbc.odbc package)
- This driver converts JDBC calls into ODBC calls and redirects the request to ODBC driver
- ODBC driver uses SP(Stored Procedure) APIs to make DBMS specific call

![Type 1 JDBC Driver](https://docs.google.com/drawings/d/1Le9ajun9PPHVF1b8fN1DZkGWF_xT-h_N2MExlDJDto0/export/png)

### Advantages
- Single driver implementation for different databases
- Vendor independent driver
- Supports all databases supported by the ODBC driver

### Disadvantages
- Slow execution speed due to large number of calls and translations
- Fully dependent on ODBC driver
- ODBC client library should be installed at client machine

### Note
- The JDBC-ODBC Bridge has been removed in JDBC 4.2
- Type-1 driver should not be used in production environment and with auto-installation applications likes Applets.

## Type-2 Driver: Java to Native API(Partly Java Driver)
- Type-2 Driver converts JDBC calls into database vendor specific native call using JNI
- These database specific calls then dispatched to db specific native libraries
- Native libraries sends request to db server by native protocol
- Example: Weblogic Type-2 Driver by BEA Weblogic

![Type 2 JDBC Driver](https://docs.google.com/drawings/d/1ETmHjQpP4IcBgJZR-4Qf2ivLoDZF93Z6k6M6JBCojPw/export/png)

### Advantages
- Fast processing as compared to Type-1 Driver
- Contains exclusive feature provided by DB vendor and supported by JDBC specification

### Disadvantages
- Native librariesto be installed on client machine
- Executes DB specific native functions on JVM, aby bug in Type-2 driver might crash the JVM
- Increase the cost of application in case it runs on different platforms

## Type-3 Driver: Java to Network Protocol(Pure Java Driver)
- Type-3 Driver converts JDBC calls into middleware server specific calls
- Driver communicates with middleware over a socket
- Middleware converts these calls into database specific calls
- These type of drivers also known as net-protocol drivers
- Example: IDS Driver, WebLogic RMI Driver

![Type-3 Driver](https://docs.google.com/drawings/d/1Jr3Lv122T8z8KvjpWmZ33CY2cjd3enOD14qagfEYV7k/export/png)

### Advantages
- Additional features like Pool Management, performance improvement and connection availability
- It is auto downloadable so best suits for Applets
- No native library needed to be installed in client machine
- Database independent, middleware takes care of converting calls to DB specific calls
- Database details are not required at client side because it is available at middle-ware server
- Easy to switch among databases, without changing client side driver classes

### Disadvantages
- Performes task slowly because network call is involved
- Cost of middleware server is more


## Type-4 Driver: Java to Database Protocol(Pure Java Driver)
- Type-4 implements the database protocol to interact directly with a database
- This driver prepares a DBMS specific network message and then communicates with DB server over a socket
- Type-4 Driver uses DB specific proprietary protocol for communication
- Generally these type of drivers are implemented by DBMS vendors, since the protocols used are proprietary
- Example: Oracle Thin driver, WebLogic & Mysqlserver4 for MY SQL server from BEA system

![Type-4 Driver](https://docs.google.com/drawings/d/1pKWKl9KP00xIeVIiPCuI5pBWlowPATpA_IdD87QeViI/export/png)

## Advantages
- This is lightweight driver
- Auto downloadable
- No native library needed to be installed at client side
- No middleware server required

## Disadvantages
- This uses database specific proprietary protocol so it is vendor dependent
