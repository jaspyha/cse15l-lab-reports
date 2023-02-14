# Lab Report 3

## Bash Grep Command Options
---
### The '-i' Option
#### *Example 1*
Input:
```
grep -i "coLumBuS" ./written_2/travel_guides/berlitz2/Bahamas-History.txt
```

Output:
```
Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal 
Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
```

In our input, "coLumBus" is clearly not in the text file, however "Columbus" is! This tells us a bit about the '-i' option where the capitalization seems to be ignored.

#### *Example 2*
Input:
```
grep -i -l "THE" ./written_2/travel_guides/berlitz2/Bahamas-History.txt
```

Output:
```
./written_2/travel_guides/berlitz2/Bahamas-History.txt
```

The output being the original input file indicates that the pattern successfully exists in the file.


However, running the same command but without '-i'

Input:
```
grep -l "THE" ./written_2/travel_guides/berlitz2/Bahamas-History.txt
```

Output:
```

```

The blank means that the file did not contain the pattern!

**Summary**

This means that the '-i' option removes the case-sensitive aspect of pattern matching with default grep! 

This is useful for when we want to locate lines/files matching a pattern where capitalizations prevent the defauilt grep to be used.

---
### The '-w' Option
#### *Example 1*
Input:
```
grep -w "Colum" ./written_2/travel_guides/berlitz2/Bahamas-History.txt
```
Output:
```

```
The output is blank, so there is clearly something wrong as in the previous example with '-i' "Columbus" is in the file.

Let's try "Columbus" this time and see the result.

#### *Example 2*
Input:
```
grep -w "Columbus" ./written_2/travel_guides/berlitz2/Bahamas-History.txt
```
Output:
```
Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal 
Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
```

This output is the exact same as Example 1 for the '-i' option.
This means that it successfully found the lines containing "Columbus".

**Summary**
The '-w' option is used to indicate the pattern as a word. It ensures that there are spaces before and after the pattern. That is why in Example 1 "Columbus" could not be found as "Colum" is a fragment of the word. This option is useful when we are attempting to find words that are contained in other words, such as finding all "at" in a text file. With the default option, "cat" and "bat" would be included as a match.

---
### The '-A n' Option
#### *Example 1*
Input:
```
grep -A 1 "Liquor" ./written_2/travel_guides/berlitz2/Bahamas-History.txt
```
Output:
```
Liquor money bought Nassau better houses, churches, lighting, water, roads, sewers, docks, and hotels. The city’s first gambling casino opened in 1920; the first daily air service from Miami began in 1929; the yacht set decided Nassau was fashionable, and many wealthy Americans as well as Prohibition millionaires built homes on the islands.
When the boom suddenly came to an end with the worldwide depression and the repeal of Prohibition in 1933, unemployment rose again, despite the first significant tourism the Bahamas had known.
```

#### *Example 2*
Input:
```
grep -A 0 "Liquor" ./written_2/travel_guides/berlitz2/Bahamas-History.txt
```
The '-A n' option seems to take in a number for 'n'. It also seems like two sentences are returned. The second sentence does not seem to contain "Liquor".

Output:
```
Liquor money bought Nassau better houses, churches, lighting, water, roads, sewers, docks, and hotels. The city’s first gambling casino opened in 1920; the first daily air service from Miami began in 1929; the yacht set decided Nassau was fashionable, and many wealthy Americans as well as Prohibition millionaires built homes on the islands.
```
The '-A n' option seems to take in a number for 'n'. It also seems like only one sentence is returned in comparision to two in Example 1.

**Summary**
The '-A n' option takes in a parameter n that is a number. It indicates the number of lines after the line where the pattern occurs to include in the output as well. In default grep, only the line where the pattern occurs is returned. This is useful when searching through scholarly articles and context is useful.

---
### The '-o' Option
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
https://www.geeksforgeeks.org/grep-command-in-unixlinux/
