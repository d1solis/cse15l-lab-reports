# Lab Report 2 - Servers and Bugs (Week 3)
**Part 1.**

Below is my code for `StringServer.java`.
```
import java.io.IOException;
import java.net.URI;

class StringHandler implements URLHandler {
    // The one bit of state on the server: a string that will be manipulated by
    // various requests.
    String serverString = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Starting...");

        } else if (url.getPath().contains("/add-message")) {
            String[] val1 = url.getQuery().split("=");

            if(val1[0].equals("s")){
                serverString += "\n" + val1[1];
                return serverString;
            }
            else{
                return "404 Not Found!";
            }

        } else {
            System.out.println("Path: " + url.getPath());
            return "404 Not Found!";
        }
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new StringHandler());
    }
}
```

Attached are the screenshots for `/add-message`:

![Screenshot(78).png](https://raw.githubusercontent.com/d1solis/cse15l-lab-reports/main/Screenshots%20Folder/Screenshot%20(78).png)
- Which methods in your code are called?
  - handleRequest
- What are the relevant arguments to those methods, and the values of any relevant fields of the class?
  - localhost:5322/add-message?s=Hello
- How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
  - When handleRequest is called, "Hello" is being added to `String serverString`.

![Screenshot(79).png](https://raw.githubusercontent.com/d1solis/cse15l-lab-reports/main/Screenshots%20Folder/Screenshot%20(79).png)
- Which methods in your code are called?
  - handleRequest
- What are the relevant arguments to those methods, and the values of any relevant fields of the class?
  - localhost:5322/add-message?s=How are you
- How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
  - When handleRequest is called, "How are you " is being added to `String serverString` which already has "Hello" tracked. Thus, it outputs the entire string where a new line is included after "Hello" and includes "How are you" below it.

**Part 2.**

A failure-inducing input for the buggy program `ArrayTest.java`.
```
@Test 
	public void testReverseInPlace() {
    int[] input1 = { 6, 7, 8 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 8, 7, 6 }, input1);
	}
  
 
  @Test
  public void testReversed() {
    int[] input1 = { 6, 7, 8 };
    assertArrayEquals(new int[]{ 8, 7, 6 }, ArrayExamples.reversed(input1));
  }
```
An input that doesn’t induce a failure, as a JUnit test and any associated code.
```
@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}


  @Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
```

The symptom, as the output of running the tests.
![Screenshot(60).png](https://raw.githubusercontent.com/d1solis/cse15l-lab-reports/main/Screenshots%20Folder/Screenshot%20(60).png)

The bug, as the before-and-after code change required to fix it.

BEFORE:
```
// Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

AFTER:
```
 // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    // Create a copy of the array and insert the reverse array into it
    int[] CopyArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      CopyArray[i] = arr[arr.length - i - 1];
    }
    // Putting the reversed array back into the array
    for(int i = 0; i < arr.length; i++){
      arr[i] = CopyArray[i];
    }
  }

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }

    for(int i = 0; i < arr.length; i++){
      arr[i] = newArray[i];
    }
    return arr;
  }
```
When the second half of the array was being inverted, the issue appeared. When the latter half of the array was being reversed, the elements from the first half 
couldn't be used since they had already been modified because the first half of the array's elements had already been reversed. The array has to be reversed into
an new array copy in order for to fix the issues.

**Part 3.**
Something that I learned in lab 2 is that there is a lot that webservers can do, especially when we focused on programs that take a URL as input and respond with 
the text of a web page. Building and running a server specifically was something that I did not know how to do before, and ports were something that I never knew
about before coming into the class, and was interested to know more about them. 
