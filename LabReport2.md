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

3. An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
4. The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
5. The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
