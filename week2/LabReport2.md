# Lab Report 2
## Part 1 (String Server)

### My StringServer Code
```java
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String messageList = "";
  
    public String handleRequest(URI url) {
        if (url.getPath().equals("/add-message")) {
            String[] query = url.getQuery().split("=");
            if (query[0].equals("s")){
                messageList += query[1] + "\n";
                return String.format(messageList);
            }
            return String.format("No Query Entry.");
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
```
---
**Adding "Hello World!"**

![Hello World!](https://cdn.discordapp.com/attachments/975608841838415872/1069468198539370526/image.png)

Typing "localhost:4000/add-message?s=Hello World!" in for the url triggers the method 
```public String handleRequest(URI url)```.

The url we typed in to our browser is the argument we pass to the URI url parameter.
With the URI, we aquire the path and check if it matches "/add-message", which is the path for adding a string to the output.
Next, we check the first line of the query. In our method, we only add a String to the output if the first String in the query is "s", indicated by "query[0]".
Then, we add the String in "query[1]" prepended by "\n" to the instance variable 
```String messageList = "";```.
This instance variable indicates the output String and is first initailized to an empty String.
After adding "query[1] + \n" with "\n" to start a new line for the next string added, we return messageList to display it.

In conclusion, it will output ```messageList```, which is holds the String value of "Hello World!\n".

**Adding  "What a nice day!"**

![What a nice day!](https://cdn.discordapp.com/attachments/975608841838415872/1069468865786032248/image.png)

# Part 2 (Junit Testing)

# Part 3 (Summary)

