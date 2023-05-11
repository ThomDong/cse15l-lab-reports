# Lab Report 3 
First I will show you how I found some interesting command line options for the grep command
Here is the source to how I found these: https://chat.openai.com/
![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/6516879e-63d8-485b-b895-2ed6c4c95ab3)
## grep -i ##

According to ChatGPT, -i option ignores case distinctions in both the pattern and input files. Therefore, if -i is used, grep will find all the lines with the argument both in upper and lower case letters.

Example 1:

![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/9d84d185-2e5f-4529-8bf3-2b633fd082fc)
In the example above I put:

~~~
$ grep -i "third" /c/Users/hahnd/Documents/GitHub/docsearch/technical/911report/chapter-1.txt
~~~
in order to find the word "third" no matter of the word's cases. The output shows all of the lines with the word "third" regardless of its cases. You can see "Third" or "third" in the output.

Example 2:

![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/0a4c6d05-c540-4610-b760-536c217ecab1)

In the example above I put:
~~~
grep -i "the" /c/Users/hahnd/Documents/GitHub/docsearch/technical/911report/chapter-1.txt
~~~

in order to find the word "the" no matter of the word's cases. The output shows all of the lines with the word "the" regardless of its cases. You can see "The" or "the" in the output. It is interesting that it also finds "Their."

## grep -v ##

According to ChatGPT, -v option finds all the lines that do not contain the argument word. Therefore, if -v is used, grep will find all the lines without the argument word.

Example 1:

![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/792d671c-d00c-4867-85bc-60895db96450)
In the example above I put:
~~~
grep -v "the" /c/Users/hahnd/Documents/GitHub/docsearch/technical/911report/chapter-1.txt
~~~

in order to find the lines that do not contain the most commonly used word in English "the". The output shows all of the lines without the word "the". You can see "THE" or "Their" in the output. It is interesting that it does not see "THE" as "the." It only finds lines that do not include specifically "the."

Example 2:

![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/c792b28c-4262-4cfd-9a56-bfc876a40003)

In the example above I put:
~~~
grep -v "he" /c/Users/hahnd/Documents/GitHub/docsearch/technical/911report/chapter-1.txt
~~~

in order to find the lines that do not contain the most commonly used word in English "he". The output shows all of the lines without the word "he". You can see "THE" in the output. Again, it is interesting that it does not see "HE" as "he." It only finds lines that do not include specifically "he."

## grep -e ##
According to ChatGPT, -e option takes two or more arguments to finds all the lines that contain either argument 1 or argument 2 or argument 3 etc. Therefore, if -e is used, grep will find all the lines with given arguments.

Example 1:

![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/bcffdb3d-3312-4aa6-ae4e-364da21f71be)
In the example above I put:
~~~
grep -e "CAPPS" -e "Appreciate" /c/Users/hahnd/Documents/GitHub/docsearch/technical/911report/chapter-1.txt
~~~
in order to find the lines that contain either "CAPPS" or "Appreciate". The output shows all of the lines that contain either "CAPPS" or "Appreciate". You can see "Appreciate" at the last line.

Example 2:

![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/0d3d693c-344f-4c41-9beb-8d8bb361c38d)

In the example above I put:
~~~
grep -e "9:37" -e "9:25" -e "10:31" /c/Users/hahnd/Documents/GitHub/docsearch/technical/911report/chapter-1.txt
~~~
in order to find the lines that contain either "9:37" or "9:25" or "10:31". The output shows all of the lines that contain either either "9:37" or "9:25" or "10:31". From this, I realized that -e can be helpful when searching for lines with specific numbers that you want.



## grep -n ##

According to ChatGPT, -n option takes an arguments to finds all the lines that contain the argument with line numbers. Therefore, if -n is used, grep will find all the lines with given argument with line numbers outputted.

Example 1:

![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/e708f42d-d3a0-4fd5-80e8-0198de365509)

In the example above I put:
~~~
grep -n "10:31" /c/Users/hahnd/Documents/GitHub/docsearch/technical/911report/chapter-1.txt
~~~
in order to find the lines that contain "10:31". The output shows all of the lines that contain "10:31" with the line numbers. From this, I realized that -n can be helpful when searching for lines with specific words or numbers. Also, it is very user friendly because it outputs the line number within the txt file.

Example 2:

![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/250826e1-485e-456e-a642-c5ef49183cfa)

In the example above I put:
~~~
grep -n "the" /c/Users/hahnd/Documents/GitHub/docsearch/technical/911report/chapter-1.txt
~~~
in order to find one of the most common words "the." along with the line numbers. From this, I realized that -n can be helpful when searching for lines with common words or numbers. Also, it is very user friendly because it outputs the frequency of the common words within the txt file. Anyone who is curious about the frequency of common words within the txt file can try this command.

