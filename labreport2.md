![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)
#                                 °₊·ˈ∗♡ 《LAB REPORT 2》 ♡∗ˈ‧₊°
#                                      _Servers and Bugs_

*Name: Anna He*

*Date: 04/23/2023*

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《PART 1》 🍒 

🍒 **String Server Code:**
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

🍒 **Using `/add-message`**

1. 
![Image](https://media.discordapp.net/attachments/783745953680326656/1099960789500170330/Screen_Shot_2023-04-24_at_12.31.22_AM.png?width=1856&height=512)
2.
![Image](https://media.discordapp.net/attachments/783745953680326656/1099961059420426260/Screen_Shot_2023-04-24_at_12.32.29_AM.png?width=1996&height=568)
> _Note: the urls I entered were `http://localhost:4567/add-message?s=two birds` and `http://localhost:4567/add-message?s=on a feather`. According to my research, because spaces in urls are not allowed they were replaced with `%20`_

I decided to use a helper class Handler, modeling my code off the NumberServer code we worked with in lab. I modified the `handleRequest()` method to still accept an url as a paramter but now initialize a variable `str` that is an empty string. Then, I take the query of the url, which is defined as anything after the `?` (such as `"s=two birds"` in **1**), and concatenate the string after `=` in the url (such as `"two birds"`) to my variable `str`. Finally, I use the `format()` method to display the updated string in my web server. 
* The method in my code that was called was the `handleRequest()` method in line 6.
* The relevant argument to this method is the url of the webserver shown in the two screenshots labeled **1** and **2**. 
* I did not use fields in my code. 
---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《STEP 2》 🍒 Remotely Connecting

1. Find your course-specific CSE15L username using the UCSD Account Look-Up ([Link](https://sdacs.ucsd.edu/~icc/index.php)). You should have a username starting with "cs15lsp23" followed by a few letters.
2. If this is your first time accessing this account, you will need to create a password as well. Use the password change tool ([Link](https://password.ucsd.edu/)) and make sure you type in your username from **Step 1**.
![Image](https://media.discordapp.net/attachments/783745953680326656/1094742541611569192/Screen_Shot_2023-04-09_at_2.55.54_PM.png?width=2134&height=1228)
> Follow the instructions on screen to change your password (should send you an email). 

3. Open VSCode and open a new terminal, using keyboard shortcut *ctrl + shift + `*.
4. Type in the command `$ ssh <username>@ieng6.ucsd.edu` with "username" substituted with your user from **Step 1**. 
5. If this is your first time connecting to the server, you will likely get an authentication message looking like this:
```
⤇ ssh cs15lsp23zz@ieng6.ucsd.edu
The authenticity of host 'ieng6-202.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
Password: 
```
Type in `yes`.
   
6. You will then be prompted to type in a password. Use the password from **Step 2**. 
7. You will get something like this!! 
![Image](https://media.discordapp.net/attachments/717565547268669500/1094749809874841620/Screen_Shot_2023-04-09_at_3.24.43_PM.png?width=2476&height=864)

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《STEP 3》 🍒 Trying Some Commands

1. To see the difference between running commands on the remote server versus your personal computer, create a new terminal using *ctrl + shift + `*. 
2. This will give you something like this, where the `ssh` is the remote server and `zsh` is your personal computer.
![Image](https://media.discordapp.net/attachments/783745953680326656/1094744747375067136/Screen_Shot_2023-04-09_at_3.04.38_PM.png?width=2520&height=554)
3. Try running some commands on both servers. Examples include: 
* `cd`: the command `cd <path>` switches the current working directory to the given `<path>`
* `ls`: the command `ls <path>` stands for list and is used to list the files and folders in the given path 
* `pwd`: stands for "print working directory" and is used to display the current working directory 
* `mkdir`: allows you to create new directories (_Note: make sure you have permission from the computer you're working on, or else you may get a `permission denied` message!_)
* `cp`: the command `cp <path1> <path2>` stands for copy and is used to copy the file at `<path1>` and move it to `<path2>`. If `<path2>` does not exist, it first creates that file before proceeding as aforementioned

Example Output:
![Image](https://media.discordapp.net/attachments/783745953680326656/1094764311408291960/Screen_Shot_2023-04-09_at_4.22.07_PM.png?width=2520&height=384)
![Image](https://media.discordapp.net/attachments/783745953680326656/1094764510071492648/Screen_Shot_2023-04-09_at_4.23.10_PM.png?width=1612&height=432)

4. On your `ssh` server, try running these specific commands: 
* `cd`
* `cd ~`
* `ls -lat`
* `ls -a`
* `ls <directory>` where <directory> is /home/linux/ieng6/cs15lsp23/cs15lsp23abc (abc is one of the other group members’ username)
* `cp /home/linux/ieng6/cs15lsp23/public/hello.txt ~/`
* `cat /home/linux/ieng6/cs15lsp23/public/hello.txt`
   
---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 Congrats! You've done it! Onto the next week ~ ♡( •ॢ◡-ॢ)✧˖° ♡
![Image](https://i.pinimg.com/originals/62/8a/0a/628a0a38a8f0b9b9efa19492f63ea541.png)
   
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)
