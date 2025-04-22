//pgm-8

<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
pageEncoding="ISO-8859-1"%>
<html>
<head>
<title>Sample Order Form</title>
</head>
<body>
<h2>Sample Order Form</h2>
<form method="post" action="./final.html">
<label for="productName">Product Name:</label>
<input type="text" id="productName" name="productName" required>
<br>
<label for="quantity">Quantity:</label>
<input type="number" id="quantity" name="quantity" required>
<br>
<label for="customerName">Your Name:</label>
<input type="text" id="customerName" name="customerName" required>
<br>
<label for="email">Your Email:</label>
<input type="email" id="email" name="email" required>
<br>
<input type="submit" value="Submit Order">
</form>
</body>
</html>
final.html
<!DOCTYPE html>
<html>
<head>
<meta charset=
"ISO-8859-1">
<title>Insert title here</title>
</head>
<body>
<p>Order placed</p>
</body>
</html>

//pgm-7

import java.sql.*;
public class Database {
public static void main(String[] args) {
try{
Class.forName("com.mysql.cj.jdbc.Driver");
System.out.println("Driver loaded successfully");
Connection con=DriverManager.getConnection("jdbc:mysql:"
+ "//localhost:3306/student","root","root@123");
System.out.println("Connection established sucessfully"+con);
Statement stmt=con.createStatement();
stmt.executeUpdate("insert into student (Name, USN, Sem) "
+ "values ('Kennedy','4VV21CS001',3)");
ResultSet rs=stmt.executeQuery("select * from student");
System.out.println("Name \tUSN \t\tSem");
while(rs.next())
System.out.println(rs.getString(1)+"\t"+
rs.getString(2)+"\t"+rs.getInt(3));
con.close();
}
catch(Exception e) {
System.out.println(e);
}
}
}
