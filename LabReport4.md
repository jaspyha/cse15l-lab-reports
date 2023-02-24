# Lab Report 4
rm -rf lab7 to remove old repository

## Setup Delete any existing forks of the repository you have on your account
---

## Setup Fork the repository
---

## Log into ieng6
---
Copy email from notepad with <Ctrl-C>

```
ssh cs15lwi23aig@ieng6.ucsd.edu
```

Typed with:
```
ssh <Ctrl-V> <Enter>
```

![](https://cdn.discordapp.com/attachments/1078458930356834344/1078458946681045085/image.png)
## Clone your fork of the repository from your Github account
---
Copy SSH from github repository
![](https://cdn.discordapp.com/attachments/1078458930356834344/1078460078555938927/image.png)

```
git clone git@github.com:jaspyha/lab7.git
```
Typed with:
```
git clone <Ctrl+V> <Enter>
```
![](https://cdn.discordapp.com/attachments/1078458930356834344/1078460295430799390/image.png)

## Run the tests, demonstrating that they fail
---
Change Directory to cloned Repo
```
cd lab7 <Enter>
```

Compile Junit Tests
Copy compile command for Mac
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
```
Typed with:
```
<Ctrl-V> <Enter>
```
![](https://cdn.discordapp.com/attachments/1078458930356834344/1078461919108804669/image.png)

Copy run command for Mac
```
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExampleTests
```
Typed with:
```
<Ctrl-V> ListExampleTests <Enter>
```

![](https://cdn.discordapp.com/attachments/1078458930356834344/1078461851928645743/image.png)

## Edit the code file to fix the failing test
---
```
nano ListExamples.java <Enter>
```
![](https://cdn.discordapp.com/attachments/1078458930356834344/1078462458466926723/image.png)

down 14, right 22, backspace 3
down 28, left 6, backspace 1, 2
Ctrl-o enter
ctrl-x

![](https://cdn.discordapp.com/attachments/1078458930356834344/1078463109334827039/image.png)
## Run the tests, demonstrating that they now succeed
---
up 3 <Enter>
![](https://cdn.discordapp.com/attachments/1078458930356834344/1078463576223776840/image.png)
up 3 <enter>
![](https://cdn.discordapp.com/attachments/1078458930356834344/1078463458766503976/image.png)


## Commit and push the resulting change to your Github account
---
```
git add ListExamples.java <Enter>
git commit -m "Updated" <Enter>
git push <Enter>
```

![](https://cdn.discordapp.com/attachments/1078458930356834344/1078471931994570873/image.png)
![](https://cdn.discordapp.com/attachments/1078458930356834344/1078472063951589386/image.png)
![](https://cdn.discordapp.com/attachments/1078458930356834344/1078472127465918504/image.png)
