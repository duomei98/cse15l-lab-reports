![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)
#                                 °₊·ˈ∗♡ 《LAB REPORT 2》 ♡∗ˈ‧₊°
#                                      _Servers and Bugs_

*Name: Anna He*

*Date: 04/23/2023*

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《PART 1》 🍒 

**🍒 String Server Code:**
![Image](https://media.discordapp.net/attachments/717565547268669500/1099959946801582131/Screen_Shot_2023-04-24_at_12.28.03_AM.png?width=1828&height=1236)
My StringServer code takes in the command line arguments as a String array. If no port number is given (for example, if we type only `java StringServer` in the command line), the main method reminds you to type in a port number because our web server requires a port to run on. Otherwise, it takes the port number and creates a server with that port and using our Handler, which I will discuss in further detail below. 
* The method that is called in my code is the main method in line 17.
* The relevant argument to this method is an `int` port number. For example, one command line input is 
```
javac StringServer.java
java StringServer 4567
```
It creates a url `http://localhost:4567` that represents my StringServer.
* I wrote my code in a way that didn't use fields.

**🍒 Using `/add-message`**

1. 
![Image](https://media.discordapp.net/attachments/783745953680326656/1099960789500170330/Screen_Shot_2023-04-24_at_12.31.22_AM.png?width=1856&height=512)

2.
![Image](https://media.discordapp.net/attachments/783745953680326656/1100131424453017681/Screen_Shot_2023-04-24_at_11.49.24_AM.png?width=1912&height=524)
> _Note: the urls I entered were `http://localhost:4567/add-message?s=two birds` and `http://localhost:4567/add-message?s=on a wire`. According to my research, because spaces in urls are not allowed they were replaced with `%20`_

I decided to use a helper class Handler, modeling my code off the NumberServer code we worked with in lab. I modified the `handleRequest()` method to still accept an url as a paramater but now initialize a variable `str` that is an empty string. Then, I take the query of the url, which is defined as anything after the `?` (such as `"s=two birds"` in **1**), and concatenate the string after `=` in the url (such as `"two birds"`) to my variable `str`. Finally, I use the `format()` method to display the updated string in my web server. 
* The method in my code that was called was the `handleRequest()` method in line 6.
* The relevant argument to this method is the url of the webserver shown in the two screenshots labeled **1** and **2**. 
* I did not use fields in my code. 

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《PART 2》 🍒 

I will be addressing the bug in the `reverseInPlace()` method in the file ArrayExamples.java.

**🍒 Failure Inducing Input: Test and Symptom** 

* A failure inducing input includes any input array that has unique values for each index, such as the test I wrote below.
```
  @Test
  public void testReverseInPlaceEvenArray() {
    int[] input2 = {1, 2};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{2, 1}, input2);
  }
```
_Symptom:_ 

Here is the output of running this test. The failed test is the test I wrote above: 
![Image](https://media.discordapp.net/attachments/783745953680326656/1100205705056768030/Screen_Shot_2023-04-24_at_4.44.34_PM.png?width=2520&height=1150)

**🍒 Non-Failure Inducing Input: Test and Symptom** 

* An input that doesn't induce a failure is any input that has the same value for corresponding indexes `i` and `input.length - i - 1`, aka indexes the same distance from the front and back of the array.
```
  @Test
  public void testReverseInPlaceDoesNotFail() {
    int[] input1 = {1, 1};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{1,1}, input1);
  }
```
_Symptom:_

Here is the output of running this test. Evidently, all tests passed: 

![Image](https://media.discordapp.net/attachments/783745953680326656/1100135465081909298/Screen_Shot_2023-04-24_at_12.05.29_PM.png?width=2244&height=576)

**🍒 Bugs, Fix, and Explanation** 

_Before (original):_
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
  ```
_After (fixed):_
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < (arr.length / 2); i += 1) {
      int placeholder = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = placeholder;
    }
  }
```
_Explanation of bug:_

The main issue in the original code is that it creates a mirrored list, aka a list where all indexes the same distance from the front and back of the array, are equal, rather than a reversed list. When you update the value of `arr[i]` to reverse the array, you lose the original value, meaning that you can’t actually reverse the second half of the array. For our `input2 {1,2}`, when `i = 0` our code updates `arr[0]` to `arr[1]`, changing the array to `{2,2}`. Then, for `i = 1`, because the original value, 1, was lost, `arr[1]` updates to the incorrect value of 2.

Our revision fixes this bug by storing the original array value in a `placeholder` variable, and also changing the iteration length to only half the array, so that when you iterate through the first half of the array, you are actually reversing the array values. Let's revisit the the input `{1, 2}`. Now, for the iteration `i = 0`, the `placeholder` variable gets the value 1, and `arr[0]`is updated to the value of index 1, which is 2. `arr[1]` is then updated to our `placeholder` value of 1. The loop ends after one iteration, which is half the length of the array, and we've successfully reversed the array. 

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《Part 3》 🍒 

Something I learned in week 2 of lab that I didn't learn before was how to write a web server and change what words / numbers are displayed using methods that I can write in the class Handler. I learned that the Handler class can use methods from the URLHandler class such as `getQuery()` and `getPath()` which returns the respective parts of the url, which you can then use to update what you see in the your webserver. 


## …ᘛ⁐̤ᕐᐷ 🍒 That was actually kinda fun, wasn't it? Keep up the good work! ~ ♡( •ॢ◡-ॢ)✧˖° ♡
![Image](https://i.pinimg.com/originals/62/8a/0a/628a0a38a8f0b9b9efa19492f63ea541.png)
   
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)
