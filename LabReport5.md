# Lab Report 5

## Bash Less Command Options
---
### The '-E' Option
#### *Example 1*
Input:
```
less -E Algarve-History.txt
```

Output:
![](https://cdn.discordapp.com/attachments/1078458930356834344/1084901179907129344/image.png)

In our input, we included the '-E' option. When running the command, the output resembles the normal 'less' command, however when we scroll to 
the end it automatically closes without pressing 'q'.

#### *Example 2*
Input:
```
less -E Algarve-Intro.txt
```

Output:
![](https://cdn.discordapp.com/attachments/1078458930356834344/1084901803214250024/image.png)

Trying the '-E' option on a different text file, we see the same output, where less automatically exists when we reach the end of the text file!

**Summary**

This means that the '-E' option is similar to the original less command, except it exits when we reach the end.

This is useful for when we need to scroll through long files so we do not need to press q to exit every time. Overall though, there is little benefit to this option.

---
### The '-n' Option
#### *Example 1*
Input:
```
less -n Algarve-History.txt
```
Output:

![](https://cdn.discordapp.com/attachments/1078458930356834344/1084903098524389476/image.png)

The output for the -n option looks very similar to the original 'less' command, except there is a slight interface change where the line numbers are gone!
There are no other changes in features and we are still required to press 'q' to exit.

Let's try this on another file to test affirm the behavior.

#### *Example 2*
Input:
```
less -n Algarve-Intro.txt
```
Output:
![](https://cdn.discordapp.com/attachments/1078458930356834344/1084906391531175986/image.png)

As expected, the behavior resembles our expectations. There is a lack of line numbers on the left-side of the screen and the rest of the interface is acting as normal.

**Summary**

The '-n option removes the line number indicators from the left-side of the screen. There are no other effects on the 'less' function.
A possible use case for this may be to reduce excess information, such as line numbers when only the file content is important.

---
### The '-p' Option
#### *Example 1*
Input:
```
less -p bishop Algarve-History.txt
```
Output:
![](https://cdn.discordapp.com/attachments/1078458930356834344/1084908395326361640/image.png)

The '-p' option seems to take in a pattern, which we inputed as "bishop" and the pattern is highlighted when we ran the command. The first line shown is also jumped to the first occurence of this pattern.

#### *Example 2*
Input:
```
less -p Porto Algarve-Intro.txt
```

Output:
![](https://cdn.discordapp.com/attachments/1078458930356834344/1084907416862326874/image.png)

The '-p' option seems to take in a pattern, which we inputed as "Porto" and less began at the first line occurence of the pattern in the file.

**Summary**

The '-p' option for less allows for searching a file for a pattern. The first occurence of the pattern is highlighted and jumped to.
This option can be highly usefui when searching a large file for a specific section without manually searching and scrolling.

---
### The '-s' Option
For reference, this is the contents of the original and modified ```Sample.txt``` file.

Original:
```
Hello World!
This
Is
A
Test
File!
```
Modified:
```
Hello World!



This


Is

A

Test





File!
```

#### *Example 1*
Input:
```
less -s Sample.txt                                                   
```
Output:
![](https://cdn.discordapp.com/attachments/1078458930356834344/1084909890100789289/image.png)

There does not seem to be anything special about the output compared to normal less.

#### *Example 2*
Let us try this again on Sample.txt, but with a few modifications.

Input:
```
less -s Sample.txt   
```
Output:
![](https://cdn.discordapp.com/attachments/1078458930356834344/1084911042993336330/image.png)

This time, the extra blank lines we added seem to only show as one, despite having more than one.

**Summary**

The '-s' file scans the file for 2 or more blank lines in the file. If there are, it will replace theses blank line chunks with a single blank line.
A use for this option is to increase readability when a file may contain many blank lines consecutively.

---
## Sources For All Grep Options
https://www.geeksforgeeks.org/less-command-linux-examples/
