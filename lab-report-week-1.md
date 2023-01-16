# Tutorial: How to log into a course-specific account on ieng6
This is a lab report about remote access and is a tutorial for incoming 15L students 
(and my future self!) about how to log into a course-specific account on ieng6. There
are about 6 parts to this tutorial:

## 1. Installing Visual Studio Code

First, we will install VScode **(if not already installed you may skip this step and just open the program up)**.
Use this website if necessary [https://code.visualstudio.com/](https://code.visualstudio.com/) and follow the 
instructions to get the program on your computer.

Attached is an image of what the program looks like when you first open it up (which can look different depending on the 
theme the program was set to).

![Image](Screenshot(40).png)


## 2. Remotely Connecting

Next, we will open up the terminal in VScode. You will need to use `$ ssh cs15lwi23zz@ieng6.ucsd.edu` in order
to connect to a remote server. **(Make sure you replace the `zz` with the letters in your course-specified account)**.
Then this message will most likely appear if this is your first time connecting to the server: 
`Are you sure you want to continue connecting (yes/no/[fingerprint])?`, just be sure to type in `yes` and press enter.
Afterwards, make sure to type in your password when asked. Now your terminal has been successfully connected to a remote server!

Attached is an image of what the program looks like when you have been connected.

![Image](Screenshot(41).png)


## 3. Running Some Commands

Next, we will try running some commands to get a glimpse of what we can do on the server. Here is a list of commands you should try!
* `cd ~`
* `cd`
* `ls -lat`
* `ls -a`
* `ls <directory>` where `<directory>` is `/home/linux/ieng6/cs15lwi23/cs15lwi23xyz`, where the `xyz` is one of the other group members’ username
* `cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/`
* `cat /home/linux/ieng6/cs15lwi23/public/hello.txt`

Attached is an image of what the program looks like when you use some of the commands from above.

![Image](Screenshot(42).png)
