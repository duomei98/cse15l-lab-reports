![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)
#                                 °₊·ˈ∗♡ 《LAB REPORT 5》 ♡∗ˈ‧₊°

*Name: Anna He*

*Date: 06/05/2023*

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《Part 1》 🍒 Debugging Scenario

*🍒 Model EdStem Report*

Hi, I'm working on my personal Macbook, in the VSCode terminal. I'm trying to write a script for the autograder and I'm not sure why I'm getting this error? 

> Here is a screenshot. 
![Image](https://media.discordapp.net/attachments/783745953680326656/1115545026018152498/Screen_Shot_2023-06-06_at_12.37.33_AM.png?width=1802&height=1236)

> Here is my code for the Autograder.
![Image](https://media.discordapp.net/attachments/783745953680326656/1115547305358147594/Screen_Shot_2023-06-06_at_12.46.38_AM.png?width=1996&height=1236)

> And here is my current working directory. 
![Image](https://media.discordapp.net/attachments/783745953680326656/1115553775176921109/Screen_Shot_2023-06-06_at_1.12.20_AM.png?width=668&height=1116)

From the error it looks like there's a problem in Step 4, and running JUnit isn't working properly, because it's giving me a "ClassNotFoundException." I'm not sure why though, I made sure to copy the correct command to run Junit tests for Macs, so that's not the problem. The output I expected was the statement "Your code compiled!" printed and the grader to say "Score: 0" since I'm using a faulty submission. Any help is appreciated!!

---
*🍒 Response from TA*

Can you try looking at your current working directory? Are there any files that you are forgetting to run / move into the grading-area? Hint: the javac/java commands use the lib repository to run tests. Do you mention the lib file anywhere in your code?

---
*🍒 Response from Student*

Ohhhhh thank you so much!! I didn't think about that. I added the line `cp -r lib grading-area` to copy the respository into the grading-area before I ran grading-area, and this time I got the output I expected!! 

> Screenshot
![Image](https://media.discordapp.net/attachments/783745953680326656/1115556772640477234/Screen_Shot_2023-06-06_at_1.24.16_AM.png?width=2520&height=454)

I guess the error was in the line `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`. I never really noticed what this command was actually doing because I just used it on autopilot, so I had to do some research. But I see now that you are running a Java command where you try to run the classes that follow the pattern `*.java` and you are specifying the classpath `lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar`. When I open the lib repository, I see both `hamcrest-core-1.3.jar` and `junit-4.13.2.jar`, so not moving lib into grading-area throws an error because they can't find the class of a path that doesn't exist. 

---
*🍒 Summary:*

File: ![Link](https://github.com/ucsd-cse15l-f22/list-methods-lab3.git)

Directory Structure:

![Image](https://media.discordapp.net/attachments/783745953680326656/1115553775176921109/Screen_Shot_2023-06-06_at_1.12.20_AM.png?width=668&height=1116)

Before (for the file that has an error):
```
CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'

rm -rf student-submission # deletes the file
rm -rf grading-area       # deletes the directory 

mkdir grading-area        # creates a new directory "grading-area"

# Step 1
git clone $1 student-submission # this is a folder 
echo 'Finished cloning'

# Draw a picture/take notes on the directory structure that's set up after
# getting to this point

# Then, add here code to compile and run, and do any post-processing of the
# tests

set -e

# Step 2 

if [[ -f `find student-submission/ListExamples.java` ]] 
then 
    echo "File submitted successfully"
else 
    echo "Please make sure your file exists and is of the right format."
    exit
fi 

#Step 3

cp -r student-submission/ grading-area
cp TestListExamples.java grading-area

#Step 4

set +e
cd grading-area
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java

if [[ $? == 0 ]]
then
    echo "Your code compiled!"
else 
    echo "Your code did not compile. Please check it again."
fi

# Step 5

java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples >out.txt
# redirects error and output into out.txt

if [[ `grep -i 'OK' out.txt` == 'OK'* ]]
then    
    echo "Score: 100"
elif [[ `grep 'FAILURES!!!' out.txt` == 'FAILURES'* ]]
then 
    echo "Score: 0"
fi
```
Line that triggers bug:
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
```
Edit needed: Add the line `cp -r lib grading-area` before the line that triggers the bug. 

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《PART 2》 🍒 Reflection

I really enjoyed lab, so thanks for the great experience! I think something I learned that I didn't know before was that CS is so so so much easier (and more fun!) when you work with other people. Like it makes sense, but I've never liked asking for help but that was actually just hurting myself. The lab setup where you work on problems with a peer was really useful and conducive to learning, both for cs15 and cs12 (we discussed PAs during breaks). And I increased the amount of friends I had in CS from 1 to 4, which is a 300% increase!

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 Congrats! You've done it! The final labreport!! ~ ♡( •ॢ◡-ॢ)✧˖° ♡
![Image](https://i.pinimg.com/originals/62/8a/0a/628a0a38a8f0b9b9efa19492f63ea541.png)
   
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

