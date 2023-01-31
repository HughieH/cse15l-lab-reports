# Lab Report 2
> Written by Hou Wai Wan for CSE 15L Winter 2023

## Part 1 - Building a web server for string concatenation 

**StringServer Code**

![image](images/Lab02-code_string_server.png)

**Usage of the add-message path - Example 1**

![image](images/Lab02-example1.png)

> In example 1, the add-message path requests the server to add a String from the path into the existing String "input". This is done by concatenation
via the "handleRequest" method. The handleRequest method only takes in one argument, a URI object named "url". The method itself initializes a field String variable
"input" with the value of an empty string. An array of String objects is also used to split the value of "s" in the url path into the string value to be concatenated
onto the input. If the request for add-message is valid, the "input" field is updated via concatenation with a new line and the string from the path. 

> In the case of example 1, the string "hello" is the sole input. As this is the first request however, no concatenation is needed and the input field is just replaced by the "hello" string. This is done through an if conditional statement in the "handleRequest" method.

**Usage of the add-message path - Example 2**

![image](images/Lab02-example2.png)

> In example 2, the "handleRequest" is called 3 times after the initial request for adding the string "hello". The same "add-message" path is called 3 times
consecutively with the values of "bye", "try", and "pie". These are concatenated with a newline onto the existing field "input". As in example 1, the only arguments 
used for the "handleRequest" method is just the path URL. Instead of the initial if conditional being executed, the code defined in the else part of the conditional 
is executed. This is because the field "input" is no longer an empty string.

## Part 2 - JUnit bug testing

For the file ArrayTests.java:

**Failure inducing input code:**
```
  @Test
  public void testReverseInPlace2() {
    int[] input1 = {1, 2, 3, 4, 5};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{5, 4, 3, 2, 1}, input1);
  }
```
> Output was [5, 4, 3, 4, 5]

**Input that doesn't induce failure:**
```
> @Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```
> Output was [3]

The symptom for the failure inducing output was that at index 3, the value of 2 was expected but instead the value of 4 was outputted.

## Part 3 - What I learned from Week 2 and Week 3

One thing I found interesting was the deployment of web servers on a computer that was not operated locally by me. I learnt about the process of remotely
accessing a machine over a network via the use of SSH in Git Bash. This allows me to directly interact with and issue commands on a remote computer and do
things like hosting a web server that processes requests and sends a response on a specific URL path. I believe this is one of the fundamental aspects
of how modern web applications work over the internet.
