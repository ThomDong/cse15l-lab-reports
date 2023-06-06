# Lab Report 5
## Part 1 – Debugging Scenario

### 1. Student's Question and TA's Response

Donghyun Hahn:

Title: I keep getting this message from the debugger when I try to test `ListExamples.java` by typing in `bash test.sh`.

What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?

I am using an Asus Windows laptop, Visual Studio Code, and terminal from the VS Code.



Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.

I am really confused on what the difference is between c[:] and c[]. What does that colon between the brackets even mean? 
<img width="487" alt="image" src="https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/79f73d70-5637-41eb-aa3e-4075b6303150">



Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.

This failure happened when I tried to run the test.sh file on my terminal. I tried to run this file to see if everything works fine. I logged into my ssh CSE15L account. The working directory is  `/home/linux/ieng6/cs15lsp23/cs15lsp23rh/lab7`.

TA's Response:

Hey Donghyun!
Firstly, make sure that your current working directory is `/home/linux/ieng6/cs15lsp23/cs15lsp23rh/lab7`. You can check this by typing in `pwd`. Secondly, from the debugger's message: 
`1) testMerge2(ListExamplesTests)
arrays first differed at element [3]; expected:<c[:]> but was:<c[]>`, you can see that there might be something wrong with ListExampleTests.java. 

Why don't you open `ListExamplesTests.java` and try to find where the bug is caused? This is done by using `vim`. Please let us know if you have any more questions regarding this.


### 2. Student's Response:
Donghyun Hahn:


<img width="235" alt="image" src="https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/e6d84d46-9f87-448b-880a-73003b30b62d">

Firstly, I made sure that the current working directory is `/home/linux/ieng6/cs15lsp23/cs15lsp23rh/lab7`. I did this through typing in `pwd`.

<img width="517" alt="image" src="https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/1823acd7-8596-4ac9-8fcc-d5d5ec0f39da">

Secondly, I opened `ListExamplesTests.java` by typing in `vim ListExamplesTests.java`.

<img width="418" alt="image" src="https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/4db8bde3-ca5d-4504-b965-fc63cbb558e3">

From looking at this java file, I realized that the bug was caused by ":" after in between "c". "c:" was causing this bug. What was expected was "c:" instead of "c". I might have added ":" by accident when I tried to type in `:wq` to save and quit the vim. So I removed that colon, and I typed in `bash test.sh` again.

<img width="221" alt="image" src="https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/9ef64de3-c286-4260-bd0b-59ab90b4dbb3">

Now, the two tests did not have any problems. Thank you for the help. It was relatively an easy fix, but it took long time for me to figure out.

### 3. All the Information Needed about the Setup:

Here are all the files structure under `/home/linux/ieng6/cs15lsp23/cs15lsp23rh/lab7`:

<img width="517" alt="image" src="https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/d46094aa-a181-4a7f-934b-4e089f3a0c18">

Contents of `test.sh`

<img width="459" alt="image" src="https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/556dcd66-bbfd-405c-865c-a34d33cd111b">

Contents of `ListExamples.java`

<img width="484" alt="image" src="https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/cf2c2512-8da0-4d43-9e0b-57d06916ed66">

Contents of `ListExamplesTests.java`

<img width="494" alt="image" src="https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/62e82c1a-e378-488c-8666-26d5ad32e90f">

The line that I ran to trigger the bug:

<img width="427" alt="image" src="https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/a56e900e-3acb-4240-ba64-1f64ff9cac60">

A description of what to edit to fix the bug:

Simply, this bug can actually happen, and it happened to me once when I forgot to press `esc` to be in the normal mode and enter `:wq` to save and quit the vim. What you need to edit to fix the bug here is simply deleting that ":" in "c:" After doing so, you will get something like below:

<img width="451" alt="image" src="https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/9092c47c-f02d-442f-8625-4befbfac7d7e">

## Part 2 – Reflection

Funny enough, it is actually my second time taking this course since 2021. Back then, every CSE 15L activities were all remote. Even though it was sometimes challenging for me to actively participate because of the severe injury I had in the second week of this quarter, I have been really fortunate that I was able to participate in in-person lab experience. It made the whole learning experience so much better. Especially in the second half of this quarter, I learned a lot about bash that I really did not know about. I learned bunch of weird, picky bash syntax like having double brackets around if statements.
















