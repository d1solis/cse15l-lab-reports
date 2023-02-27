# Lab Report 4 - CLDQ (Week 7)
This is a lab report of me reproducing the task from the competition on my own using only steps 4-9.

## Step 4. - Log into ieng6
- I typed `ssh cs15lwi23auk@ieng6.ucsd.edu` and pressed `<enter>` which resulted in the following two screenshots below.
![Screenshot(105).png](https://raw.githubusercontent.com/d1solis/cse15l-lab-reports/main/Screenshots%20Folder/Screenshot%20(105).png)
![Screenshot(106).png](https://raw.githubusercontent.com/d1solis/cse15l-lab-reports/main/Screenshots%20Folder/Screenshot%20(106).png)


## Step 5. - Clone your fork of the repository from your Github account
- I typed `rm -rf lab7` and pressed `<enter>` since I was getting this message from cloning: `fatal: destination path 'lab7' already exists and is not an empty directory.`
- After typing that I typed `git clone git@github.com:d1solis/lab7.git` and pressed `<enter>` which resulted in the following screenshot below.
- Then I typed `cd lab7` and pressed `<enter>` and then typed `ls` and pressed `<enter>` which allows me to get started with lab 7 overall.
![Screenshot(107).png](https://raw.githubusercontent.com/d1solis/cse15l-lab-reports/main/Screenshots%20Folder/Screenshot%20(107).png)


## Step 6. - Run the tests, demonstrating that they fail
- I copy and pasted `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and hit `<enter>` 
- I then copy and pasted `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests ListExamples` and hit `<enter>` which resulted in the following screenshots below.
![Screenshot(110).png](https://raw.githubusercontent.com/d1solis/cse15l-lab-reports/main/Screenshots%20Folder/Screenshot%20(110).png)
![Screenshot(111).png](https://raw.githubusercontent.com/d1solis/cse15l-lab-reports/main/Screenshots%20Folder/Screenshot%20(111).png)

## Step 7. - Edit the code file to fix the failing test
- I typed `nano ListExamples.java` to get the nano editor screen.
- Next I pressed `<down>` 6 times and typed `public` before the `class` keyword.
- Next I type `CNTRL-W` and typed `index1 += 1` and pressed `<down>` about 13 times to get to line 43.
- I then pressed `<right arrow key>`, press `<backspace>` and typed `index2` in replace of `index1` (essentially typing in a `2` in replace of the `1`).
- Then I typed `CNTRL-O` and hit `<enter>` to save the file and `CNTRL-X` to exit. 
![Screenshot(112).png](https://raw.githubusercontent.com/d1solis/cse15l-lab-reports/main/Screenshots%20Folder/Screenshot%20(112).png)
![Screenshot(113).png](https://raw.githubusercontent.com/d1solis/cse15l-lab-reports/main/Screenshots%20Folder/Screenshot%20(113).png)

## Step 8. - Run the tests, demonstrating that they now succeed
- For running the tests again, I pressed `<up>` 6 times and pressed `<enter>` to get `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` in my search history to access it again instead of retyping the full command.
- Then I pressed `<up>` 2 times and pressed `<enter>` to get `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` in my search history to access it again instead of retyping the full command.
- Now pressing `<enter>` resulted in the following screenshot below.
![Screenshot(114).png](https://raw.githubusercontent.com/d1solis/cse15l-lab-reports/main/Screenshots%20Folder/Screenshot%20(114).png)

## Step 9. - Commit and push the resulting change to your Github account
- I typed `git add L` and pressed `<tab>` after L to autocomplete it to `ListExamples.java`
- Next I typed `git commit -m "Updated"`
- Finally I typed `git push` which resulted in the following screenshot below.
![Screenshot(120).png](https://raw.githubusercontent.com/d1solis/cse15l-lab-reports/main/Screenshots%20Folder/Screenshot%20(120).png)
