# Lab Report 4

## Step 4: Logging into ieng6
![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/d60cbead-5fd6-498e-a5c4-e4481193f6b1)
To log into ieng6, I typed in 
~~~
ssh cs15lsp23rh@ieng6.ucsd.edu
~~~
The image above shows what has to be displayed after you log into ieng6.
For you, the two letters rh are different. I did not need to type in any passwords as I generated SSH Keys for ieng6.

## Step 5: Cloning my fork of the repository from my Github account

After deleting the fork of the given repository, I forked it again (see step 1 and 2). To clone my fork of the given repository from my Github account, I typed in 
~~~
git clone git@github.com:ThomDong/lab7.git
~~~


![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/2d6db386-ab4d-46e0-98c1-76972ba67be0)
After you successfully clone the fork, you will get a message like this shown in above.

## Step 6: Running the tests, demonstrating that they fail

In order for me to run the tests, I have to change the directory to lab7.
To do this, I typed in 
~~~
cd lab7
~~~
Then, to demonstrate that tests fail. I typed in 
~~~ 
bash test.sh
~~~
to show that the test bash file has a failure.
After you change the directory to lab7 and successfully run the tests, you will see something like below:
![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/1e3bbad3-ef17-496e-89ee-94b0f80ae171)
You can see from the above image that out of two tests, there is one failure.

## Step 7: Editting the code file ListExamples.java to fix the failing test

To edit the code file ListExamples.java, I typed in:
~~~
vim ListExamples.java
~~~

![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/7d084026-7a1f-478d-a092-f5b562638012)

Like the image shown above, after you type in the command, you will see that vim opened ListExamples.java so that we can edit the necessary spots to fix the test failures.
Now I typed in
~~~
/change<enter>
~~~
Then I typed in
~~~
jllli<backspace>2
~~~
Then I typed in
~~~
:wq
~~~

~~~
/change<enter>
~~~
What I typed above searches and find for the characters "change" and by hitting the enter key, the cursor will be right at the character 'c'.
![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/c289de6e-7e70-4931-9639-5a8794ad0844)
At the end of this step, the cursor will be at the spot where you see above.
~~~
jllli<backspace>2
~~~
Let's look at what I typed above. Now that the cursor is right at the character 'c', pressing 'j' once will make the cursor go to the line below. Then, pressing l three times will allow the cursor to be at ';'. Now, I typed in 'i' to be in the insert mode. Then hit the backspace key to delete 1. Now, I pressed 2 to change 1 to 2.

![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/b36129fb-9faa-451b-94b8-797cd015c53e)

At the end of this step, you see that 1 was change to 2. This is a necessary edit (changing index1 to index2) to fix the bug.

~~~
:wq
~~~
Let's look at what I typed above. After making a necessary change, we need to save it. To quit and save from vim, I typed in ':' to be in the normal mode. Then I typed in "wq" to successfully save and quit the file.
![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/5d4d029a-1cb8-461a-977e-9a91b5d2248d)
At the end of this step, you can see that I am out of the vim editor now.


## Step 8: Running the tests and demonstrating that they now succeed
To run the tests, again, I typed in
~~~
bash test.sh
~~~
![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/adfc4c4d-5e91-4c18-9c53-890700e35890)
As you see above in the terminal, unlike before, now all the tests are OK. They succeeded.
## Step 9: Commit and push the resulting changes to my GitHub account

After generating SSH Keys for GitHub during lab time, I can now commit and push the changes using SSH. To do this, I typed in

~~~
git add .
~~~
This will add changes to all files by typing in '.'
By typing in
~~~
git status
~~~
![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/0b7ec9ac-8555-437a-afb8-03cd34a0d274)
You will see something like above. You can see that ListExamples.java was modified.
Now, type in 
~~~
git commit -m "fixed tests"
~~~
![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/d21f0965-e76a-4813-97c0-837fe72c8fb4)
Now, you will see something like above. You can see that there was 1 insertion and 1 deletion. When I committed, I chose the commit message to be "fixed tests" 
Now, type in 
~~~
git push
~~~
![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/73c341ba-627d-48eb-8538-c277766e8587)
From above, now, you see that changes were added, committed, and pushed.



