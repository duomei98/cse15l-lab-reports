![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)
#                                 °₊·ˈ∗♡ 《LAB REPORT 1》 ♡∗ˈ‧₊°

*Name: Anna He*

*Date: 04/09/2023*

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《STEP 1》 🍒 Installing VSCode

I did not need to do this step because I already had VSCode installed from a previous class. If installed correctly, you should have something like this:

![Image](https://media.discordapp.net/attachments/783745953680326656/1094714888347201679/Screen_Shot_2023-04-09_at_1.05.36_PM.png?width=1150&height=1230)

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《STEP 2》 🍒 Remotely Connecting

1. Find your course-specific CSE15L username using the UCSD Account Look-Up ([Link](https://sdacs.ucsd.edu/~icc/index.php)). You should have a username starting with "cs15lsp23" followed by a few letters.
2. If this is your first time accessing this account, you will need to create a password as well. Use the password change tool ([Link](https://password.ucsd.edu/)) and make sure you type in your username from **Step 1** from username. 
![Image](https://media.discordapp.net/attachments/783745953680326656/1094742541611569192/Screen_Shot_2023-04-09_at_2.55.54_PM.png?width=2134&height=1228)
> Follow the instructions on screen to change your password (should send you an email). 

3. Open VSCode and open a new terminal, using keyboard shortcut *ctrl + shift + `*.
4. Type in the command `$ ssh *username*@ieng6.ucsd.edu` with "username" substituted with your user from **Step 1**. 
5. If this is your first time connecting to the server, you will likely get an authentication message looking like this:
```
⤇ ssh cs15lsp23zz@ieng6.ucsd.edu
The authenticity of host 'ieng6-202.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
Password: 
```

> Type in `yes`.
   
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
* `cd`
* `ls`
* `pwd`
* `mkdir`
* `cp`
4. On your `ssh` server, try running these specific commands: 
* `cd`
* `cd ~`
* `ls -lat`
* `ls -a`
* `ls <directory>` where <directory> is /home/linux/ieng6/cs15lsp23/cs15lsp23abc (abc is one of the other group members’ username)
* `cp /home/linux/ieng6/cs15lsp23/public/hello.txt ~/`
* `cat /home/linux/ieng6/cs15lsp23/public/hello.txt`
Example Outputs:
![Image](https://media.discordapp.net/attachments/783745953680326656/1094764311408291960/Screen_Shot_2023-04-09_at_4.22.07_PM.png?width=2520&height=384)
![Image](https://media.discordapp.net/attachments/783745953680326656/1094764510071492648/Screen_Shot_2023-04-09_at_4.23.10_PM.png?width=1612&height=432)

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 Congrats! You've done it! Onto the next week ~ ♡( •ॢ◡-ॢ)✧˖° ♡
![Image](https://i.pinimg.com/originals/62/8a/0a/628a0a38a8f0b9b9efa19492f63ea541.png)
   
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)
