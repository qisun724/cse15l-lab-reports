# **LAB REPORT 2**
## **Part 1 - Creating a StringServer**
![Image](StringServerCode.png)

## Examples from using /add-message?s=<String>
![Image](ex1.png)
* After each use of /add-message in the above screenshot, the **main** method is called first. Then the **start** method in the Server.java(code not shown; gotten from wavelet repository from lab2) is called. I am not sure if there are more methods being called in Server.java since I am still unfamiliar with its code. Looking at the **StringHandler** class in StringServer.java, I think that everytime I use /add-message, the **handleRequest** method will also be called to actually display what we can see on the webpage.
* When the **main** method is run, it takes a port number as its argument given in the command line. Then the **start** method is called given the port number from the command line and a **StringHandler** object. I have a field in the **StringHandler** class that is an **ArrayList** of type **String** called strs, which stores the incoming request that comes after `/add-message?s=`. There is also a variable of type **String** called result which is used to keep track of what gets displayed on the webpage. For the **handleRequest** method in the **StringHandler** class, it takes in an object of type **URI** as its argument.
* The **ArrayList** strs will be changed where a **String** is added to it everytime after there is an incoming request using /add-message. The **String** result will also be changed after every incoming request becuase a new String would be added to **ArrayList** strs as it loops through it and turn it into a formatted **String** to be displayed on the webpage. I think everything else stays the same becuase the arguments that they take in doesn't really change. For example, the **start** method is still called using the port number and **StringHandler** object.\


![Image](ex2.png)
* The methods that are being called are the same as described previously for the first example of screenshot. The relevant arguments for those methods also stay the same. The values of the **ArrayList** strs and **String** result field of the **StringServer** class will also stay the same; they store Strings.
* The **ArrayList** strs and the **String** result behave the same as described in previously, but I tried giving it some "unusal" incoming requests to see if anything different will happen. Even after different values like integers and strings that are URLs(https://), the code still behaved like how it should by displaying every incoming request. However, I did notice different and unusal/unexpected outputs for two incoming requests using /add-message. For the first one, if we give it a string input that starts with `#`, it will throw ArrayIndexOutOfBoundsException: Index 1 out of bounds for length 1. The second request is that if we give it a string input that contains`%` or `^`, it will throw URISyntaxException.\




## **Part 2 - Debugging from Lab 3**
Failure-inducing input for buggy program
```
@Test
public void testAverageWithoutLowest(){
  double[] input = {3.52, 10.3, 5.84, 3.52, 21.2};
  assertEquals(10.215, ArrayExamples.averageWithoutLowest(input), 0.1);
}
```

Input that doesn't induce a failure
```
@Test
public void testAverageWithoutLowest(){
  double[] input = {10.2, 32.4, 11.1, 10.1, 23.4, 23.2};
  assertEquals(20.06, ArrayExamples.averageWithoutLowest(input), 0.1);
}
```

Tests ran & Symptom 
```
@Test
public void testAverageWithoutLowest(){
  double[] input1 = {};
  double[] input2 = {4.0};
  double[] input3 = {3.52, 10.3, 5.84, 3.52, 21.2};
  double[] input4 = {10.2, 32.4, 11.1, 10.1, 23.4, 23.2};
  assertEquals(0, ArrayExamples.averageWithoutLowest(input1), 0);
  assertEquals(0, ArrayExamples.averageWithoutLowest(input2), 0);
  assertEquals(10.215, ArrayExamples.averageWithoutLowest(input3), 0.1);
  assertEquals(20.06, ArrayExamples.averageWithoutLowest(input4), 0.1);

```
image




The Bug, Before vs After
```
static double averageWithoutLowest(double[] arr) {
  if(arr.length < 2) { return 0.0; }
  double lowest = arr[0];
  for(double num: arr) {
    if(num < lowest) { lowest = num; }
  }
  double sum = 0;
  for(double num: arr) {
    if(num != lowest) { sum += num; }
  }
  return sum / (arr.length - 1);
 }
```

```
static double averageWithoutLowest(double[] arr) {
  if(arr.length < 2) { return 0.0; }
  double lowest = arr[0];
  double sum = 0;
  for(double num: arr) {
    sum += num;
    if(num < lowest) { lowest = num; }
  }
  return (sum-lowest) / (arr.length - 1);
}
```

## **Part 3**
Something very useful that I learned from my peers during lab 2 was using the up arrow on the keyboard as a shortcut to go to previously commands ran on in the terminal. This saved me so much time because I don't have to go back to look to copy and paste the commands for compiling and executing the code. 

Another thing I learned was from lab 3 when I tried using **assertEquals** to compare **double** but getting errors saying the method is deprecated. That was when I found out that there is an **assertEquals** method with three parameters where the first two are the same. The third parameter is delta, and I learned that it is for us to put the difference we want between the expected and actual in order to determine whether it passes or fails. We need to do this because of the problem with precision when working with doubles. For example, we would put delta as 0.1 to let the test pass as long as the difference between the expected and actual is 0.1 or below.
