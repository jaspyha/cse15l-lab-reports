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

This means that the '-i' option removes the case-sensitive aspect of pattern matching with default grep!

---
### The '-w' Option
#### *Example 1*
Input:
```

```
Output:
```

```

#### *Example 2*
Input:
```

```
Output:
```

```

---
### The '-A n' Option
#### *Example 1*
Input:
```

```
Output:
```

```

#### *Example 2*
Input:
```

```
Output:
```

```

---
### The '-o' Option
#### *Example 1*
Input:
```

```
Output:
```

```

#### *Example 2*
Input:
```

```
Output:
```

```

---
## Sources
https://www.geeksforgeeks.org/grep-command-in-unixlinux/
