# Week 1 Lab Report
## Downloading Visual Studio Code

![](https://cdn.discordapp.com/attachments/975608841838415872/1064026680290705408/image.png)

What is VS Code?
VS Code is a popular code editor

To begin, click on the link below to visit the VS Code website
Then, download the file for your operating system. (Mac/Windows/Linux)

There will be 3 different icons for Windows, Linux, and Mac repectively.
![](https://cdn.discordapp.com/attachments/1023456934248058934/1064022830834012210/image.png)

Download: [VScode link](https://code.visualstudio.com/download)

After completing the download, open the file and finish the setup process.

Finally, open VSCode!
![](https://cdn.discordapp.com/attachments/1023456934248058934/1064025514727190528/image.png)

It should look like this!

## Remotely Connecting
![](https://cdn.discordapp.com/attachments/975608841838415872/1064027980541730836/Git-Icon-1788C.png)

To remotely connect to the account, we will be using Git Bash. We will follow a process similar to downloading Visual Studio Code.
The download link is below!

Download: [Git link](https://git-scm.com/downloads)

After Git is downloaded, open the terminal with Ctrl+\`
From there press Ctrl+Shift+P and adjust the terminal to Git Bash.
A pop-up will appear at the top of your screen after pressing the keybind and type in "Select Default Profile".
![](https://cdn.discordapp.com/attachments/975608841838415872/1064394235299774484/image.png)

(If Git Bash does not appear, restart VSCode!)

To connect we will be using SSH (Secure Shell)

We will do this by typing in this in the terminal
(For the email, remember to replace the "xx" with your account number)
```
$ ssh cs15lwi23xx@ieng6.ucsd.edu
```
After pressing Enter, it will prompt you for your account password that you set earlier
```
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is XXXX.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```
Then type "yes" into the terminal and press enter.

A successful login will display a lot of statistics about the server
![](https://cdn.discordapp.com/attachments/975608841838415872/1064632487881482281/image.png)

## Running Commands
Now that we have established a remote connection, we can run basic commands in the terminal.
This will allow us to remotely manage files on the computer.


Some of the basic terminal commands:
**Print Working Directory:** *pwd* (Displays the current directory/path you are in)
![](https://cdn.discordapp.com/attachments/975608841838415872/1064633433629917234/image.png)

**Change Directory:** *cd <path>* (Sets the current directory to the specified path)

**List:** *ls* (Displays files in current dirctory)

![](https://cdn.discordapp.com/attachments/975608841838415872/1064633053714059325/image.png)
  
 *-a* (displays more details about the files)
  
 ![](https://cdn.discordapp.com/attachments/975608841838415872/1064633148421460008/image.png)
 
 *-lat*(displays even more details about the files)
 
  ![](https://cdn.discordapp.com/attachments/975608841838415872/1064633281515098122/image.png) 
 
**Copy:** *cp <path>* (Copies the file at specified path to current directory)

**Display Contents:** *cat <path>* (Displays the contents of the file at specified path i.e .txt, .java)

  ![](https://cdn.discordapp.com/attachments/975608841838415872/1064635053889560658/image.png)
  
**Exit Terminal:** *exit*

## Summary
  This week, we learned how to install VSCode and Git, while learning basic navigation on a remote connection through ssh commands.
