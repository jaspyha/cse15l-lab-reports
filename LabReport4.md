# Lab Report 4
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
  
We are logging into the remote computer with this command. The email address we pasted is the computer we are attempting to log into.

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

This command allows us to clone our repository on GitHub and later modify it.
  
## Run the tests, demonstrating that they fail
---
Change Directory to cloned Repo
```
cd lab7 <Enter>
```

This command changes our directory to the cloned repository so we can compile and run the java files.
 
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
This command compiles all the java files and tests.

Copy run command for Mac
```
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExampleTests
```
Typed with:
```
<Ctrl-V> ListExampleTests <Enter>
```

![](https://cdn.discordapp.com/attachments/1078458930356834344/1078461851928645743/image.png)
This command runs the java tests to check if the code passes the test cases. It states that it failed 2 tests!
  
## Edit the code file to fix the failing test
---
```
nano ListExamples.java <Enter>
```
![](https://cdn.discordapp.com/attachments/1078458930356834344/1078462458466926723/image.png)

This command opens the built-in text editor to edit ListExamples.java!
  
```
<Down>x14 <Right>x22 <Backspace>x3
<Down>x28 <Left>x6 <Backspace> 2
<Ctrl-O> <Enter>
<Ctrl-X>
```
We are navigating to the error using the arrow keys.
We enter <Ctrl-O> <Enter> to save our changes!
We enter <Ctrl-X> to exit nano!

![](https://cdn.discordapp.com/attachments/1078458930356834344/1078463109334827039/image.png)

## Run the tests, demonstrating that they now succeed
---
```
<up>x3 <Enter>
```

![](https://cdn.discordapp.com/attachments/1078458930356834344/1078463576223776840/image.png)
We need to recompile the code and tests, so we use the arrow keys to navigate up our command history!

It is the same as running
  
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
```

```
<up>x3 <enter>
```
![](https://cdn.discordapp.com/attachments/1078458930356834344/1078463458766503976/image.png)

Here we are also renavigating our command history to run the java test!

It is the same as running

```
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExampleTests
```

We see that the test cases all pass!

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

Here, we are telling Git to track changes for ListExamples.java, which we altered to pass the test cases!

Next, we are commiting our changes with a message "Updated". 
This means Git has a version that we want to update the GitHub repository with!

Finally, we use ```git push``` to update the GitHub repository with our current one!

And we are done!

