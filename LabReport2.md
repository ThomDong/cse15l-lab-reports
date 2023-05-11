# PART 1

Code for the StringServer.java:

~~~
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
   
    String str = "";

    public String handleRequest(URI url) {
        
            System.out.println("Path: " + url.getPath());
            if (url.getPath().equals("/add-message")) {
                String[] parameters = url.getQuery().split("=");
            
                if (parameters[0].equals("s")) {
                    str += parameters[1] + "\n";
                    return String.format( "%s", str);
                }
                    
                
            }
            return "404 Not Found!";
        }
    }
    class StringServer {
      public static void main(String[] args) throws IOException {
      if(args.length == 0){
        System.out.println("Missing port number! Try any number between 1024 to 49151");
        return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
~~~
Now, we will try using the code above to add message
Let's first compile. Type in on your terminal

~~~
javac Server.java StringServer.java
~~~
Now, let's run this thing. Type in on your terminal
~~~
java StringServer 4200
~~~
![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/c099052e-1dfd-4a3e-83f0-feedd73e5731)
You will not get a link on your terminal.

After running StringServer with port number 4200, you will see the link below.
http://localhost:4200

Now, after 4200 on the address, type in /add-message?s=How are you
Then you will something like below.




Screenshots of using /add-message.:
![image](https://user-images.githubusercontent.com/130010181/234196298-060dcaf1-c736-4877-89ed-b2da449ca2b1.png)
In the screenshot above, main() method is called in order for the command line arguments to work. HandleRequest() method is also being called to pass the request to the URI. The relevant arguments and the values of any relevant fileds of the class for the main() method is args array (command line arguments), port (port number). The relevant arguments and the values of any relevant fields of the class to handleRequest() method is uri object, str, and parameters array. The relevant field that is changed is the str. Specifically, from this request str value is "How are you".

Now let's add some more messages.
Again, after 4200 on the address, type in /add-message?s=Wassup
Then you will something like below.
![image](https://user-images.githubusercontent.com/130010181/234196409-16a32a0b-3f94-4a2c-8b52-ede29ed29073.png)
In the screenshot above, main() method is called in order for the command line arguments to work. HandleRequest() method is also being called to pass the request to the URI. Specifically in this scenario, the request add-message/?s=Wassup is being processed to handle the specific request.The relevant arguments and the values of any relevant fileds of the class for the main() method is args array (command line arguments), port (port number). The relevant arguments and the values of any relevant fields of the class to handleRequest() method is url, str, and parameters array. The relevant field that is changed is the str. Specifically, from this request str value is "How are you\n + wassup".
# PART 2
Okay, now I am going to choose a program that has some bugs. I chose reverseInPlace from ArrayExamples.java
1. A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown
I am going to test this input: {1, 2, 3, 4}.
~~~
@Test
  public void testReverseInplace2() {
    int[] input2 = {1, 2, 3, 4}; 
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[] {4, 3, 2, 1 }, input2);
  }
~~~
![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/e875a228-ceb2-4d70-8853-9bf8b27971de)
Another failure-inducing input: {101, 201, 301, 401}.
~~~
 @Test
 public void testReverseInplace3() {
    int[] input3 = {101, 201, 301, 401}; 
    ArrayExamples.reverseInPlace(input3);
    assertArrayEquals(new int[] {401, 301, 201, 101 }, input3);
  }
~~~  
![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/c11f378b-140c-47d4-994c-0332421c9015)
Another failure-inducing input: {99, 97, 95, 93}
~~~
@Test
  public void testReverseInplace4() {
    int[] input4 = {99, 97, 95, 93}; 
    ArrayExamples.reverseInPlace(input4);
    assertArrayEquals(new int[] {93, 95, 97, 99}, input4);
  }
~~~
![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/e728799c-334e-4eef-85d9-b39981301873)

2. An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)

An input that does not induce a failure: { 3,3,3 }
~~~
@Test 
	public void testReverseInPlace() {
    int[] input1 = {3,3,3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{3,3,3}, input1);
	}
~~~
![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/78467f0d-a6b2-4a33-ac3b-976ba6c9b7ca)
You can see from the screenshot above the test is smoothly passed, and there is no problem with it. This is because an input with the same number inside will not cause any problems within the test.

3. The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
screenshots

a.
![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/53ea7b1a-c536-46f9-87ea-1afebff31f40)
b.
![image](https://github.com/ThomDong/cse15l-lab-reports/assets/130010181/e1b0c4b1-d613-4142-96cf-535bbcef8347)
Alright now, let us look at the first and second example. There are four elements total. These are [0],[1],[2],and [3]. From the input, our goal is to have them flipped. So, if input is [0],[1],[2],and [3], then the output should be [3],[2],[1],and [0]. However, both examples show that there was  a problem with the flipped output at element [2]. It is supposed to have element [1] of the original input at the element [2] of the output. Instead. the element [2] of the output is having [2] of the input. The element [1] of the output is equal to the element [2] of the input as it should be. However, the symptom here in both examples is that element [1] of the input is being overwritten at the element [2] of the output when element [2] of the ouput should be euqal to the element [1] of the input.


4. The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)

Before:

~~~
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
~~~

After:

~~~
for(int i = 0; i < arr.length/2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
~~~

Brief Description:

In the code before, the for loop iterates over the entire array, resulting in overwriting. It does not correctly update the newly created reversed array. Change from "for(int i = 0; i < arr.length; i += 1)" to "for(int i = 0; i < arr.length/2; i += 1)" is to ensure that the for loop iterates until the half length of the array in order to update the elements of the new array correctly. We don't want any overwriting. In order to avoid overwriting, we would need a temporary variable that can hold arr[i]. Then arr[i] also has to hold arr[arr.length - i - 1] in order to correctly update the value of index[i] with values from index[arr.length - i - 1]. Then,arr[arr.length - i - 1] equals temp to correctly update the value of temp.

# PART 3
What I leared from labs in week 2 or week 3
From week 2 lab, I learned how to get the code from my GitHub repository onto Visual Studio Code. I feel like this skill is really essential. I learned how to use GitHub Desktop. In week 3 lab, I learned how to compile and run java programs on the terminal of Visual Studio Code. I also realized that MAC and WINDOW have different commands format to compile and run java programs on the terminal. Especially, week 2 lab was really interesting because I leanred how to modifty the web page with different queries in the url, using the java program.



