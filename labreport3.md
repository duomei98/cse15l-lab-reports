![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)
#                                 °₊·ˈ∗♡ 《LAB REPORT 3》 ♡∗ˈ‧₊°
#                                    _Researching Commands_

*Name: Anna He*

*Date: 05/10/2023*

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

I researched 4 interesting command-line options for the `less` command. Normally, `less` displays the contents of a file without printing the entire document (as `cat` would do) and thus is a way to quickly look through a file.

## …ᘛ⁐̤ᕐᐷ 🍒 《OPTION 1: `-p`》 🍒 

`-p <pattern>`: tells `less` to start at the first occurrence of the pattern in the file (_Source:_ [Link](https://www.geeksforgeeks.org/less-command-linux-examples/))


**🍒 EXAMPLE 1:**
```
$ less -p "Result" rr172.txt
```

This command looks for the first occurrence of the word "Result" in the file `rr172.txt`. This is useful because if I was doing research on the link between pulmonary disease and smoking (or whatever this file is about) and I needed a reminder as to what the result of the experiment was, I could quickly go to it without having the scroll through the entire file.

_Output:_

![Image](https://media.discordapp.net/attachments/783745953680326656/1105974956883460148/Screen_Shot_2023-05-10_at_2.49.33_PM.png?width=1888&height=784)

**🍒 EXAMPLE 2:**
```
$ less -p "pulmonary disease" rr*.txt
```

This command looks for the first occurrence of the words "pulmonary disease" in all .txt files that begin with "rr". This is helpful if I wanted to find information related to pulmonary disease, but I don't remember actually which file I saw it in. 

_Output:_


![Image](https://media.discordapp.net/attachments/783745953680326656/1105979818941612032/Screen_Shot_2023-05-10_at_3.08.51_PM.png?width=1052&height=140)
> `Pattern Not Found (press RETURN)` means that the phrase "pulmonary disease" is not in the file. Since I typed in `rr*.txt` for the file pattern, `less -p` begins searching at rr166.txt, the first .txt file that begins with "rr"—— which does not have the phrase we're looking for. 

![Image](https://media.discordapp.net/attachments/783745953680326656/1105999861339389973/Screen_Shot_2023-05-10_at_4.28.29_PM.png?width=2052&height=872)
> Scrolling to the bottom of the file and typing `:n` allows you to go to the next page. I learned this from the website ([Link](https://flaviocopes.com/linux-command-less/#:~:text=In%20this%20case%20the%20behaviour,to%20go%20to%20the%20previous))

![Image](https://media.discordapp.net/attachments/783745953680326656/1106000424445689986/Screen_Shot_2023-05-10_at_4.30.45_PM.png?width=2120&height=668)
> I continued navigating to the next file until I found one that contained "pulmonary disease." Therefore, rr172.txt is the file we're looking for. 

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《OPTION 2: `-i`》 🍒 

`-i`: causes searches to ignore case (_Source:_ [Link](https://www.geeksforgeeks.org/less-command-linux-examples/))

**🍒 EXAMPLE 1:**
```
$ less -i -p "isopropyl alcohol" rr166.txt
```

This command looks for the first occurrence of the phrase "isopropyl alcohol" in the file `rr166.txt` regardless of case. This is useful because in many occasions when you search through a file, you do not care about the capitalization of a word, only its meaning—— for example, if I wanted to know how much isopropyl alcohol I needed to buy to complete this experiment. Having to search multiple times based on capitalization is much more tedious. 

_Output:_

![Image](https://media.discordapp.net/attachments/783745953680326656/1106066155183034418/Screen_Shot_2023-05-10_at_8.51.54_PM.png?width=2132&height=892)

**🍒 EXAMPLE 2:**
```
$ less -i -p "RNA" *.txt
```

Similarly, this command looks for the occurences of the word "RNA" in all .txt files. I might use this to account for different spellings of RNA (eg rna, Rna) so that I can still find the information I'm looking for without worrying about case.  

_Output:_

![Image](https://media.discordapp.net/attachments/783745953680326656/1106069831427563550/Screen_Shot_2023-05-10_at_9.06.33_PM.png?width=1956&height=868)

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《OPTION 3: `-J`》 🍒 

`-J`: displays a status column on the left side of the screen that shows the lines that matched the current search (_Source:_ [Link](https://phoenixnap.com/kb/less-command-in-linux))

**🍒 EXAMPLE 1:**
```
$ less -J -i -p "insulin" rr191.txt
```

_Output:_

![Image](https://media.discordapp.net/attachments/783745953680326656/1106074028944396298/Screen_Shot_2023-05-10_at_9.23.13_PM.png?width=2128&height=852)

This command marks the lines that match your search—— in my case, lines that contain the phrase "insulin" with any case. This is useful for future reference; I can quickly see which lines are important if I wanted to cite something about insulin. 

**🍒 EXAMPLE 2:**
```
$ less -J -p "Materials" rr*.txt
```

 _Output:_
 
 ![Image](https://media.discordapp.net/attachments/783745953680326656/1106082151792918528/Screen_Shot_2023-05-10_at_9.55.31_PM.png?width=2104&height=868)
  
 ![Image](https://media.discordapp.net/attachments/783745953680326656/1106082310165647392/Screen_Shot_2023-05-10_at_9.56.08_PM.png?width=2136&height=872)
 
This command allows you to search through all .txt files starting with "rr" and mark each "Materials" section— therefore providing a fast way to document what materials you would need if you wanted to do the experiments described. 

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 《OPTION 4: `-X`》 🍒 

`-X`: keeps content on the screen even after quitting (usually, typing 'q' immediately clears the terminal) (_Source:_ [Link](https://phoenixnap.com/kb/less-command-in-linux))

**🍒 EXAMPLE 1:**
```
$ less -X -p "Introduction" rr191.txt
```

_Output:_

![Image](https://media.discordapp.net/attachments/783745953680326656/1106078555965767711/Screen_Shot_2023-05-10_at_9.41.13_PM.png?width=2036&height=880)

This command allows you to search for something in a file and then save that result to terminal. This is helpful because it allows you to keep the information even after quitting the `less` window; normally, the terminal clears immediately as soon as you exit `less` and therefore you have to type the command again if you want to see what output you got. 

**🍒 EXAMPLE 2:**

```
$ less -X -p "Results" *.txt
```

_Output:_

![Image](https://media.discordapp.net/attachments/783745953680326656/1106085101412028486/Screen_Shot_2023-05-10_at_10.07.14_PM.png?width=1252&height=1236)

This command searches through all .txt files and prints each section containing the word "Results" to the terminal. This is very helpful because it allows you to easily keep similar information (such as the results of your experiments) together, and allows you to look at them all at once without continuously scrolling through files. It also only shows information relevant to your search, so your data is concise and easy to look at.  

---
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)

## …ᘛ⁐̤ᕐᐷ 🍒 Onto the next week! ~ ♡( •ॢ◡-ॢ)✧˖° ♡
![Image](https://i.pinimg.com/originals/62/8a/0a/628a0a38a8f0b9b9efa19492f63ea541.png)
   
![Image](https://media.discordapp.net/attachments/783745953680326656/1094753603274686584/IMG_4813.png?width=2520&height=132)
