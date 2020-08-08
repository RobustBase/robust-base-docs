# JDBC Hello World program
---
This JDBC Hello World program illustrate the very basic steps to connect to a database and fetch data from an already existing table.

This example:
- was compiled and ran using JDK 8.
- uses h2 Database ↑ as data source.
- fetches data from LEARN_JDBC table. (see how to create table ↑ and insert data ↑ into it.)

```
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
 
/**
 * This class contains very basic example of HelloWorld JDBC program, that
 * fetches all records from a existing table and prints the row by row on the console.
 * 
 * This example uses h2 database as data source.
 * 
 */
public class HelloWorldJDBC {
	public static void main(String[] args) {
		Connection con = null;
		Statement stmt = null;
		ResultSet rs = null;
		try {
			// Loading the driver class
			Class.forName("org.h2.Driver");
			// Establishing the connection with data source
			con = DriverManager.getConnection("jdbc:h2:~/test", "sa", "");
			// Creating statement
			stmt = con.createStatement();
			// Performing operation
			rs = stmt.executeQuery("SELECT * FROM LEARN_JDBC");
			while (rs.next()) {
				System.out.print(rs.getInt(1));
				System.out.print(" ");
				System.out.println(rs.getString(2));
			}
		} catch (ClassNotFoundException e) {			
			e.printStackTrace();
		} catch (SQLException e) {			
			e.printStackTrace();
		} finally {
			if (rs != null) {
				try {
					rs.close();
				} catch (SQLException e) {
					e.printStackTrace();
				}
			}
			if (stmt != null) {
				try {
					stmt.close();
				} catch (SQLException e) {					
					e.printStackTrace();
				}
			}
			if (con != null) {
				try {
					con.close();
				} catch (SQLException e) {					
					e.printStackTrace();
				}
			}
		}
	}
}
```
