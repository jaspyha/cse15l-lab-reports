# Lab Report 2
## Part 1 (String Server)

**My StringServer Code**
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

image[](https://cdn.discordapp.com/attachments/975608841838415872/1069468198539370526/image.png)
image[](https://cdn.discordapp.com/attachments/975608841838415872/1069468316260905041/image.png)

# Part 2 (Junit Testing)

# Part 3 (Summary)

