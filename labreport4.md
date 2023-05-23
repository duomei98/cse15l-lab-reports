![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)
#                                 °₊·ˈ∗♡ 《LAB REPORT 4》 ♡∗ˈ‧₊°

*Name: Anna He*

*Date: 05/22/2023*

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《STEP 4》 🍒 Log into ieng6

![Image](https://media.discordapp.net/attachments/783745953680326656/1110370061035778108/Screen_Shot_2023-05-22_at_5.54.06_PM.png?width=1984&height=740)

*Keys Pressed:*

- ssh cs15lsp23pl@ieng6.ucsd.edu 
Since I had already gone through the steps of generating SSH keys for ieng6, I didn't have to enter my password and logged in quickly. 

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《STEP 5》 🍒 Clone your fork of the repository from your GitHub account 

![Image](https://media.discordapp.net/attachments/783745953680326656/1110415764873281536/Screen_Shot_2023-05-22_at_8.55.44_PM.png?width=2176&height=452)

*Keys Pressed:*

- git clone git@github.com:duomei98/lab7.git
Here, I clone the directory using the ssh url to access lab7. 

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《STEP 6》 🍒 Run the tests, demonstrating that they fail 

![Image](https://media.discordapp.net/attachments/783745953680326656/1110417527990923334/Screen_Shot_2023-05-22_at_9.02.46_PM.png?width=2520&height=658)

*Keys Pressed:*

- `<up>``<up>``<up>``<up>``<up>``<up>``<up>``<up>``<up>``<up>``<up>``<enter>`
I had to press up a lot until I found the command `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` in my history, but it was still much easier than retyping the whole thing.
- `<up>``<up>``<up>``<up>``<up>``<up>``<up>``<up>``<up>``<up>``<up>``<up>``<enter>`
Once again, I searched through history until I found `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`. Now, you can clearly see that both of the tests fail. 
   
---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《STEP 7》 🍒 Edit the code file to fix the failing test

![Image](https://media.discordapp.net/attachments/783745953680326656/1110402834182176840/Screen_Shot_2023-05-22_at_8.04.21_PM.png?width=2520&height=774)

*Keys Pressed:*

- vim ListExamples.java
- /return `<enter>` nnnn
Searches for the word "return" in the file. My goal is to go to the last return in the file, so I typed n four times to go next a maximum of four times (depending on where you start on the file, you might not actually press n  all four times).
- kk e x i 2 `<esc>` :wq
Goes up two lines to the incorrect index. e goes to the end of the word, and we delete the 2 and replace it with 1 using insert mode. Then, we type `<esc>` to exit insert mode and save the file. 

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《STEP 8》 🍒 Run the tests, demonstrating that they now succeed

![Image](https://media.discordapp.net/attachments/783745953680326656/1110417368343126087/Screen_Shot_2023-05-22_at_9.01.52_PM.png?width=2520&height=406)

*Keys Pressed:*

`<up>``<up>``<up>``<up>`
I pressed up 4 times until I found the command `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` in my history.
- `<up>``<up>``<up>``<up>``<enter>`
Once again, I searched through history until I found `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`. Now, you can clearly see that the tests succeed.

---

![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《STEP 9》 🍒 Commit and push the resulting change to your Github account

![Image](https://media.discordapp.net/attachments/783745953680326656/1110418514038227044/Screen_Shot_2023-05-22_at_9.06.39_PM.png?width=2362&height=1232)

*Keys Pressed:*

- git add .
This command adds all modified and new files to prepare for commit.
- git commit -m "updated"
This command saves the changes into history with the message "updated."
- git push
Now our changes are updated into my repository!!

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 Congrats! You've done it! Onto the next week ~ ♡( •ॢ◡-ॢ)✧˖° ♡
![Image](https://i.pinimg.com/originals/62/8a/0a/628a0a38a8f0b9b9efa19492f63ea541.png)
   
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)
