# Lab Report 4 - CLDQ (Week 7)
This is a lab report of me reproducing the task from the competition on my own using only steps 4-9.

## Step 4. - Log into ieng6
- I typed `ssh cs15lwi23auk@ieng6.ucsd.edu` and pressed `<enter>` which resulted in the following two screenshots below.

![Screenshot(105).png](https://raw.githubusercontent.com/d1solis/cse15l-lab-reports/main/Screenshots%20Folder/Screenshot%20(105).png)
![Screenshot(106).png](https://raw.githubusercontent.com/d1solis/cse15l-lab-reports/main/Screenshots%20Folder/Screenshot%20(106).png)


## Step 5. - Clone your fork of the repository from your Github account
- I typed `rm -rf lab7` and pressed `<enter>` since I was getting this message from cloning: `fatal: destination path 'lab7' already exists and is not an empty directory.`
- After typing that I typed `git clone git@github.com:ucsd-cse15l-w23/lab7.git` and pressed `<enter>` which resulted in the following screenshot below.
- Then I typed `cd lab7` and pressed `<enter>` and then typed `ls` and pressed `<enter>` which allows me to get started with lab 7 overall.

![Screenshot(107).png](https://raw.githubusercontent.com/d1solis/cse15l-lab-reports/main/Screenshots%20Folder/Screenshot%20(107).png)


## Step 6. - Run the tests, demonstrating that they fail
- I copy and pasted `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and hit `<enter>` 
- I then copy and pasted `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests ListExamples` and hit `<enter>` which resulted in the following screenshots below.

![Screenshot(110).png](https://raw.githubusercontent.com/d1solis/cse15l-lab-reports/main/Screenshots%20Folder/Screenshot%20(110).png)
![Screenshot(111).png](https://raw.githubusercontent.com/d1solis/cse15l-lab-reports/main/Screenshots%20Folder/Screenshot%20(111).png)

## Step 7. - Edit the code file to fix the failing test


## Step 8. - Run the tests, demonstrating that they now succeed


## Step 9. - Commit and push the resulting change to your Github account
