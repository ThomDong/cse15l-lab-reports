# Part1

Code for the StringServer.java:

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

Screenshots of using /add-message.:
![image](https://user-images.githubusercontent.com/130010181/234196298-060dcaf1-c736-4877-89ed-b2da449ca2b1.png)
In the screenshot above, main() method is called in order for the command line arguments to work. HandleRequest() method is also being called to pass the request to the URI. The relevant arguments and the values of any relevant fileds of the class for the main() method is args array (command line arguments), port (port number). The relevant arguments and the values of any relevant fields of the class to handleRequest() method is url, str, and parameters array. The relevant field that is changed is the str. Specifically, from this request str value is "How are you".
![image](https://user-images.githubusercontent.com/130010181/234196409-16a32a0b-3f94-4a2c-8b52-ede29ed29073.png)
In the screenshot above, main() method is called in order for the command line arguments to work. HandleRequest() method is also being called to pass the request to the URI. The relevant arguments and the values of any relevant fileds of the class for the main() method is args array (command line arguments), port (port number). The relevant arguments and the values of any relevant fields of the class to handleRequest() method is url, str, and parameters array. The relevant field that is changed is the str. Specifically, from this request str value is "How are you \n wassup".
