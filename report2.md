# **LAB REPORT 2**
## **Part 1 - Creating a StringServer**
![Image](StringServerCode.png)

![Image](ex1.png)
* After each use of /add-message in the above screenshot, the main method is called first. Then the start method is called using the port given in the command line and StringHandler() object. 
* What are the relevant arguments to those methods, and the values of any relevant fields of the class?
* How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why. 

If we give it a string input that starts with `#`, it will throw ArrayIndexOutOfBoundsException: Index 1 out of bounds for length 1

If we give it a string input that contains`%` or `^`, it will throw URISyntaxException.

![Image](ex2.png)
* Which methods in your code are called?
* What are the relevant arguments to those methods, and the values of any relevant fields of the class?
* How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.




## **Part 2**
Choose one of the bugs from lab 3
