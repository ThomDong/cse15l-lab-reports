# Lab Report 5
## Part 1 – Debugging Scenario

1. Student's question and TA's response
Donghyun Hahn:
Title: I keep getting this message from the debugger when I try to test if every file works smoothly in Lab 7 

What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?
I am using a PC laptop, Windows, Visual Studio Code, and terminal.



Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.

I am really confused on what the difference is between c[:] and c[]. What does that colon between the brackets even mean? 
<img width="487" alt="image" src="https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/79f73d70-5637-41eb-aa3e-4075b6303150">



Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.

This failure happened when I tried to run the test.sh file on my terminal. I tried to run this file to see if everything works fine. I logged into my ssh CSE15L account. The working directory is lab7.

TA's response:

Hey Donghyun!
Firstly, make sure that your current working directory is lab7. You can check this by typing in `pwd`. Secondly, from the debugger's message: 
"1) testMerge2(ListExamplesTests)
arrays first differed at element [3]; expected:<c[:]> but was:<c[]>", you can see that there might be something wrong with ListExampleTests.java. 

Why don't you open ListExamplesTests and try to find where the bug is caused? This is done by using vim. Please let us know if you have any more questions regarding this.
2.
<img width="517" alt="image" src="https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/1823acd7-8596-4ac9-8fcc-d5d5ec0f39da">









