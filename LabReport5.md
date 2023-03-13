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
grep -A 1 "Liquor" ./written_2/travel_guides/berlitz2/Bahamas-History.txt
```
Output:
```
Liquor money bought Nassau better houses, churches, lighting, water, roads, sewers, docks, and hotels. 
The city’s first gambling casino opened in 1920; the first daily air service from Miami began in 1929; the yacht set decided 
Nassau was fashionable, and many wealthy Americans as well as Prohibition millionaires built homes on the islands.
When the boom suddenly came to an end with the worldwide depression and the repeal of Prohibition in 1933, unemployment rose 
again, despite the first significant tourism the Bahamas had known.
```

#### *Example 2*
Input:
```
less -p Porto Algarve-Intro.txt
```

Output:
![](https://cdn.discordapp.com/attachments/1078458930356834344/1084907416862326874/image.png)

The '-p' option seems to take in a pattern, which we inputed as "Porto" and less began at the first line occurence of the pattern in the file.

**Summary**

The '-A n' option takes in a parameter n that is a number. It indicates the number of lines after the line where the pattern occurs to include in the output as well. In default grep, only the line where the pattern occurs is returned. This is useful when searching through scholarly articles and context is useful.

---
### The '-s' Option
#### *Example 1*
Input:
```
grep -o "Liquor" ./written_2/travel_guides/berlitz2/Bahamas-History.txt                                                    
```
Output:
```
Liquor
```
The command seems to only return the pattern, however Liquor only occurs once in the text file.

#### *Example 2*
Input:
```
grep -o "Columbus" ./written_2/travel_guides/berlitz2/Bahamas-History.txt
```
Output:
```
Columbus
Columbus
Columbus
```
This time, the command returns the pattern 3 times, which also matches with the number of times Columbus occurs in the text file.


**Summary**

The '-o' option returns only the instances it finds in the specified file. Wihtout the option, grep returns the entire line that contains the pattern. With '-o', it is easier to count the number of times a pattern occurs in a file.

---
## Sources For All Grep Options
https://www.geeksforgeeks.org/less-command-linux-examples/
