# Simple Search Engine:
```
import java.net.URI;
  import java.util.ArrayList;
  
  class Handler implements URLHandler {
      String s;
      ArrayList<String> library = new ArrayList<>();
  
      public String handleRequest(URI url) {
          if (url.getPath().equals("/add")) {
             String[] parameters = url.getQuery().split("=");
             if (parameters[0].equals("s")) {
                 library.add(parameters[1]);
             }
             String returns = "";
             for (int i=0; i < library.size(); i++) {
                 returns += " "+library.get(i);
             }
             return "Library:"+returns;
          }
          else if (url.getPath().equals("/search")) {
             String[] parameters = url.getQuery().split("=");
             if (parameters[0].equals("s")) {
                 for (int i=0; i < library.size(); i++) {
                     if (library.get(i).contains(parameters[1])) {
                     return library.get(i);
                     }
                 }
             }
              return "Search failed!";
          }
          else {
              return "404 Not Found!";
          }
      }
  }
  
  class SearchEngine {
      public static void main(String[] args) throws IOException {
          if(args.length == 0){
              System.out.println("Missing port number! Try any number between 1024 to   49151");
              return;
          }
  s
          int port = Integer.parseInt(args[0]);
  
          Server.start(port, new Handler());
      }
  }


```
Methods: handleRequest()

Relevant arguments: parameter[1] = "/add", "juicy"

Relevant changes: adds juicy to an ArrayList.
![Image](/lab3_images/Lab3-SE1.png)
Methods: handleRequest()

Relevant arguments: parameter[1] = "/add", "watermelon"

relevant changes: adds watermelon to an ArrayList.
![Image](/lab3_images/Lab3-SE2.png)
Methods: handleRequest()
Relevant arguments: parameter[1] = "/add", "watermelooooon", "watermelooooooooooooooooooon"

Relevant changes: adds watermelooooon and watermelooooooooooooooooooon to an ArrayList.
![Image](/lab3_images/Lab3-SE3.png)
Methods: handleRequest()

Relevent arguments: parameter[1] = "/search", "water"

Relevant arguments: "search" searches for all strings in the library that contain "water".
![Image](/lab3_images/Lab3-SE4.png)






# Problem 1:
The first problem is the reverseInPlace() method.

This test produced a failure in the method:
![Image](/lab3_images/Lab3-p1-test.png)

Here is the output of the test (symptoms)
![Image](/lab3_images/Lab3-p1-symptoms.png)

And here is the bug, and an example of a solution:
![Image](/lab3_images/Lab3-p1-bug.png)
![Image](/lab3_images/Lab3-p1-sln.png)

This problem would be replicated for an array of any size greater than one, and contained different elements at the beginning and end. The issue was that the first element of the array was being overwritten and so the last index was being refilled with its original value. Also, to prevent the array from performing this on every other index in the first half, the array should stop at `.length/2`.

# Problem 2:
For the second problem we will be looking at the `merge` method from ListExamples.


This test produced a failure in the method:
![Image](/lab3_images/Lab3-p2-test.png)

Here is the output of the test (symptoms)
![Image](/lab3_images/Lab3-p2-symptoms.png)

And here is the bug, and an example of a solution:
![Image](/lab3_images/Lab3-p2-bug.png)
![Image](/lab3_images/Lab3-p2-sln.png)

An OutOfMemoryError was triggered as a symptom. This was caused by the program entering an infinite loop. Any input outside of empty lists would have caused this, as the index2 was not being incremented as expected. This filled the computers memory until the program eventually crashed.