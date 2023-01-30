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
#### Adding "Hello World!"

![Hello World!](https://cdn.discordapp.com/attachments/975608841838415872/1069468198539370526/image.png)

Typing ```localhost:4000/add-message?s=Hello World!``` in for the url triggers the method 
```public String handleRequest(URI url)```.

The url we typed in to our browser is the argument we pass to the URI url parameter.
With the URI, we aquire the path and check if it matches "/add-message", which is the path for adding a string to the output.

Next, we check the first line of the query. In our method, we only add a String to the output if the first String in the query is ```"s"```, indicated by ```query[0]```.

Then, we add the String in ```query[1]``` prepended by ```"\n"``` to the instance variable 
```String messageList = "";```.

This instance variable indicates the output String and is first initailized to an empty String.
After adding ```"query[1] + \n"``` with ```"\n"``` to start a new line for the next string added, we return messageList to display it.

In conclusion, it will output ```messageList```, which is holds the String value of ```"Hello World!\n"```.

---

#### Adding  "What a nice day!"

![What a nice day!](https://cdn.discordapp.com/attachments/975608841838415872/1069468865786032248/image.png)

For this action, it will be similar to the first, but we did not restart the program, so ```messageList``` still holds the value of ```"Hello World!\n"```.

We will type in the URL ```localhost:4000/add-message?s=What a nice day!``` into our search engine which will be passed as a URI to the method ```public String handleRequest(URI url)```. 

We will check the path to make sure it is ```/add-message``` then check if the first value in the query is ```"s"```.
After this, we will append ```"What a nice day!" + "\n"``` to ```messageList```, resulting in ```messageList``` holding the value ```"Hello World!\nWhat a nice day!\n"```.

Since we have ```"\n"``` in the String, the values ```"Hello World!"``` and ```"What a nice day!"``` will be on seperate lines.

As a result, when messageList is returned, this will be displayed on the website!
```
Hello World!
What a nice day!
```

# Part 2 (Junit Testing & Bugs)
## Array File (reverseInPlace)

### Failure-inducing input
```java
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
	    int[] input1 = {1,2,3,4};
	    ArrayExamples.reverseInPlace(input1);
	    assertArrayEquals(new int[]{4,3,2,1}, input1);
	}
}
```
#### Output
![](https://cdn.discordapp.com/attachments/975608841838415872/1069510030367404073/image.png)
---
### Non-Failure-inducing input
```java
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
	    int[] input1 = {10};
	    ArrayExamples.reverseInPlace(input1);
	    assertArrayEquals(new int[]{10}, input1);
	}
}
```
#### Output
![](https://cdn.discordapp.com/attachments/975608841838415872/1069510341194694716/image.png)

---
### Default Code
```java
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
}
```
---
### Revised Code
```java
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < (arr.length/2); i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
}
```
---
### Analysis
#### Flaw
In the original code, the input array is iterated from index[0] to the last index. At index i, the element at index i from the end of the array is assigned as the element of index i in the array. This, however, proves problematic as it keeps the elements at indices of the second half of the array unchanged. For example, {1,2,3,4} would output {4,3,3,4} as 3 and  4 will be assigned to indexes 2 and 3, respectively. This results in their values being unchanged.

#### Solution
By iterating through only half of the array, we can swap the elements at two indexes during the same loop iteration. This is accomplished by assigning the element at the index to the variable ```int temp``` which allows the replaced element to be assinged to its mirrored index element.
# Part 3 (Summary)

