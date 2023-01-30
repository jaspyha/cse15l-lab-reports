# Lab Report 2
## Part 1 (String Server)
My StringServer Code

```java
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
```
