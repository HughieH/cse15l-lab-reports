# Lab Report 2
> Written by Hou Wai Wan for CSE 15L Winter 2023

## Part 1 - Building a web server for string concatenation 

**StringServer Code**

![image](images/Lab02-code_string_server.png)

**Usage of the add-message path - Example 1**

![image](images/Lab02-example1.png)

Which methods in your code are called?
In example 1, the add-message path requests the server to add a String from the path into the existing String "input". This is done by concatenation
via the "handleRequest" method. The handleRequest method only takes in one argument, a URI object called url in the method. 
What are the relevant arguments to those methods, and the values of any relevant fields of the class?
How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.

**Usage of the add-message path - Example 2**

![image](images/Lab02-example2.png)

