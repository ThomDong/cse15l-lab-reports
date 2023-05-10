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
4. The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
